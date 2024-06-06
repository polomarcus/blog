---
title: Rebalancing Kafka’s partitions
description: A real life feedback from TabMo’s Kafka Cluster
date: '2018-10-29T12:53:30.479Z'
categories: []
tags : [
    "kafka"
]
slug: /@polomarcus/rebalancing-kafkas-partitions-803918d8d244
---

After quite a time, uneven partitions and unbalanced brokers can make their way up to your dear Kafka cluster. Leaving you no choice but reassigning your partitions.

This is the story of our recent partitions reassignment at [TabMo, an AdTech company,](http://tabmo.io/) to help you with yours.

![](https://cdn-images-1.medium.com/max/1200/1*ef-RZJwEZ93kkLAGCFhgBg.png)

Before starting, let’s quote the Kafka documentation about partition

> More partitions allow greater parallelism for consumption, but this will also result in more files across the brokers.

An unbalanced cluster can generate unnecessary disk, CPU problems or even the need to add another broker to handle unexpected traffic 💥

### Kafka tools

These tools are great, **it’s rare so it’s better to highlight them** : [well documented](http://kafka.apache.org/documentation.html#basic_ops_automigrate), simple to use, and does not contain obvious bugs. We are going to focus on this one:

kafka-reassign-partitions  
This command moves topic partitions between replicas.

kafka-reassign-partitions has 2 flaws though, it is not aware of **partitions size**, and neither can provide a plan to reduce the number of **partitions to migrate from brokers to brokers.** By trusting it blindly, you will stress your Kafka cluster for nothing. It’s clever to calculate our own plan for large topics an to use the Kafka proposed for smaller one.

![](https://cdn-images-1.medium.com/max/1200/1*Xf4zjEtiAsi2j4KTfVge_g.png)

Thanks to our fancy calculations, we can get an optimized plan for Kafka 🔬

### Practice with Docker-compose

[This repo by](https://github.com/simplesteph/kafka-stack-docker-compose/) [Stéphane Maarek](https://medium.com/u/98189c4cef0), a Kafka evangelist, [is a goldmine](https://github.com/simplesteph/kafka-stack-docker-compose/), it contains all versions of Kafka, and a yaml file that provide [the handy Landoop’s UIs](https://github.com/Landoop/kafka-topics-ui).

#### Launch our kafka stack

With this repo, we can practice our skills before executing the reassignment of our dev and prod cluster. Here, we are going to increase the replication factor of one topic. This is the same script used for partitions reassignment, so it will be the same as moving partitions from broker to broker.

git clone [git@github.com](mailto:git@github.com):simplesteph/kafka-stack-docker-compose.git

#Choose your own Kafka version thanks to the repo tags   
git checkout tags/v4.1.0 for example

Choose your favorite yaml file from the repo, in our case we want multiple brokers, so zk-single-kafka-multiple.yml is ideal.
```
\# the -d is for detached to avoid massive log spam  
docker-compose -f zk-single-kafka-multiple.yml up -d
```
#### Create our topic my-topic

Once your containers are ready , you can connect to one of your broker, out of 3, to generate a topics, by sending messages directly
```
\# get kafka container name --> kafkastackdockercompose\_kafka1\_1  
docker ps

\# Connect to our broker  
docker exec -it kafkastackdockercompose\_kafka1\_1 bash
```
**\# All Kafka's scripts are stored in /usr/bin so available from everywhere**  
```
kafka-console-producer --broker-list localhost:9092 --topic my-topic

\> message 1  
\> message 2
```
#### Increase the number of partition from 1 to 3

Just to have more partitions to “play” with.

```
kafka-topics --topic my-topic --alter --partitions 3 --zookeeper zoo1

\# Observe partitions with Number of partition 3 and RF: 1  
kafka-topics --topic my-topic --describe  --zookeeper zoo1

Topic:my-topic PartitionCount:3 ReplicationFactor:1 Configs:  
 Topic: my-topic Partition: 0 Leader: 1 Replicas: 1 Isr: 1  
 Topic: my-topic Partition: 1 Leader: 2 Replicas: 2 Isr: 2  
 Topic: my-topic Partition: 2 Leader: 3 Replicas: 3 Isr: 3
```
#### Describe the topic we want to “move”

[Based on the documentation](http://kafka.apache.org/documentation.html#basic_ops_automigrate), we can use a template to select our topic to move, but we can also generate it by using this TabMo homemade script. It will select all topics and generate our topics-to-move.json
```
echo '{"topics": \[' > topics-to-move.json && kafka-topics --zookeeper $ZK\_SERVERS --list | perl -ne 'chomp;print "{\\"topic\\": \\"$\_\\"},\\n"' >> topics-to-move.json && truncate --size=-2 topics-to-move.json && echo '\],"version":1}' >>  topics-to-move.json

cat topics-to-move.json  
{"topics": \[  
{"topic": "my-topic"}\],"version":1}
```
#### Generate a plan for our reassignment
```
kafka-reassign-partitions --zookeeper zoo1:2181 --broker-list "1,2,3" --topics-to-move-json-file topics-to-move.json --generate > full-reassignment-file.json
```
Keep the rollback json file somewhere, just in case. **Heads up,** you will not be able to rollback your plan until your first plan is completely done.
```
cat full-reassignment-file.json | grep version | head -n 1 > rollback.json

cat full-reassignment-file.json | grep version | tail -n 1 > reassignment.json

{  
    "version":1,  
    "partitions":\[ {  
        "topic": "my-topic", "partition": 1, "replicas": **\[1\]**  
    }  
    ,  
    {  
        "topic": "my-topic", "partition": 0, "replicas": **\[3\]**  
    }  
    ,  
    {  
        "topic": "my-topic", "partition": 2, "replicas": **\[2\]**  
    }  
    \]  
}
```
#### Optimize the proposed plan

**_Heads up_**_, Kafka’s kafka-reassign-partitions script is not aware of partitions size, does not limit partition migration between brokers, and does not generate a deterministic plan, so you should not trust it. Just use it as a template and calculate yourself your plan while limiting partitions migrations._

We are going to increase the replication factor (RF) to 3.
```
sed -i 's/\\\[\[1-3\]\\\]/\[1,2,3\]/g' reassignment.json

cat reassignment.json  
{  
    "version":1,  
    "partitions":\[ {  
        "topic": "my-topic", "partition": 1, "replicas": **\[1,2,3\]**  
    }  
    ,  
    {  
        "topic": "my-topic", "partition": 0, "replicas": **\[1,2,3\]**  
    }  
    ,  
    {  
        "topic": "my-topic", "partition": 2, "replicas": **\[1,2,3\]**  
    }  
    \]  
}
```
#### Migrate
```
kafka-reassign-partitions --zookeeper zoo1 --reassignment-json-file reassignment.json **\--execute**
```
#### Monitor and verify
```
kafka-reassign-partitions --zookeeper zoo1 --reassignment-json-file reassignment.json **\--verify**  
Status of partition reassignment:   
Reassignment of partition \[my-topic,0\] completed successfully  
Reassignment of partition \[my-topic,2\] completed successfully  
Reassignment of partition \[my-topic,1\] still in progress
```
While all topics are still in progress, we could see on this the Isr, in-sync replicas, different to replicas
```
root@kafka1:/# kafka-topics --topic my-topic --describe  --zookeeper zoo1  
Topic:my-topic PartitionCount:3 ReplicationFactor:3 Configs:  
 Topic: my-topic Partition: 0 Leader: 1 Replicas: 1,2,3 Isr: 1,3,2  
 Topic: my-topic Partition: 1 Leader: 2 **Replicas**: 1,2,3 **Isr**: 2,3  
 Topic: my-topic Partition: 2 Leader: 3 Replicas: 1,2,3 Isr: 3,2,1
```
### Be safe, not sorry

During partitions reassignment more resources are going to be used, be sure your cluster can handle +20% CPU usage and up to +30% disk.

**Heads up**, while a partition is not entirely migrated, its origin broker will keep the entire copy of this partition. If this broker is receiving another partition, its disk usage can go through the roof!

![](https://cdn-images-1.medium.com/max/800/1*wiZLmuu82AVQKqtxB_NJ6A.png)
![](https://cdn-images-1.medium.com/max/800/1*E-efxXU8PgTlBPbDeXHLdg.png)

**Protips**: It’s smarter to move large topics, topic by topic. The task will last longer, but your cluster’s disks will be safe.

### Future work : Automate this process

At TabMo we currently use Kafka’s scripts and excel sheets, we’ll definitely try these new DataDog’s tools (**EDIT 2019**: we do now 😁), it removes a lot of manual pain points, such as providing you the smartest migration plan limiting partitions migration between brokers and is aware of partitions size.

> `topicmappr` is a drop-in replacement for the Kafka `kafka-reassign-partitions.sh` script `--generate`

[**Introducing Kafka-Kit: Tools for Scaling Kafka**  
_For a company with data in the name, it's no surprise that we ingest large amounts of it. Kafka is our messaging…_www.datadoghq.com](https://www.datadoghq.com/blog/engineering/introducing-kafka-kit-tools-for-scaling-kafka/ "https://www.datadoghq.com/blog/engineering/introducing-kafka-kit-tools-for-scaling-kafka/")[](https://www.datadoghq.com/blog/engineering/introducing-kafka-kit-tools-for-scaling-kafka/)

[**DataDog/kafka-kit**  
_Kafka data mapping and recovery tools. Contribute to DataDog/kafka-kit development by creating an account on GitHub._github.com](https://github.com/DataDog/kafka-kit/tree/master/cmd/topicmappr "https://github.com/DataDog/kafka-kit/tree/master/cmd/topicmappr")[](https://github.com/DataDog/kafka-kit/tree/master/cmd/topicmappr)

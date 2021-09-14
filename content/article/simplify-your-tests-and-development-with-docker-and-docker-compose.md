---
title: 'Simplify your tests and development with Docker and Docker Compose'
description: 'A developer is a computer scientist. And as scientists, it’s our duty to follow a scientific method.'
date: '2020-02-17T14:23:42.730Z'
---
### Scientific method

We tend to forget about it, to be a developer is to be a computer **scientist.** And as scientists, it’s our duty to follow a [**scientific method**](https://en.wikipedia.org/wiki/Scientific_method)**.**

Tech community suffer from a toxic mentality about not testing applications, by business pressure or laziness. In the long run, it makes us wasting a **massive** amount of time, and time is money, [especially when tech companies have a great turnover rate](https://business.linkedin.com/talent-solutions/blog/trends-and-research/2018/the-3-industries-with-the-highest-turnover-rates) as confirmed in the [2019 StackOverflow developer survey](https://insights.stackoverflow.com/survey/2019#work-_-how-long-ago-did-developers-last-change-jobs).

![](https://cdn-images-1.medium.com/max/800/1*QNa4dUoUOxQdBfyT4ykwQQ.png)

It’s a herculean task to take over a project without its original maintainers and without proper tests…

Without reliable applications developers are considered unable to manage a whole projects. So, for some manager, developers are simple technicians who need constant supervision, whereas with a bit of trust earned thanks to **test, documentation, automation, monitoring and communication**, we can make big things happen. This computer **science** is not all about code, and this can be a bit overwhelming…

![](https://cdn-images-1.medium.com/max/800/0*lxCCrgY-Ola2OkLK.jpg)

[😥 http://www.commitstrip.com/en/2017/02/08/where-are-the-tests/](http://www.commitstrip.com/en/2017/02/08/where-are-the-tests/)

Docker and Docker Compose are **tools** to make us more efficient by giving us the possibility to start on our own machine, or somewhere else, any systems in minutes ➡️ **Reproducibility** is a core value of the [scientific method](https://en.wikipedia.org/wiki/Scientific_method)

### My daily tasks as a data engineer

Data engineer is a quite new trend since the Big Data area. I like to call myself a backend engineer specialized in distributed systems. The only difference with a developer is you might spend a bit more time in your database/system config files or documentation, one of my running joke is that I’m not a data engineer but a **configuration engineer.**

I spend most of my days coding, upgrading, or testing open source systems, such as database or message queue to see if they work smoothly together. Also, what I like the most in my job is to help other developers’ to use these systems, that can be new to them, and integrate them to their applications without too much effort **by simplifying the on boarding process.**

### Avoid technical jargon

It’s important to clarify technical words, we often use them without clearly knowing what we are talking about, _sometimes name dropping them to seem smarter than we actually are_, and beginners, _I consider myself a beginner for many, many technologies,_ can be scared and assume :

> This is too difficult for me, I won’t touch it and let it to the pros and I’ll keep my good ol’ 15 line of bash command to update, or not, my system.

#### Containers

We’ve read this word everywhere for now several years. I like to think about containers as **tiny servers** on your computer. It helps me realized that we don’t have to have a proper dev infrastructure on my favorite cloud platform to run tests.
```
docker ps # get all my containers 

$ docker exec -ti my\_container\_name bash # connect to our container

\> ls
```
[You can find 10 useful docker commands here](https://dev.to/aduranil/10-docker-compose-and-docker-commands-that-are-useful-for-active-development-22f9)

Would you rather have at your disposal a remote server where you need to ask permissions to restart a service or play & destroy service on your own machine? I clearly want to have a full control on my test servers without having to disturb others in case something goes wrong (and it will 😄)

#### Docker images

They correspond to the ZIP file I used to download to use a system. You can either use an existing one found on [the Docker hub](https://hub.docker.com/r/confluentinc/cp-kafka/), where you can see configuration details. Or create your own thanks to a [descriptive file containing all instructions an app needs to run](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/)

#### [Docker compose](https://docs.docker.com/compose/) files

We can run a docker images on a container with a `docker run image:version` command, but docker compose gives us more control and a human readable file, _and as human we prefer that_ 😜

> Compose is a tool for defining and running multi-container Docker applications.
```
services:  
  zoo1:  
    image: zookeeper:3.4.9 **\# image name found on the docker hub**  
    ports: # link on computer host with the container host  
      - "2181:2181"  
  kafka1:  
    image: confluentinc/cp-kafka:5.2.2  
    ports:  
      - "9092:9092"  
    environment:**#Config goes here as described on the dockerhub page**  
      KAFKA\_ADVERTISED\_LISTENERS: PLAINTEXT://localhost:9092  
      KAFKA\_LOG4J\_ROOT\_LOGLEVEL: "WARN"  
   volumes: **\# we can link on computer data with the container data**  
      - ./../../src/test/testData:/tmp/data  
    depends\_on:  
      - zoo1
```
These docker-compose file when run with a `docker-compose up` command start 2 services: a [Zookeeper](https://zookeeper.apache.org/), and a [Kafka](https://kafka.apache.org/) in a few seconds ✨

#### It can become data engineers, and even product owners best friend.

![](https://cdn-images-1.medium.com/max/800/0*SwPF8cytRwniuJTe)

Use 11 different systems together can take way to long

**As data engineers**, we have sometimes 11 systems to tests together. And to upgrade these systems, especially with a strict [Service Level Agreement (SLA)](https://en.wikipedia.org/wiki/Service-level_agreement) production system, can be stressful. Docker compose forbids us to be lazy, and we can test several tests scenario with different versions and configuration in no time 😎

**As product owner**, if the development team have a continuous integration systems to publish docker image of their app for each branch, I can validate each change with a Docker (compose) **one liner** found in the readme of the project.

### On boarding

I’ve already heard that Docker Compose commands inside READMEs were great for juniors developers. Well, that’s true, **but it’s also true for experts**. The hardest part of a project is the on-boarding, if I have to install a new technology, I am sure, _because I’ve installed too many_, that I am going to waste 1 hour of my time or more to finally get it right.

![](https://cdn-images-1.medium.com/max/800/0*d8i4v4P50JtnyPEE)

A +2300 stars project from a top company where you have to install Go

If you’re wondering why you have only a few contributors to your project, it might be because **it’s too hard to help you.** Try to imagine yourself as if you had to reinstall everything on your computer tomorrow 😖

### “It works on my container”

Most continuous integrations systems integrates docker image, at TabMo we use GitLab, where we can run end to end and unit tests thanks to [their docker image integration](https://docs.gitlab.com/ee/ci/docker/using_docker_images.html#define-image-and-services-from-gitlab-ciyml)

```
unit\_test:  
  services:  
    - name: postgres:9.3  
      alias: my\_postgres\_hostname  
  stage: test  
  image: `hseeberger/scala-sbt`  
  script:  
    - sbt clean test  
  variables: `POSTGRES_PASSWORD: example`
```

With only a few lines, our CI can start any database or system, here postgres, in a [Cattle VS Pet fashion](http://cloudscaling.com/blog/cloud-computing/the-history-of-pets-vs-cattle/), for our test. Beautiful and convenient.

### Docker-compose receipt projects

Docker is a rich ecosystem, and I’m sure you can find some open source projects that will match your needs. For the kakfa ecosystem I strongly recommend [this repository](https://github.com/simplesteph/kafka-stack-docker-compose) containing lot of examples on how to run kafka with different configurations

![](https://cdn-images-1.medium.com/max/800/0*nRU8w0zf3HCTplGG)

### For production?

The good news is once you’ve learnt how to use Docker and Docker Compose, it’s a baby step to move to [Kubernetes](https://kubernetes.io/) 👍

### Conclusion

With Docker and docker compose, we are not lazy anymore to **test hard things**. It increases project quality and its lifetime: **more tests are written**, because it’s easier, we dare more to refactor code.. and it’s almost **0 effort to get started** with any projects, so **more people can contribute** and it makes the project more resilient and [**pass the bus factor**](https://en.wikipedia.org/wiki/Bus_factor)

---
title: "What I Like About Data Engineering"
draft: false
description: "Why do you do what you do ?"
date: 2018-01-23T16:50:07+02:00
---

I've recently been asked why I chose to specialize in data engineering and what I liked about it.

As a developer, I'm more used to technical questions/articles/tweets based on facts and long hours of development, and it felt actually good to remember **why** I spend some much time reading and developing by answering this question.

**TL;DR:** To build trustworthy analytical dashboards, whereas more data engineers I know seem to enjoy more building systems that scale well

## The beginning
I started to work as front-end dev/technical support in a high-paced advertising start-up (from 50 to 500+ people in a few years), dealing with lot of advertising *openRTB* events such as click, view, complete... And got interested by knowing how the business actually runs and why customers use the platform, [simply because I want my work to make sense to me.](https://www.strikemag.org/bullshit-jobs)

I could notice **trust** was the number 1 reason, beside a wide network of publishers, why customers invest their advertising campaigns. And, dashboards were the key to it. Late, changing, or simply wrong metrics happen and can hurt business badly. And don't think it happens only to others, [even Facebook keeps having "bug" with their ad metrics](https://www.forbes.com/sites/greatspeculations/2016/11/17/more-bugs-found-in-facebooks-ad-metrics-to-the-dismay-of-advertisers/#505ddbfe2a85)

After having to support several cases like metrics discrepancies with remorseless customers, it led me to understand how metrics were calculated, *Hadoop MapReduce, Spark jobs*, where those metrics were stored, *Cassandra, Postgres, Hadoop Distributed File System*, what could we do if something goes wrong, *Lambda/Kappa architecture*, how to send data between services, *Kafka*, and what format should data be, *Avro, Parquet*, **to be sure to provide the best metrics possible that benefit business.**

Thanks to this willingness to learn, another startup trusted me to become their first data engineer. I'll be forever thankful for everything I learned there. *I know I sound cliché 😛*

## My advice to start Data Engineering
Data engineering, is still software development, at the point where I want to call myself more and more software engineer/developer/your favorite words to describe a developer, instead of data engineer.
The only difference is you might spend a bit more time in your database/system config files or documentation, one of my running joke is that I'm not a data engineer but a configuration engineer, so **you don't be afraid to start, you can do it.**

## Learn
You can start today to write your first Spark code using Scala/Java/Python/SQL or R on [Databricks](https://community.cloud.databricks.com/), that provides a notebook platform with a free 6G server to analyze your favorite dataset or use one of their introduction notebooks. Or play with [BigQuery, Google's data warehouse for analytics, to analyse open datasets](https://cloud.google.com/bigquery/public-data/) like [Github.](https://bigquery.cloud.google.com/dataset/bigquery-public-data:github_repos)

## Learn more
Maxime Beauchemin (AirBnb/Lyft) writes beautiful [a](https://medium.freecodecamp.org/the-rise-of-the-data-engineer-91be18f1e603)rticle[s](https://medium.com/@maximebeauchemin/the-downfall-of-the-data-engineer-5bfb701e5d6b) about Data Engineering

I name-dropped a lot of technologies that look fancy and complicate, [Martin Kleppman's Designing data-intense applications](https://martin.kleppmann.com/2015/05/11/please-stop-calling-databases-cp-or-ap.html) book contains everything you need to know about the subject. Remember, deep down it's all about simple config files.


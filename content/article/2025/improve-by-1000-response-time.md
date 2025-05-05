---
title: "Scaling Smart: From 60s to 60ms response time with 0 added costs"
draft: false
description: "Partitionning, caching and materialized views to save cost and improve performance on custom full-scan SQL queries"
date: "2025-05-04T12:50:07+02:00"
thumbnail: "images/2025/from-seconds-to-milliseconds.png"
images:
    - "images/2025/from-seconds-to-milliseconds.png"
---

For the [Ecology Media Observatory](https://observatoiremediaecologie.fr/), a project I’ve been working on for over a year, with features like misinformation detection or being able to deep dive into the observatory's data, I struggled to find time to improve the site’s performance for rare and custom full-scan queries — [especially given a tight infrastructure budget.](https://www.epauler.fr/article/2025/blog-observatoire-des-medias-scaleway/)


## Initial caching strategy using Metabase and Slack
The observatory displays a lot of graphs. And for performance, I've relied on cache for the website's full-scan queries with automatic pre-warm up requests from a slack bot to refresh them.

I implemented this solution pretty quickly thanks to [Metabase persistence model](https://www.metabase.com/docs/latest/data-modeling/model-persistence), and Metabase slack alerts.

It seemed good enough for me, but people in a hurry that customize some full-scan queries, they couldn't use the cache and had to wait about a minute for results, and in today's too fast world this was not acceptable for them. 

A recurring issue when non–data-driven users interact with analytical tools is that they may not grasp the performance impact of certain choices. In our case, the data is partitioned by time, so even a simple date filter could drastically improve query performance. But from a user's perspective, more data often feels like better insight - so they would understandably remove predefined time filters, unaware that this triggered expensive full-scan queries behind the scenes. In exploratory phases where I don't know exactly what I'm looking for, a principle I follow myself is to start with as little data as needed to test a hypothesis and only scale up once the insights are meaningful.

## Vertical scaling wasn’t sustainable
There’s a [popular saying in tech that "a one-second delay can cost you 10% of your users."](https://research.google/blog/speed-matters/) Whether or not that number is exact, it reflects a real truth: users expect speed. As a result, many top engineers run oversized, underutilized servers - burning budget just to keep response times low. CPUs often idle at 1%, but hey, the latency graphs look good.

When we launched the observatory in November 2024, I set up the postgresql node type a bit higher - nothing fancy but the response time was improved. However, databases are expensive, and I couldn’t justify the cost in the long run. So after the launch buzz calmed down, I downgraded the instance to protect our infrastructure budget.

For months, I kept hearing minor complaints in meetings about slowness. Without being able to tackle this performance issue, the use case was too rare, and I had many other priorities. And it was "only" one minute of their time *- and mine sometimes and I use the platform too -* and the trick of the cache works for the majority.

But deep down, my ego was hurt and I knew this wasn’t sustainable either, especially for a project that’s here to last.

## Using materialized views
Eventually, I could find a small window of time to work on this case, and successfully prototyped using Data Build Tool (DBT) to pre-calculate (using [a materialized view](https://docs.getdbt.com/docs/build/materializations#materialized-view)) the first query displayed on the website : a percent of information linked to ecology in media by month.

Thanks to this PoC with automated tests, motivation due to my ego a bit hurt by months of "website being slow" complaints, and helped with the head of data of Quota Climat who identitied a generic root query, we could implement a materialized view on our 25GB of data.

**Result: custom query response times dropped from 60 seconds to 60 milliseconds — a 1000x improvement, with zero additional infrastructure cost.** 

The kind of solution I love: no money thrown at the problem, just smart modeling.

## Thoughts on DBT
DBT has clearly taken over a big slice of the modern data stack.

### ✅ Things I liked about it :
* being able to quickly add seeds for my tests
* the clear command lines without too many options

### ❌ Things I disliked about it :
* **developer experience:** Coming from statically typed languages like Scala, it hurts to write untyped SQL and wait for runtime to catch errors. I know that’s standard in the Python world but I still wish for early error detection. Spark Scala's Dataset API based on Panda's DataFrame succesfully done it years ago by adding type safety :
![SparkSQL Vs Dataframe Vs Dataset](https://www.java-success.com/wp-content/uploads/2018/08/Screen-Shot-2022-02-09-at-9.35.08-pm.png)
* a bit messy to add `pytest`, but i'm glad it works well

Have a look to [my dbt project here](https://github.com/dataforgoodfr/quotaclimat/tree/main/my_dbt_project) to comment or be inspired for your project.

## Conclusion - erooM law for the win
Performance doesn’t always need to mean scaling up and paying more. Sometimes, a deeper understanding of user behavior and smarter modeling is enough. In my case, I used partitioning, caching and pre-calculation with DBT and materialized views : [erooM law for the win.](https://blog.octo.com/la-loi-de-moore-est-morte-et-c%27est-une-bonne-nouvelle)
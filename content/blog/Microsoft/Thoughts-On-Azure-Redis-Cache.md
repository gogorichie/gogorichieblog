---
title: "Thoughts On Azure Redis Cache"
description: ""
date: "2022-08-02T21:46:19-05:00"
thumbnail: ""

tags:
  - "Azure"
  - "Microsoft"


---

![Distributed cache](https://azurecomcdn.azureedge.net/cvt-0575bb7a1cf68c8dbe5697224d85b9818047b8965b5b42e076e5aee4946f7128/images/page/services/cache/distributed-cache.png)

Recently I took some time to revisit my learnings about Azure Redis Cache.

I won't go into detail about what Redis is but you can check out this page about to learn more https://redis.io/docs/about/.

A particular use benefit over using self-hosting is it will allow a business to bring the frequently called data to the cloud so that the data can be called faster with higher availability. This is perfect for situations where you have a frequently queried data source stored within a private network with high latency and an even higher constraint on memory usage from on-prem servers.

![Distributed cache](https://azurecomcdn.azureedge.net/cvt-0575bb7a1cf68c8dbe5697224d85b9818047b8965b5b42e076e5aee4946f7128/images/page/services/cache/distributed-cache.png)

The benefits of using Azure Redis are pretty straightforward it decreases latency during peak usage as the volume of calls grows and is easy to deploy from an infrastructure engineer's perspective. Caching using Azure Redis vs. self-hosted Redis has no impact on Developers as they will be able to call the cache the same way they would call any other cache option. A key feature of the  Azure Redis Cache is as the usage grows the Microsoft Advisor service will identify performance issues and recommend solutions. Another benefit is that by default, Azure Redis Cache is set up as Master-Slave with high availability.

A great place to start to learn more is https://docs.microsoft.com/en-us/azure/azure-cache-for-redis/.
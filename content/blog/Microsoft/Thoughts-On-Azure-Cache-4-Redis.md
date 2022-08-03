---
title: "Thoughts On Azure Cache For Redis"
description: ""
date: "2022-08-02T08:46:19-05:00"
thumbnail: ""

tags:
  - "Azure"
  - "Microsoft"


---

![Distributed cache](https://azurecomcdn.azureedge.net/cvt-0575bb7a1cf68c8dbe5697224d85b9818047b8965b5b42e076e5aee4946f7128/images/page/services/cache/distributed-cache.png)

Recently I took some time to revisit my learnings about Azure Cache for Redis I got first introduced to the service in 2018. I won't go into detail about what Redis is but you can check out this page about it to [learn more](https://redis.io/docs/about/). But instead i want to share my thoughts on using it on the Azure platform.

A particular use benefit over using self-hosting version for data cache needs is it will allow a business to bring the frequently called data to the cloud so that the data can be called faster with higher availability. This is perfect for situations where you have a frequently queried data source stored within a private network with high latency and an even higher constraint on memory usage from on-prem servers.

Keep things to keep in mind about Azure Cache for Redis:

1. It's easy to deploy from Infrastructure Engineer's perspective it can be deployed through Azure portal or your IaC tool of choice.
2. Caching using Azure Cache for Redis vs. self-hosted Redis has no impact on Developers as they will be able to call the cache the same way they would call any other cache option.
3. Using Redis modules are still possible on the [Enterprise tiers](https://docs.microsoft.com/en-us/azure/azure-cache-for-redis/cache-overview#service-tiers).
4. Logging and Recommendations through Log Analytics Workspaces. A key feature of the Azure Cache for Redis highlighted in its documentation is as the usage grows the Microsoft Advisor service will identify performance issues and recommend solutions.
5. Cache can opportunity private link service to allow for network isolation.

A great place to learn more is https://docs.microsoft.com/en-us/azure/azure-cache-for-redis/.
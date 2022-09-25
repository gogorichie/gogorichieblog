---
title: "Thoughts On Azure Cache For Redis"
description: ""
date: "2022-08-03T08:46:19-05:00"
thumbnail: ""

tags:
  - "Azure"
  - "Microsoft"


---


Recently I took some time to revisit Azure Cache for Redis I got first introduced to the service in 2018 and a lot has changed since then. I won’t go into detail about [Redis](https://redis.io/docs/about/) and what it is or What is [caching](https://azure.microsoft.com/en-us/resources/cloud-computing-dictionary/what-is-caching/#overview). But instead, I want to share my thoughts on using it on the Azure platform.

A particular use benefit of using Azure Cache for Redis instead of the self-hosting version for data cache needs is it will allow a business to bring the frequently called data to the cloud so that the data can be called faster with higher availability. This is perfect for situations where you have a frequently queried data source stored within a private network with high latency and an even higher constraint on memory usage from on-prem servers.

|![Distributed cache](https://gogorichiesitefiles.blob.core.windows.net/publicfiles/distributed-cache.png)|
|:--:|
| *Architecture design of Azure Cache for Redis implemented for data caching* |

Things to keep in mind about Azure Cache for Redis:

1. It’s easy to deploy from Infrastructure Engineer’s perspective it can be deployed through the Azure portal or your IaC tool of choice supporting deployment via Terraform, BiCep, ARM, etc.
2. Caching using Azure Cache for Redis vs. self-hosted Redis has no impact on Developers as they will be able to call the cache the same way they would call any other cache option.
3. Using Redis modules is still possible on the [Enterprise tiers](https://docs.microsoft.com/en-us/azure/azure-cache-for-redis/cache-overview#service-tiers).
4. Logging and Recommendations are handled through Log Analytics Workspaces. A key feature of the Azure Cache for Redis highlighted in its documentation is as the usage grows the Microsoft Advisor service will identify performance issues and recommend solutions.
5. The Cache can be accessed and can be isolated so it’s hosted in the cloud but not available online when you use Azure Private Link which allows you to privately access services on the Azure platform as well as On-premises and peered networks while protecting against data leakage.

A great place to learn more is https://docs.microsoft.com/en-us/azure/azure-cache-for-redis/.
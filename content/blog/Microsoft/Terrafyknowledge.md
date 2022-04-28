---
title: 'Terrafy Knowledge Share'
description: ''
date: 2022-04-27T22:46:02-05:00
draft: false
categories: []
tags: ["Azure", "microsoft"]
---

*A little disclaimer here these are notes from a demo on 4-28-22 sorry If This Doesn't make sense later.*

**Overview:**

Azure Terrafy is a new tool currently in preview as of April 27th from Microsoft designed to help you export Azure Resources listed within the AzureRM provider to a terraform main.tf file and maintain a state file.

  

**How To Install It:**

1. To be able to install Terrafy you'll need to download the binary from the [github repo](https://github.com/Azure/aztfy). If you haven't installed terrform you'll want to do that as well. [Click here for details](https://learn.hashicorp.com/tutorials/terraform/install-cli)

1. Update the Environment variables.
![Alt](https://gogorichiesitefiles.blob.core.windows.net/publicfiles/envvars.JPG)
1. type "aztfy" in your favorite IDE.
![Alt](https://gogorichiesitefiles.blob.core.windows.net/publicfiles/aztfy.JPG)
  

**User Cases:**

Three use cases that come to mind  where this tool will be  useful.

1. Working with a team that has no experience with IaC and allowing for them to build their ideal enviroment to the required standards before creating a terraform plan that parameterized, templated and applied to other environments
1. Assisting a team with moving to IaC that may have hundreds of existing resources that might need to managed as Code going forward.
1. Extracting the complex resource configurations such SQL MI or VM Scale Sets.
  

**Demo:**

*I did a live demo here*


**Userful Links:**

Here are some useful links.

A: [Azure Terrafy and AzAPI Terraform Provider Previews Announcement](https://techcommunity.microsoft.com/t5/azure-tools-blog/announcing-azure-terrafy-and-azapi-terraform-provider-previews/ba-p/3270937).

B: [Azure Terrafy Repo](https://github.com/Azure/aztfy).

C: [Terrafy Presentation](https://azure.github.io/aztfy/).

D: [Azure Terraform Documentation](https://docs.microsoft.com/en-us/azure/developer/terraform/).
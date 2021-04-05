---
layout: post
title: Moving my blog and getting to grips with Bicep!
categories: [Infrastructure as Code, ARM, Bicep, Azure, Microsoft, DevOps, Blog]
excerpt: "Inspired by a recent presentation by Chris Reddington at the Limerick DotNet Azure User Group, I have decided to move this blog from GitHub Pages and Jekyll to an Azure Storage Account and Hugo based deployment. I'll be making use of GitHub Actions to implement a CI/CD workflow for my blog."
---

Inspired by a recent presentation by Chris Reddington ([@reddobowen](https://twitter.com/reddobowen){:target="_blank"}) at the Limerick DotNet Azure User Group, I have decided to move this blog from GitHub Pages and Jekyll to an Azure Storage Account and Hugo based deployment. I'll be making use of GitHub Actions to implement a CI/CD workflow for my blog. Chris' session was called "How GitHub Actions can help in planning, building, and deploying a Static Website and more". If you want to catch the recording, you can find it on the [Community](/community){:target="_blank"} page under 'Past Events'.

I'll also be using this as an opportunity to get to grips with Bicep, the new deployment language for Azure Resource Manager.

### What is Bicep?

> "Bicep is a Domain Specific Language (DSL) for deploying Azure resources declaritively. It aims to drastically simplify the authoring experience with a cleaner syntax, improved type safety, and better support for modularity and code re-use."
>
> -- <cite>Excerpt taken from the Bicep Github Page.</cite>

I've been getting to know Bicep for a few weeks now and, so far, it does seem a lot simpler that ARM Templates. In my opinon, ARM templates are generally unpleasant to deal with. To date, Bicep is certainly easier to deal with and is also much shorter in terms of lines of code. For example, a simple Virtual Network with two Subnets deployment has about 60 lines of code as an ARM Template whereas the Bicep version has about 30-35 lines of code.

I encourage you to check it out for yourself. You can use the links below to get up to speed.

* [Bicep GitHub Repo](https://github.com/Azure/bicep){:target="_blank"} - Great place to start getting to know Bicep.
* [Bicep Tutorial](https://github.com/Azure/bicep/blob/main/docs/tutorial/01-simple-template.md){:target="_blank"} - Quick tutorial to get you started.
* [Bicep Playground](https://bicepdemo.z22.web.core.windows.net/){:target="_blank"} - Side by Side comparisons of Bicep and ARM Templates.

I'll be using Bicep to deploy the Azure resources required to run this blog. I'll be taking advantage of Bicep's modularity to make the code as readable and re-usable as possible. As you will see later, we will start out with a 'main.bicep' file which will then call the various components required to build out the platform.

### What is GitHub Actions?


### What is Hugo?


### The ask and the Why?

Talk about decsions made and why.


### The infrastructure


### The Workflow

Flow Diagram for workflow with explanations

Thanks for reading!

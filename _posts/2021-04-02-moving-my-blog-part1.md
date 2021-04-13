---
layout: post
title: Moving my blog (Part 1) and getting to grips with Bicep!
categories: [Infrastructure as Code, ARM, Bicep, Azure, Microsoft, DevOps, Blog, Hugo, GitHub Actions]
excerpt: "Inspired by a recent presentation by Chris Reddington at the Limerick DotNet Azure User Group, I have made the decision to move this blog from GitHub Pages and Jekyll to an Azure Storage and Hugo based deployment. I will also be making use of GitHub Actions to implement a CI/CD workflow for my blog."
---

Inspired by a recent presentation by Chris Reddington ([@reddobowen](https://twitter.com/reddobowen){:target="_blank"}) at the Limerick DotNet Azure User Group, I have made the decision to move this blog from GitHub Pages and Jekyll to an Azure Storage and Hugo based deployment. I will also be making use of GitHub Actions to implement a CI/CD workflow for my blog. Chris' session was called "How GitHub Actions can help in planning, building, and deploying a Static Website and more". If you want to catch the recording, you can find it on the [Community](/community){:target="_blank"} page under 'Past Events'.

I'll also be using this as an opportunity to get to grips with Bicep, the new deployment language for Azure Resource Manager.

In this article (Part 1), I'll be focusing on how I am using Azure Storage and Azure CDN to build a blog platform as well as the Bicep files used to deploy and maintain the Azure resources. In Part 2, I'll go into detail on incorporating this infrastructure as code into a CI/CD workflow as well as information on the process of writing a new blog article or making changes to the site.

### What is Bicep?

> "Bicep is a Domain Specific Language (DSL) for deploying Azure resources declaritively. It aims to drastically simplify the authoring experience with a cleaner syntax, improved type safety, and better support for modularity and code re-use."
>
> -- <cite>Bicep Github Page.</cite>

I've been getting to know Bicep for a few weeks now and, so far, it does seem a lot simpler that ARM Templates. In my opinon, ARM templates can be quite intimidating to work with. To date, Bicep is certainly easier to deal with and is also much shorter in terms of lines of code. For example, a simple Virtual Network with two Subnets deployment has about 60 lines of code as an ARM Template whereas the Bicep version has about 30-35 lines of code.

I encourage you to check it out for yourself. You can use the links below to get up to speed.

* [Bicep GitHub Repo](https://github.com/Azure/bicep){:target="_blank"} - Great place to start getting to know Bicep.
* [Bicep Tutorial](https://github.com/Azure/bicep/blob/main/docs/tutorial/01-simple-template.md){:target="_blank"} - Quick tutorial to get you started.
* [Bicep Playground](https://bicepdemo.z22.web.core.windows.net/){:target="_blank"} - Side by Side comparisons of Bicep and ARM Templates.

I'll be using Bicep to deploy the Azure resources required to run this blog. I'll be taking advantage of Bicep's modularity to make the code as readable and re-usable as possible. As you will see later, we will start out with a 'main.bicep' file which will then call the various components required to build out the platform.

### What is 'GitHub Actions'?

GitHub Actions is a service from GitHub which is similar to Azure Pipelines (Azure DevOps). It allows you to create automated and customisable workflows for your code. I'll be using the process of moving my blog to get more familiar with the capabilities of GitHub Actions.

If you want to learn more you can check out the resources below:

* [GitHub Docs](https://docs.github.com/en/actions){:target="_blank"} - I recommend starting with the GitHub Actions section of the GitHub Docs. You'll find plenty of guides and quickstarts here to get you up to speed.
* [GitHub Learning Lab](https://lab.github.com/search?q=github+actions){:target="_blank"} - If you want to take a more hands on approach, you can check out the GitHub Learning Lab which has courses to walk you through various GitHub Actions related scenarios.

I'll be talking more about GitHub Actions in Part 2 of this series.

### What is Hugo?

Hugo is an open-source static site generator written in Go. The blurb on the [gohugo.io](https://gohugo.io/){:target="_blank"} website says that it is "The world’s fastest framework for building websites".

You can find out more about Hugo using the links below:

* [GoHugo.io Website](https://gohugo.io/){:target="_blank"}
* [Hugo GitHub Repo](https://github.com/gohugoio/hugo){:target="_blank"}
* [Hugo Docs](https://gohugo.io/getting-started/){:target="_blank"}

I don't need much in the way of fancy web frameworks or dynamic content delivery for my blog so a static site generator fits perfectly. It allows me to contribute to the community without having to worry about my lack of web development skills. It also allows me to write my articles in Markdown instead of HTML, which makes life a lot easier. At a high level, Hugo will take my Markdown files convert them to HTML and output a set of static HTML files to a 'Public' directory on my machine (or build agent as you'll see in Part 2). I can then upload these files directly to my Azure Storage container to publish them to my site.

There are other static site generators available, such as Jekyll (which I am moving from) and Gatsby to name just two. If you want to know more about choosing the best one for your needs, you can check out [this](https://www.netlify.com/blog/2020/04/14/what-is-a-static-site-generator-and-3-ways-to-find-the-best-one/){:target="_blank"} article on Netlify. It goes into detail on things to think about when choosing a static site generator.

I chose Hugo for a number of reasons. Firstly, it is open-source and I enjoy using open-source technology where possible. Developing your product in the open is a great way to gain trust and build a community. It's also great for building secure and stable applications as your project can benefit from a global community of contributors. Secondly, Hugo is used by a number of other community members with great success. Checkout the [CloudFamily](https://cloudfamily.info/){:target="_blank"} or the [CloudwithChris](https://www.cloudwithchris.com/){:target="_blank"} websites as two examples.

### The ask and the Why?

Talk about decsions made and why.


### The infrastructure


### The Workflow

Flow Diagram for workflow with explanations

Thanks for reading!

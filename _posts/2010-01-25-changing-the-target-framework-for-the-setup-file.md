---
toc: false
id: 1167
title: Changing the target framework for the setup file
date: 2010-01-25T14:36:49+00:00
author: Ajay Matharu
layout: post
guid: https://www.ajaymatharu.com/?p=1167
permalink: /changing-the-target-framework-for-the-setup-file/
aktt_notify_twitter:
  - no
dsq_thread_id:
  - 465385947
categories:
  - .Net
  - Setup
  - Visual Studio
tags:
  - .net framework
  - application project
  - Change target framework
  - deployment project
  - Framework
  - framework version
  - microsoft net framework
  - Setup for Framework v2.0
  - Setup Project
  - Target Framework
  - vs.net
  - windows application
---
One of my team member, <a href="https://kunalsidhpura.wordpress.com" target="_blank">kunal</a>, was facing a problem while creating the setup project for v 20 using VS 2008. Even after just changing the target framework while creating the project did no help so had to search for the solution, and the solution that solved our problem is as follows,

**1) Create a windows application project with target framework as v2.0**

 ****

<div style="width: 692px" class="wp-caption aligncenter">
  <strong><strong><img title="Select Framework" src="https://ajaymatharu.wordpress.com/files/2009/05/1selectframework.png" alt="Select Target Framework" width="682" height="313" /></strong></strong>
  
  <p class="wp-caption-text">
    Select Target Framework
  </p>
</div>

 ****

**2) Create Setup and deployment project and select target framework as v2.0**

 ****

<div style="width: 691px" class="wp-caption aligncenter">
  <strong><strong><img title="Target framework for setup" src="https://ajaymatharu.wordpress.com/files/2009/05/2setupframework.png" alt="Target Framework for Setup" width="681" height="463" /></strong></strong>
  
  <p class="wp-caption-text">
    Target Framework for Setup
  </p>
</div>

 ****

**3) Right-Click on setup project Name and select Properties, under properties select Prerequisites
  
** 

 ****

<div style="width: 565px" class="wp-caption aligncenter">
  <strong><strong><img title="select prerequisite" src="https://ajaymatharu.wordpress.com/files/2009/05/4prerequisite.png" alt="Select Prerequisite" width="555" height="440" /></strong></strong>
  
  <p class="wp-caption-text">
    Select Prerequistes
  </p>
</div>

 ****

**4) Check .NET framework 2.0 and uncheck .NET framework 3.5**

 ****

<div style="width: 512px" class="wp-caption aligncenter">
  <strong><strong><img title="Select framework in prerequisite" src="https://ajaymatharu.wordpress.com/files/2009/05/5selectprerequisite.png" alt="Select Framework in Prerequisite" width="502" height="395" /></strong></strong>
  
  <p class="wp-caption-text">
    Select Framework in Prerequisite
  </p>
</div>

 ****

**5) Under Solution Explorer double click on Microsoft.NET framework under**

 **Setup project.**

 ****

<div style="width: 267px" class="wp-caption aligncenter">
  <strong><strong><img title="Select Framework" src="https://ajaymatharu.wordpress.com/files/2009/05/6framework.png" alt="Select the Framwork to change the version" width="257" height="226" /></strong></strong>
  
  <p class="wp-caption-text">
    Select the Framwork to change the version
  </p>
</div>

 ****

**6) Right-Click on .NET framework select properties and change the version to v2.0&#8230;**

 ****

<div style="width: 786px" class="wp-caption aligncenter">
  <strong><strong><img title="Framework Version" src="https://ajaymatharu.wordpress.com/files/2009/05/8changeversion.png" alt="Change Framework Version" width="776" height="483" /></strong></strong>
  
  <p class="wp-caption-text">
    Change Framework Version
  </p>
</div>

 ****

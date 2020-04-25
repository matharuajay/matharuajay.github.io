---
toc: false
id: 445
title: '&#8220;content encoding error&#8221; while using blogengine.net'
date: 2008-11-13T16:07:42+00:00
author: Ajay Matharu
layout: post
guid: https://ajaymatharu.wordpress.com/?p=445
permalink: /content-encoding-error-when-using-blogenginenet/
ljID:
  - 90
dsq_thread_id:
  - 465358352
categories:
  - .Net
  - ASP.Net
  - Development
  - Firefox
  - Visual Studio
tags:
  - .Net
  - ASP.Net
  - blogengine
  - blogengine.net
  - CompressionModule
  - content encoding error
---
While using BlogEngine.net you may run into &#8220;content encoding error&#8221; “The page you are trying to view cannot be shown because it uses an invalid or unsupported form of compression” this error, to resolve this, find

<add name=&#8221;CompressionModule&#8221; type=&#8221;BlogEngine.Core.Web.HttpModules.CompressionModule, BlogEngine.Core&#8221;/>

in your web.config file and comment this line of code. This error mostly arrives when you host blogengine.net site on GoDaddy.

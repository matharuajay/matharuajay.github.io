---
toc: false
id: 276
title: 'Debugging asp.net web application &#8211; Tip of week #9'
date: 2008-11-17T03:29:11+00:00
author: Ajay Matharu
layout: post
guid: http://ajaymatharu.wordpress.com/?p=276
permalink: /debugging-aspnet-web-application-tip-of-week-9/
ljID:
  - 93
dsq_thread_id:
  - 465358109
categories:
  - .Net
  - Tip of Week
  - Visual Studio
tags:
  - .Net
  - Tip of Week
  - Visual Studio tips
  - vs.net
---
Hi, Many a times we find it difficult to debug big applications. If we run the application it takes too much time to build and then run the application. Also at times it becomes difficult when you have to debug a code and you can not run the application because some other part of code is errorneous. How to debug the application or code in this scenario?

You can open the page in the browser by right click on the page in the IDE &#8211; View in browser or directly open the page in the browser by URL.

Go to IDE &#8211; Tools &#8211; Attatch to process or (ctrl + alt + P)

[<img class="aligncenter size-full wp-image-277" title="attach" src="http://ajaymatharu.files.wordpress.com/2008/10/attach.png" alt="" width="450" height="286" />](http://ajaymatharu.files.wordpress.com/2008/10/attach.png)

check on both the check boxes at the bottom and select the process W3WP in Windows Server 2003 and ASPNETWP in Windows XP and Windows server 2000.

Refresh the page the breakpoint will hit and you can debug the application

---
toc: false
id: 2059
title: module was built either with optimizations enabled or without debug information
date: 2010-10-20T07:13:27+00:00
author: Ajay Matharu
layout: post
guid: http://www.ajaymatharu.com/?p=2059
permalink: /module-was-built-either-with-optimizations-enabled-or-without-debug-information/
aktt_notify_twitter:
  - no
wysiwyg:
  - 'a:2:{s:18:"plain_text_editing";s:0:"";s:13:"post_modified";s:19:"2010-10-20 07:13:27";}'
dsq_thread_id:
  - 465388972
categories:
  - .Net
  - ASP.Net
  - Visual Studio
tags:
  - error in debugging .net
  - error in debugging vs.net
  - mapping of dll in GAC
  - optimization enabled
  - problem while debugging
---
> <div>
>   The following module was built either with optimizations enabled or without debug information
> </div>

When you get the above error you can resolve it by the following way, Tools &#8211;> Options &#8211;> Debugging &#8211;> General &#8211;> Enable Just my code (Managed only) &#8211;> un check "Warn if no user code on launch"&nbsp;

I encountered this problem in Visual Studio 2008 and like others here, my project settings did not have optimizations enabled and debugging information was configured. My problem turned out to be that the project assemblies stored in the GAC were from an older build. I think when I started debugging, VS tried to map between the GAC assemblies and the new source and could not do so and threw up this message. Deleting my old assemblies from the GAC resolved my issue.

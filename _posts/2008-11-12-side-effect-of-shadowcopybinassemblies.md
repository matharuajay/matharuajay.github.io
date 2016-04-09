---
id: 441
title: Side effect of shadowCopyBinAssemblies in web.config
date: 2008-11-12T15:17:52+00:00
author: Ajay Matharu
layout: post
guid: http://ajaymatharu.wordpress.com/?p=441
permalink: /side-effect-of-shadowcopybinassemblies/
ljID:
  - 89
dsq_thread_id:
  - 465364544
categories:
  - .Net
  - ASP.Net
  - Development
  - Visual Studio
tags:
  - .Net
  - ASP.Net
  - shadowCopyBinAssemblies
  - vs.net
  - web.config
---
Today while developing I ran into the problem saying something like _&#8220;the assembly exists at two location&#8221;_. I, normally used to solve this problem by deleting the files from _&#8220;Temporary ASP.NET Files&#8221;_, but this error started to appear too often. So I googled on this error and found someone saying you need to put the following code of line in web.config file if you are running accross this error too often,

_<hostingEnvironment shadowCopyBinAssemblies=&#8221;false&#8221; />_

_hostingEnvironment  :_ Defines configuration settings that control the behavior of the application hosting environment.

_shadowCopyBinAssemblies :_ Optional <span><span class="input">Boolean</span></span> attribute. Sets a Boolean value indicating whether the assemblies of an application in the Bin directory are shadow copied to the application&#8217;s ASP.NET Temporary Files directory.

After placing this part of code in my web.config file, I got rid of the above problem, But I came accross another one which irritated me more. As my application had multiple projects, I frequently have to make changes in one of those, build it and then again add the refrence to my web application.

But after placing this line in my web.config I was not able to remove the previously added reference. When I tried to add reference to new DLL it threw an error something like this _&#8220;cannot delete or modify as file is already is in use by another process. Access denied&#8221;_ . Later when I removed this line from my web.config I was releaved of this error, phew!!!
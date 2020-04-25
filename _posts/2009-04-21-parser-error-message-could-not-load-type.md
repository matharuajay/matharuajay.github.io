---
toc: false
id: 1146
title: 'Parser Error Message: Could not load type'
date: 2009-04-21T15:43:35+00:00
author: Ajay Matharu
layout: post
guid: http://www.ajaymatharu.com/?p=1146
permalink: /parser-error-message-could-not-load-type/
aktt_notify_twitter:
  - no
ljID:
  - 221
dsq_thread_id:
  - 465390694
categories:
  - .Net
  - ASP.Net
  - Visual Studio
tags:
  - .Net
  - ASP.Net
  - bin directory
  - could not load type
  - Error
  - error message
  - global assembly
  - page directive
  - Parser Error Message
  - source error
  - Technology
  - using visual studio
  - Visual Studio
  - vs.net
  - web application
---
>  <span style="font-family: Tahoma; color: #000080; font-size: x-small;"></span>

Source Error:

Line 1: <%@ Application Codebehind=&#8221;Global.asax.cs&#8221; Inherits=&#8221;Global'&#8221; %>

This error occurs when you create a new web application in asp.net using visual studio.net and without compiling the application, you try to browse a page in the application.

This occurs because of the Application DLL not having been formed.

asp.net will look in the Global Assembly Cache, and then in the application&#8217;s local bin directory. If it can&#8217;t find the class with the name you specified then it won&#8217;t load. When you do a codebehind file in Visual studio, you are writing a base class for your aspx file to inherit from &#8211; the HTML template you write in the aspx is inlined into the dynamically generated subclass&#8217;s Render method.

Even if you don&#8217;t put any code in your page, you still need to compile it as long as you put the Inherts Global in your Page directive.

To resolve this, Built the application using Ctrl + Shift + B or use F5 to build the application and then try to browse the application. The error will be resolved.

---
id: 458
title: Server Application Unavailable
date: 2010-04-22T10:15:51+00:00
author: Ajay Matharu
layout: post
guid: http://ajaymatharu.wordpress.com/?p=458
permalink: /server-application-unavailable/
bte_opp_original_pub_date:
  - 2008-11-17 12:10:27
aktt_notify_twitter:
  - no
dsq_thread_id:
  - 465388013
categories:
  - .Net
  - ASP.Net
  - Development
tags:
  - .Net
  - ASP.Net
  - asp.net 1.1
  - asp.net 1.1 server error
  - IIS
  - server unavailable
  - Virtual Directory Error
  - vs.net
---
Many a time while developing a web application you may come accross &#8220;Server application unavailable&#8221;

[<img class="aligncenter size-full wp-image-463" title="unavailable2" src="http://ajaymatharu.files.wordpress.com/2008/11/unavailable2.jpg" alt="unavailable2" width="500" height="284" />](http://ajaymatharu.files.wordpress.com/2008/11/unavailable2.jpg)

When you get this error in Windows XP make sure you have given ASPNET user sufficient rights on your physical application folder, it mainly requires read permission.

When you get this error in Windows 2003 server you can right click your virtual directory &#8211; permission &#8211; grant aspnet user sufficient rights there.

If the above solution doesn&#8217;t work here is another alternative,

You could try editing the Machine.config (located in
  
C:\WINDOWS\Microsoft.NET\Framework\v1.1.4322\CONFI G\).

Look for a key userName=&#8221;machine&#8221;. If you set it to &#8220;SYSTEM&#8221;
  
instead the aspnet_wp.exe runs with a different user (with
  
higher privileges).

Hope this helps
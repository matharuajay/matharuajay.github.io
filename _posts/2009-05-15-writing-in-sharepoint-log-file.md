---
toc: false
id: 1186
title: Writing in Sharepoint log file
date: 2009-05-15T12:21:48+00:00
author: Ajay Matharu
layout: post
guid: http://www.ajaymatharu.com/?p=1186
permalink: /writing-in-sharepoint-log-file/
ljID:
  - 234
dsq_thread_id:
  - 465388648
categories:
  - .Net
  - Development
  - Sharepoint
  - Visual Studio
tags:
  - Sharepoint
  - Sharepoint Log
  - Sharepoint logging
---
Below is an example on how to write to the SharePoint log files (located in C:\Program Files\Common Files\Microsoft Shared\web server extensions\12\LOGS folder).

> <span style="color: #0000a0;">catch(Exception e)<br /> {<br /> Microsoft.Office.Server.Diagnostics.PortalLog.LogString(&#8220;Exception: {0} &#8211; {1}&#8221;, e.Message, e.StackTrace);<br /> }</span>

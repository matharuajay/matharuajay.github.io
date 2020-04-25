---
toc: false
id: 140
title: 'Error creating MySite &#8211; Sharepoint'
date: 2008-09-16T05:39:58+00:00
author: Ajay Matharu
layout: post
guid: http://ajaymatharu.wordpress.com/?p=140
permalink: /error-creating-mysite-sharepoint/
ljID:
  - 25
dsq_thread_id:
  - 465388793
categories:
  - Sharepoint
  - Technical
tags:
  - Sharepoint
  - Technical
---
While creating MySite today, i encountered the following error,

HTTP/1.1 404
  
Connection: close
  
Date; Tue, 16 Sep 2008 05:04:43 GMT
  
Server: Microsoft-IIS/6.0
  
MicrosoftSharepointTeamServices: 12.0.0.6219
  
X-Powered-By: ASP.NET

This error occurs because the SharedService is not properly configured. You can resolve this error by correcting the SharedService or by creating a new SharedService for this site from Central Admin.

I just created a new SharedService from the Central Admin and associated this site with that SharedService and MySite was created <img src="http://www.ajaymatharu.com/wp-includes/images/smilies/simple-smile.png" alt=":-)" class="wp-smiley" style="height: 1em; max-height: 1em;" />

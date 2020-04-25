---
toc: false
id: 136
title: Error Creating Sharepoint Site
date: 2008-09-16T05:23:50+00:00
author: Ajay Matharu
layout: post
guid: https://ajaymatharu.wordpress.com/?p=136
permalink: /error-creating-sharepoint-site/
ljID:
  - 24
dsq_thread_id:
  - 465380387
categories:
  - Sharepoint
  - Technical
tags:
  - Sharepoint
  - Technical
---
Today I was working on creating a new sharepoint site, and after creating the site from the central admin, I got the following error:

HTTP/1.1 404
  
Connection: close
  
Date: Tue, 16 Sep 2008 05:09:29 GMT
  
Server: Microsoft-IIS/6.0
  
X-Powered-By: ASP.NET
  
MicrosoftSharePointTeamServices: 12.0.0.6219

I searched on the error and found the following solution, so just wanted to
  
share the solution with you guys.

Make sure you reset the IIS after creating the site in central admin. Run the following command
  
to reset IIS &#8220;IISRESET /NOFORCE&#8221;

After resetting the IIS run the following command

<p align="left">
  <span><span style="font-family:Calibri;"><span style="font-size:small;">&#8220;C:\PROGRAM FILES\COMMON FILES\MICROSOFT SHARED\WEB SERVER EXTENSIONS\12\BIN\STSADM.exe&#8221; -O CREATESITE -URL </span><a title="https://servername" href="https://servername/"><span style="font-size:small;">https://<em>servername</em></span></a><span style="font-size:small;"><em> </em><span> </span>-OWNEREMAIL <em><e-mail></em> -OWNERLOGIN <em><domain\username></em></span></span></span>
</p>

<p align="left">
  You can get more details on this command using the following command,
</p>

<p align="left">
  <span><span style="font-size:small;"><span><span style="font-family:Calibri;">C:\PROGRAM FILES\COMMON FILES\MICROSOFT SHARED\WEB SERVER EXTENSIONS\12\BIN\STSADM.exe</span></span> -help CreateSite</span></span>
</p>

<p align="left">
  After executing this command you can access your site. You will be asked for the site template to be applied to the site and also the members that will be able to access the site.
</p>

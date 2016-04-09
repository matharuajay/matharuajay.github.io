---
id: 1632
title: Add another application as child of BlogEngine.net
date: 2009-08-28T23:48:52+00:00
author: Ajay Matharu
layout: post
guid: http://www.ajaymatharu.com/?p=1632
permalink: /add-another-application-as-child-of-blogengine-net/
dsq_thread_id:
  - 465393227
categories:
  - .Net
  - ASP.Net
  - Development
  - Visual Studio
tags:
  - .Net
  - ASP.Net
  - BE
  - Blog
  - Blog Engine
  - blogengine
  - blogengine.net
  - Code
  - Microsoft
  - Visual Studio
  - VS
  - vs.net
---
I have been getting good response for my post <a href="http://www.ajaymatharu.com/integrating-blogengine-into-an-existing-site/" target="_blank">Integrating blog engine into existing site</a>. One of the guy asked me this question on how can we do the opposite? He had a BlogEngine as parent site and needed some other site to be child of BlogEngine. So He posted on that and this is the answer he got for his question.

You need to make this change in your web.config file. If you want to have a website as child of BlogEngine

<pre name="code" class="xml"><strong>&lt;location path="." inheritInChildApplications="false"&gt;</strong>
 &lt;system.web&gt;
 ..... existing content .....
 &lt;/system.web&gt;
<strong>&lt;/location&gt;</strong>

<strong>&lt;location path="." inheritInChildApplications="false"&gt;</strong>
 &lt;system.webServer&gt;
 ..... existing content .....
 &lt;/system.webServer&gt;
<strong>&lt;/location&gt;</strong></pre>
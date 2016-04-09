---
id: 1208
title: Launch application from javascript
date: 2009-05-12T17:02:28+00:00
author: Ajay Matharu
layout: post
guid: http://www.ajaymatharu.com/?p=1208
permalink: /launch-application-from-javascript/
ljID:
  - 231
dsq_thread_id:
  - 465387186
categories:
  - HTML
  - Internet Explorer
  - Javascript
  - Web
tags:
  - Application from web
  - Browsers
  - Firefox
  - Internet
  - Javascript
  - Launch
  - Web
---
Following is the code that will launch a command prompt on the client machine when you click on the link. This code runs only on Internet Explorer. I&#8217;ll shortly write code for Firefox and other browsers as well. So stay tuned.

This is the javascript code that will launch the application

<pre class="jscript" name="code"></pre>

To call this code in your HTML use,

<pre class="html" name="code"><a href="javascript:StartThis('cmd.exe')">Start explorer</a>
</pre>
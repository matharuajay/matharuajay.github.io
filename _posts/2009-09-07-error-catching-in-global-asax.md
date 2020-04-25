---
toc: false
id: 1635
title: Error catching in Global.asax
date: 2009-09-07T09:53:22+00:00
author: Ajay Matharu
layout: post
guid: https://www.ajaymatharu.com/?p=1635
permalink: /error-catching-in-global-asax/
dsq_thread_id:
  - 465392190
categories:
  - .Net
  - ASP.Net
  - Development
  - Visual Studio
tags:
  - .Net
  - ASP.Net
  - code snippet
  - custom error
  - Dot Net
  - error handling
  - global.asax
  - httpcontext
  - visual studio.net
  - web.config
---
The following code snippet will help you to catch an error in the global.asax file,

Turn off the custom error mode in web.config file first,

<pre name="code" class="xml">&lt;customErrors mode="Off"&gt;</pre>

And add this code in your global.asax file to catch the error,

<pre name="code" class="c#">void Application_Error(object sender, EventArgs e)
 {
 HttpContext context = ((HttpApplication)sender).Context;
 if (context.Error != null)
 {
 Exception ex = context.Error;
 string msg = string.Empty;

 while (ex != null)
 {
 if (!string.IsNullOrEmpty(ex.Message))
 msg += ex.ToString() + "&lt;br /&gt;&lt;br /&gt;";
 ex = ex.InnerException;
 }
 context.Response.Clear();
 context.Response.Write(msg);
 context.Response.End();
 }
 } </pre>

Hope this helps <img src="https://www.ajaymatharu.com/wp-includes/images/smilies/simple-smile.png" alt=":)" class="wp-smiley" style="height: 1em; max-height: 1em;" />

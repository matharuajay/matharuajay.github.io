---
id: 1980
title: ASP.Net menu control not working in Google Chrome
date: 2010-01-06T13:01:40+00:00
author: Ajay Matharu
layout: post
guid: http://www.ajaymatharu.com/?p=1980
permalink: /asp-net-menu-control-not-working-in-google-chrome/
aktt_notify_twitter:
  - yes
dsq_thread_id:
  - 465386341
categories:
  - .Net
  - ASP.Net
  - Chrome
  - Internet Explorer
tags:
  - asp.net menu control
  - asp.net menu control in chrome
  - asp.net menu control not working
  - asp.net menu not working
  - asp.net menu not working in chrome
---
ASP.Net menu controls breaks in Google Chrome and works fine in other browsers. Here is the hack to make it work in Google Chrome as well,

<pre name="code" language="c#">if (Request.UserAgent.IndexOf("AppleWebKit") &gt; 0)
     Request.Browser.Adapters.Clear();
</pre>

Just add this code on your page load and the menu control will start working fine in Google Chrome as well.

Also some times the hover menus don&#8217;t work on IE8 to make it work on IE8 you need to set
  


## &#8220;z-index&#8221;

in DynamicMenuStyle property of the menu control.

Hope this helps <img src="http://www.ajaymatharu.com/wp-includes/images/smilies/simple-smile.png" alt=":)" class="wp-smiley" style="height: 1em; max-height: 1em;" />
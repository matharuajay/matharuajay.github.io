---
id: 436
title: Firefox not displaying WMV video?
date: 2008-11-11T04:20:27+00:00
author: Ajay Matharu
layout: post
guid: http://ajaymatharu.wordpress.com/?p=436
permalink: /firefox-not-displaying-wmv-video/
ljID:
  - 86
dsq_thread_id:
  - 465358312
categories:
  - .Net
  - ASP.Net
  - Firefox
  - Technical
  - Technology
tags:
  - ASP.Net
  - Embed
  - Firefox
---
Last night I have been digging on how to embed wmv file in firefox. I was not able to see the video in firefox although I could see that in IE. Firefox was not displaying the embeded wmv video.

So I tried many ways and finally this one worked for me.

<object id=&#8221;player&#8221;>
  
<param name=&#8221;AutoStart&#8221; value=&#8221;true&#8221;>
  
<param name=&#8221;URL&#8221; value=&#8221;http://www.kita-o.com/news2006/Lew Tabackin.wmv&#8221;>
  
<param name=&#8221;uiMode&#8221; value=&#8221;full&#8221;>
  
<embed src=&#8221;http://www.kita-o.com/news2006/Lew Tabackin.wmv&#8221;name=&#8221;player&#8221; width=&#8221;420&#8243; height=&#8221;366&#8243; type=&#8221;video/x-ms-wmv-plugin&#8221; pluginurl=&#8221;http://www.microsoft.com/windows/windowsmedia&#8221; allowchangedisplaysize=&#8221;1&#8243; autosize=&#8221;1&#8243; displaysize=&#8221;1&#8243; showcontrols=&#8221;1&#8243;showstatusbar=&#8221;1&#8243; autorewind=&#8221;1&#8243; autostart=&#8221;1&#8243;>
  
</embed>
  
</object>
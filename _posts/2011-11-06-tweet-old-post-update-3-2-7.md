---
id: 2663
title: 'TWEET OLD POST &#8211; Update 3.2.7'
date: 2011-11-06T21:09:39+00:00
author: Ajay Matharu
layout: post
guid: http://www.ajaymatharu.com/?p=2663
permalink: /tweet-old-post-update-3-2-7/
dsq_thread_id:
  - 465386949
categories:
  - Plugins
  - wordpress
tags:
  - Tweet Old Post
  - Tweet old post plugin
  - tweet old post wordpress plugin
  - Tweet Old Posts Wordpress Plugin
---
**Tweet old post &#8211; update 3.2.7**

&nbsp;

What&#8217;s new:

**Enable Log** &#8211; I have included this option to log all that happens while posting a post to twitter. Please enable this if something is not working for you. You can try again after enabling log and check the log.txt file under log folder under wp-content/Tweet-Old-Post/log/log.txt. If you are not able to understand or make it work you can mail me the log.txt file at ajay[at]ajaymatharu[dot]com

**Exclude Post** &#8211; Yes, exclude post is back in this version. I have worked on the vulnerability issue and resolved that in this version.

**Misc** &#8211; Some other bug fixes and optimization. Tried to resolve the issue of nothing happens when you click to authorize twitter account with plugin.

&nbsp;

There were some other options that were confusing here is the explanation for those,

**Use Inline Hashtags** &#8211; If checked it looks for hashtags (from tags/categories/custom field/common) within the tweet content, if found it replaces that word with hashtag. If not checked hashtag will be added at end of tweet.

**Maximum Hashtag Length** &#8211; Specifies maximum number of character hashtags can contain. This is included to calculate the tweet length. e.g. Suppose you have set this to 30, if your post&#8217;s total hashtags character length is more than 60 it will it will trim it to 30 character to include those in tweet. This is to include more content in your tweet than hashtags. If you set this to 0 it will post all the hashtags reducing the size of your tweet content.

**Random Interval** &#8211; its an random interval which is added to minimum interval. e.g. if you have set the minimum interval to 4 hours and random interval to 4 hours the next post may happen at 4 hours 28 mins or 4 hours 58 mins. This option adds some additional time interval to minimum time interval.

&nbsp;

You can download the latest plugin from <a title="Tweet Old Post Download Link" href="http://wordpress.org/extend/plugins/tweet-old-post/" target="_blank">WordPress</a>
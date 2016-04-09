---
id: 2602
title: How to prevent image from caching in javascript
date: 2011-02-24T22:01:35+00:00
author: Ajay Matharu
layout: post
guid: http://www.ajaymatharu.com/?p=2602
permalink: /how-to-prevent-image-from-caching-in-javascript/
dsq_thread_id:
  - 465379184
categories:
  - Browsers
  - Javascript
  - JQuery
  - Technology
  - Web
tags:
  - Clear image cache in browser
  - Image Cache in browser
  - Image Caching
  - Image caching in Javascript
  - javascript code to clear image cache in browser
  - Javascript code to prevent image caching
  - Javascript to prevent image cache
  - Prevent image cache
  - Prevent Image Caching
---
Many a times when we replace the image with the same name, browser still picks up the old one. Almost every developer faces this issue, then he asks the person to clear the cache by ctrl + F5 or any other means. But is this the solution?

No, So what can we do in this case? There are two solutions,

1 &#8211; rename the new image and change the image name in code. But for a dot net developer this is pain because he may have to republish the code and send an upload of the dll again. And giving an upload of dll because of change in image is foolishness, ain&#8217;t it?

2 &#8211; Another solution is to write a javascript code so that the browser does not pick up image from the cache and loads it everytime. Following is the sample code of how you can try this,

<pre name="code" class="javascript">document.getElementById('myimg').src = document.getElementById('myimd').src + '?' + (new Date()).getTime();
</pre>

You need to make sure this code runs after page has loaded else, it will give an error if that image tag is not yet rendered.

In JQuery for single image code will be

<pre name="code" class="javascript">$(document).ready(function(){
$("#myimg").attr('src',$(this).src + '?' + (new Date()).getTime());
});
</pre>

For all the images 

<pre name="code" class="javascript">$(document).ready(function(){
jQuery('img').each(function(){
jQuery(this).attr('src',jQuery(this).attr('src')+ '?' + (new Date()).getTime());
});
});
</pre>

Hope this helps. If you have any more idea please share it with us by dropping a comment.
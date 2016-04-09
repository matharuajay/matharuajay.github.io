---
id: 474
title: 'Generating random text &#8211; I'
date: 2008-11-19T17:31:09+00:00
author: Ajay Matharu
layout: post
guid: http://ajaymatharu.wordpress.com/?p=474
permalink: /generating-random-text-i/
ljID:
  - 94
dsq_thread_id:
  - 465386243
categories:
  - Misc
  - Technology
tags:
  - Microsoft
  - Microsoft Office
  - Office
  - Random text
---
This works in any version of Microsoft Word… Just open up a new document, and then type in =rand() into the document:

[<img class="aligncenter size-full wp-image-478" title="texts" src="http://ajaymatharu.files.wordpress.com/2008/11/texts.png" alt="texts" width="645" height="477" />](http://ajaymatharu.files.wordpress.com/2008/11/texts.png)

 

And then hit enter.

Three paragraphs of text will be instantly added…

[<img class="aligncenter size-full wp-image-479" title="text1" src="http://ajaymatharu.files.wordpress.com/2008/11/text1.png" alt="text1" width="660" height="466" />](http://ajaymatharu.files.wordpress.com/2008/11/text1.png)

You can add more than 3 paragraphs by using the following syntax

=rand(paragraphs,sentences)

For instance, for 6 paragraphs of 20 sentences each, you would use:

=rand(6,20)
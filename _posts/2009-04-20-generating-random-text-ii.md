---
id: 476
title: 'Generating random text &#8211; II'
date: 2009-04-20T11:00:15+00:00
author: Ajay Matharu
layout: post
guid: http://ajaymatharu.wordpress.com/?p=476
permalink: /generating-random-text-ii/
aktt_notify_twitter:
  - no
ljID:
  - 219
dsq_thread_id:
  - 465388196
categories:
  - Misc
  - Technology
tags:
  - Microsoft
  - Microsoft Office
  - Office
  - Random text
  - Tips
---
Turns out, in Word 2007 all you have to do is use =lorem() instead of =rand() and you&#8217;ll be able to insert the lorem text instead.

Just type in =lorem() into your document, and hit the enter key…

<img src="http://www.howtogeek.com/wp-content/uploads/2007/09/image99.png" border="0" alt="image" width="605" height="312" />

And just like that, Lorem Ipsum is inserted automatically!

<img src="http://www.howtogeek.com/wp-content/uploads/2007/09/image100.png" border="0" alt="image" width="620" height="404" />

Just like the other tip, you can use the following syntax:

=lorem(paragraphs,sentences)

For instance, for 6 paragraphs of 20 sentences each, you would use:

=lorem(6,20)
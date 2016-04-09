---
id: 1188
title: Simple code to loop through all the textboxes in your page
date: 2009-05-05T10:15:22+00:00
author: Ajay Matharu
layout: post
guid: http://www.ajaymatharu.com/?p=1188
permalink: /simple-code-to-loop-through-all-the-textboxes-in-your-page/
ljID:
  - 228
dsq_thread_id:
  - 465383730
categories:
  - .Net
  - ASP.Net
  - Development
  - Visual Studio
tags:
  - .Net
  - ASP.Net
  - 'C#.Net'
  - Visual Studio
  - vs.net
---
This is the simple code you can use, to loop through all the textboxes in your page. Not only textboxes you can change the textbox in
  
_**&#8220;(ctrl is Textbox)&#8221;**_ to the control you&#8217;ll like to loop in your page.

<pre name="code" class="c-sharp">private  void processTextbox()
{
     foreach (Control ctrl in Page.Controls)
     {
          if (ctrl is TextBox)
          {
              //do something here
          }
          else
          {
              //do something here
          }
     }
}
</pre>

Njoy coding <img src="http://www.ajaymatharu.com/wp-includes/images/smilies/simple-smile.png" alt=":)" class="wp-smiley" style="height: 1em; max-height: 1em;" />
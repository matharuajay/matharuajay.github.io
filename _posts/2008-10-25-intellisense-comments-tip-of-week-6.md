---
toc: false
id: 255
title: 'IntelliSense Comments &#8211; Tip of week #6'
date: 2008-10-25T08:16:05+00:00
author: Ajay Matharu
layout: post
guid: https://ajaymatharu.wordpress.com/?p=255
permalink: /intellisense-comments-tip-of-week-6/
ljID:
  - 48
dsq_thread_id:
  - 465387205
categories:
  - Tip of Week
  - Visual Studio
tags:
  - Tip of Week
  - Visual Studio tips
---
[](https://ajaymatharu.files.wordpress.com/2008/10/intellisense.png)When comments exist for a method or class, they are displayed in the IntelliSense pop up shown in below figure

<img class="aligncenter size-full wp-image-256" title="intellisense" src="https://ajaymatharu.files.wordpress.com/2008/10/intellisense.png" alt="" width="399" height="65" />

<p class="docText">
  These comments can be created a number of different ways. If you are using C#, then these comments are pulled from the XML-based comments in your code, like the following example:
</p>

<pre>/// &lt;summary&gt;

/// This method loads any number of snippets into the toolbox

/// &lt;/summary&gt;

public static void LoadSnippets( )
 
If you have description for the paramerters in you function also, here is the sample

/// &lt;summary&gt;

/// This method loads any number of snippets into the toolbox

/// &lt;/summary&gt;
<span style="color:#008000;"><span style="color:#000000;">
<span style="font-size:x-small;">/// &lt;param name="a"&gt;First number to add&lt;/param&gt;

/// &lt;param name="b"&gt;Second number to add&lt;/param&gt;
</span></span></span>
public static void addNumbers(int a, int b )

IntelliSense is one of the best features of Visual Studio, and using the shortcut keys

 summarized in  below table will allow you to get the most out of this great feature.<a name="visualstudiohks-CHP-2-ITERM-2316"></a>

 

<a href="https://ajaymatharu.files.wordpress.com/2008/10/shortcuttable.png"><img class="aligncenter size-full wp-image-257" title="shortcuttable" src="https://ajaymatharu.files.wordpress.com/2008/10/shortcuttable.png" alt="" width="450" height="65" /></a><a name="visualstudiohks-CHP-2-ITERM-2317"></a></pre>

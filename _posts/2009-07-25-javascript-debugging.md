---
tags: 
  - misc
toc:  false
id: 36
title: Javascript Debugging in Visual Studio
date: 2009-07-25T12:03:34+00:00
author: Ajay Matharu
layout: post
guid: https://ajaymatharu.wordpress.com/?p=36
permalink: /javascript-debugging/
bte_opp_original_pub_date:
  - 2008-08-10 14:31:53
dsq_thread_id:
  - 465386900
categories:
  - Visual Studio
---
<p style="text-align:justify;">
  Many a times people get stuck in solving the Javascript issues just because they are not able to debug the code. Debugging is one of the things which you should be very good at and it also checks your patience.
</p>

<p style="text-align:justify;">
  The latest version of Visual Studio i.e. VS 2008 has inbuilt feature that helps you to debug the javascript code just like any other code behind or server side code. All you need to do is set the breakpoint on the javascript code and the breakpoint will be hit when the code execution reaches that point.
</p>

But this is not possible in VS 2005 so the question arises how to debug Javascript in VS 2005?

<p style="text-align:justify;">
  The answer is simple all you need to do is write &#8220;debugger&#8221; above the line you want the breakpoint to hit. So that means write the word &#8220;debugger&#8221; without double quotes before the breakpoint line in javascript and when that code will be executed an window will popup asking you to choose which debugger you want to use to debug the javascript code and you can select the appropriate debugger to debug the javascript code. And if you have firebug in Firefox than you can debug your javascript in Firebug also it allows you to set the breakpoint in the code the same way as you do in the server side code in VS.net and you can step-in, step-out same way.
</p>

for e.g.

function validate()

{

var a=10;var b =20;

debugger

var c=a+b;

}

In this the breakpoint will hit at &#8220;var c=a+b&#8221;.

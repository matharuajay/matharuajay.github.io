---
id: 921
title: 'Breakpoints &#8211; Tip of Week #19'
date: 2009-02-02T04:48:59+00:00
author: Ajay Matharu
layout: post
guid: http://ajaymatharu.wordpress.com/?p=921
permalink: /breakpoints-tip-of-week-19/
delicious:
  - 's:86:"s:78:"a:3:{s:5:"count";s:1:"0";s:9:"post_tags";s:0:"";s:4:"time";s:10:"1233798470";}";";'
reddit:
  - 's:63:"s:55:"a:2:{s:5:"count";s:1:"0";s:4:"time";s:10:"1233798471";}";";'
ljID:
  - 177
dsq_thread_id:
  - 465383981
categories:
  - .Net
  - Microsoft
  - Tip of Week
  - Visual Studio
tags:
  - .Net
  - Breakpoints
  - Microsoft
  - Technology
  - Visual Studio
  - Visual Studio Tip
  - Visual Studio Tip Of Week
  - Visual Studio tips
  - vs.net
---
Visual Studio offers a powerful debugger to aid with testing and troubleshooting your applications. One of the most common uses of a debugger is to set breakpoints, which are positions in the code that, when reached, cause the program execution to pause, allowing the developer to inspect the code and state of the program. When a breakpoint is reached and the application suspended, the application is in break mode. In break mode, you, the developer, can examine and change the values of the program variables.

The simplest way to add a breakpoint to a particular line of code is to click in the margin for that line of code. Or place the cursor on that line and press F9 to toggle breakpoint. You can also disable all breakpoints and delete all breakpoints from the debug menu.

<img class="aligncenter size-full wp-image-922" title="brkmenu" src="http://ajaymatharu.files.wordpress.com/2009/02/brkmenu.png" alt="brkmenu" width="311" height="330" />

The Breakpoints window provides a list of the current breakpoints and allows you to enable or disable breakpoints, delete breakpoints, add new breakpoints, and edit the properties of existing breakpoints. To display the Breakpoints window, go to the Debug menu&#8217;s Windows submenu and select the Breakpoints option. You can also display this window by pressing Ctrl-Alt-B (Debug.Breakpoints).

<img class="aligncenter size-full wp-image-923" title="brkwndw" src="http://ajaymatharu.files.wordpress.com/2009/02/brkwndw.png" alt="brkwndw" width="500" height="195" />

Break Only on Certain Conditions

Breakpoints in Visual Studio can be configured to cause the program to enter break mode only when a particular condition holds. To add a condition to a breakpoint, view the breakpoint&#8217;s properties by selecting the breakpoint from the Breakpoints window and clicking on the Properties icon. From any of the tabs, you will find a button titled Condition. Clicking on this will display the Breakpoint Condition dialog, where you can specify the condition to be watched. You can also right click on the breakpoint on the margin and select Condition,

<img class="aligncenter size-full wp-image-924" title="brk" src="http://ajaymatharu.files.wordpress.com/2009/02/brk.png" alt="brk" width="432" height="221" />

<img class="aligncenter size-full wp-image-926" title="brkcond" src="http://ajaymatharu.files.wordpress.com/2009/02/brkcond.png" alt="brkcond" width="481" height="228" />

Control How Often to Break on a Breakpoint

Breakpoints, by default, cause the program to enter break mode whenever they are hit and their condition, if any, is met. However, you can configure a breakpoint to enter break mode based on the breakpoint&#8217;s hit count. The hit count of a breakpoint is the number of times the breakpoint has been reached and the condition, if specified, has been met. Through the Breakpoint Properties dialog box, you can indicate when a breakpoint should cause the program to enter break mode based on its hit count value.

To configure this information, open up the properties for a breakpoint and click the Hit Count button Clicking on this button will display the Breakpoint Hit Count dialog.

<img class="aligncenter size-full wp-image-927" title="brkcount" src="http://ajaymatharu.files.wordpress.com/2009/02/brkcount.png" alt="brkcount" width="429" height="193" />
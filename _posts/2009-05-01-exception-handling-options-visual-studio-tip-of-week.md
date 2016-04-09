---
id: 1158
title: 'Exception Handling Options &#8211; Visual Studio Tip Of Week #20'
date: 2009-05-01T23:27:21+00:00
author: Ajay Matharu
layout: post
guid: http://www.ajaymatharu.com/?p=1158
permalink: /exception-handling-options-visual-studio-tip-of-week/
aktt_notify_twitter:
  - no
ljID:
  - 225
dsq_thread_id:
  - 465385058
categories:
  - .Net
  - Tip of Week
  - Visual Studio
tags:
  - .Net
  - Breakpoints
  - Debug
  - Development
  - exceptions
  - exceptions in visual studio
  - Execute
  - Tips
  - Visual Studio
  - vs.net
---
<p class="docText">
  <span class="docEmphBold">Exceptions are a sometimes-frustrating part of debugging and developing. You can configure Visual Studio to deal differently with certain exceptions</span>.
</p>

<p class="docText">
  When <a name="visualstudiohks-CHP-5-ITERM-2833"></a><a name="visualstudiohks-CHP-5-ITERM-2834"></a>debugging a program in Visual Studio, a number of situations may cause the debugger to enter break mode. When the debugger enters break mode, program execution is suspended, allowing you—the developer—the opportunity to examine and change the program variables. With Visual Studio 2005, you can even alter the program&#8217;s underlying source code when in break mode and have the program continue with the edited source.
</p>

<p class="docText">
  A common way that break mode is entered is through breakpoints. Another way that <a name="visualstudiohks-CHP-5-ITERM-2835"></a>break mode is regularly entered is when an exception is raised that is not handled by your application. Any exception that bubbles up out of your user code will cause the Visual Studio debugger to display information about the exception. While you will likely always want to be notified of an unhandled exception when debugging, you may want to break when an exception is thrown, regardless of whether or not it&#8217;s handled. Visual Studio can be easily customized to break immediately when a particular type of exception is thrown.
</p>

<p class="docText">
  To <a name="visualstudiohks-CHP-5-ITERM-2836"></a><a name="visualstudiohks-CHP-5-ITERM-2837"></a>customize Visual Studio&#8217;s behavior when encountering exceptions, go to Debug -> Exceptions or press <a name="visualstudiohks-CHP-5-ITERM-2838"></a><a name="visualstudiohks-CHP-5-ITERM-2839"></a>Ctrl-Alt-E (Debug.Exceptions). This will display the Exceptions dialog.
</p>

<p class="docText" style="text-align: center;">
  <div style="width: 671px" class="wp-caption aligncenter">
    <img title="Exception Dialog" src="http://ajaymatharu.files.wordpress.com/2009/05/exception.png" alt="Exception Dialog" width="661" height="331" />
    
    <p class="wp-caption-text">
      Exception Dialog
    </p>
  </div>
  
  <p class="docText" style="text-align: left;">
    <p class="docText">
      The Exceptions dialog allows you to specify Visual Studio&#8217;s behavior when encountering an exception of a specific type. As discussed earlier, the default behavior is to continue when the exception is thrown and to break into the debugger if the exception is not handled. To modify these settings for a particular exception type, simply choose the exception type from the tree of exceptions and customize the radio buttons, indicating the debugger&#8217;s behavior.
    </p>
    
    <p class="docText">
      Understand that changing the setting for a particular exception modifies the behavior for any of those <a name="visualstudiohks-CHP-5-ITERM-2841"></a>derived exception types whose Use Parent Setting option is selected. By default, all derived exceptions have this Use Parent Setting checked, which means that, by default, changing the behavior of an exception will propagate those changes to its derived exceptions.
    </p>
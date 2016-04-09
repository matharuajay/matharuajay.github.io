---
id: 621
title: 'Code Defination Window &#8211; Tip of week #13'
date: 2008-12-15T07:00:15+00:00
author: Ajay Matharu
layout: post
guid: http://ajaymatharu.wordpress.com/?p=621
permalink: /code-defination-window-tip-of-week-13/
ljID:
  - 122
dsq_thread_id:
  - 465386593
categories:
  - .Net
  - Development
  - Technical
  - Tip of Week
  - Visual Studio
tags:
  - .Net
  - ASP.Net
  - 'C#.Net'
  - Code defination window
  - Development
  - Tip of Week
  - Visual Studio
  - Visual Studio Tip
  - Visual Studio Tip Of Week
  - Visual Studio tips
  - vs.net
---
There are a few hidden gems in Visual Studio that are easy to overlook. One of those is the Code Definition Window (ctrl+\,ctrl+d or View &#8211; Code Definition Window).

The Code Definition Window will work in two different ways. The first is with your current code editing window. As you navigate your code, the Code Definition Window will display the definition of the objects currently under your cursor. For instance, if your cursor is currently over a class level variable, the Code Definition Window will display the location in the source file where the variable is declared. The same goes for methods and classes both within the current source file and in other source files within your current solution.

The second way the Code Definition Window can work is in conjunction with the Visual Studio Class View Window (ctrl+shift+c or View &#8211; Class View). The Class View Window is a handy tool window in its own right, giving a quick overview of the object model of the current solution and allowing fast navigation through namespaces, classes, and methods. If you double click on a method in the Class View Window, Visual Studio will open the appropriate source code file and scroll to that particular method. This is quite useful for larger projects and for projects that might have multiple class definitions in each file. However, if you single click on a method, the contents of that method will show in the Code Definition Window without opening the file in a text editing window.

<img class="aligncenter size-full wp-image-620" title="codeview" src="http://ajaymatharu.files.wordpress.com/2008/12/codeview.jpg" alt="codeview" width="691" height="484" />
---
toc: false
id: 279
title: JQuery in Visual Studio
date: 2009-05-18T00:00:45+00:00
author: Ajay Matharu
layout: post
guid: https://ajaymatharu.wordpress.com/?p=279
permalink: /jquery-in-visual-studio/
ljID:
  - 235
dsq_thread_id:
  - 465358134
categories:
  - ASP.Net
  - Javascript
  - Visual Studio
  - Web
tags:
  - .Net
  - ASP.Net
  - CSS
  - Developer
  - Development
  - Dot Net
  - Javascript
  - Jquery
  - Visual Studio
---
A big part of the appeal of jQuery is that it allows you to elegantly (and efficiently) find and manipulate HTML elements with minimum lines of code.  jQuery supports this via a nice &#8220;selector&#8221; API that allows developers to query for HTML elements, and then apply &#8220;commands&#8221; to them.  One of the characteristics of jQuery commands is that they can be &#8220;chained&#8221; together &#8211; so that the result of one command can feed into another.  jQuery also includes a built-in set of animation APIs that can be used as commands.  The combination allows you to do some really cool things with only a few keystrokes.

For example, the below JavaScript uses jQuery to find all <div> elements within a page that have a CSS class of &#8220;product&#8221;, and then animate them to slowly disappear:

<pre class="javascript">$("div.product").slideUp('slow').addClass("removed");</pre>

As another example, the JavaScript below uses jQuery to find a specific <table> on the page with an id of &#8220;datagrid1&#8221;, then retrieves every other <tr> row within the datagrid, and sets those <tr> elements to have a CSS class of &#8220;even&#8221; &#8211; which could be used to alternate the background color of each row:

<pre class="javascript">$("#datagrid1 tr:nth-child(even)").addClass("even");</pre>

The jQuery library also works well on the same page with ASP.NET AJAX and the ASP.NET AJAX Control Toolkit.

Visual Studio figures out external script references, such as to JQuery, by following special reference comments it finds at the top of .js files:

<pre>/// &lt;reference path="jquery-1.2.3.js" /&gt;</pre>

You can download the JQuery from <a href="https://code.google.com/p/jqueryjs/downloads/detail?name=jquery-1.2.6.js&downloadBtn=%3CSPAN%3EDownload%3C%2FSPAN%3E" target="_blank">here</a>. You can get more details on JQuery from [https://jquery.com/](https://jquery.com/api/) .

For intellisense support for JQuery you need to install this <a href="https://connect.microsoft.com/VisualStudio/Downloads/DownloadDetails.aspx?DownloadID=10826" target="_blank">Hotfix</a>.

Comment for javascript is written inside for intellisense support. JavaScript has the interesting feature that calling toString on a function returns the code of this function including the comments and thus the doc comments. Here&#8217;s a similar example in JavaScript where the documentation is written inside of a class constructor:

[<img class="aligncenter size-full wp-image-280" title="jsintellisense" src="https://ajaymatharu.files.wordpress.com/2008/10/jsintellisense.png" alt="" width="450" height="59" />](https://ajaymatharu.files.wordpress.com/2008/10/jsintellisense.png)

Another difference with C# or VB.NET is that property and event accessors are two different entities in JavaScript. For this reason, to choose where the documentation should be for those members. Properties should be documented in the getter and events in the &#8220;adder&#8221; for this reason:

[<img class="aligncenter size-full wp-image-281" title="js" src="https://ajaymatharu.files.wordpress.com/2008/10/js.png" alt="" width="450" height="133" />](https://ajaymatharu.files.wordpress.com/2008/10/js.png)

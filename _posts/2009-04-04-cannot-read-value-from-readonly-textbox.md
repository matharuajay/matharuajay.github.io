---
toc: false
id: 667
title: Cannot read value from readonly textbox
date: 2009-04-04T17:37:09+00:00
author: Ajay Matharu
layout: post
guid: https://ajaymatharu.wordpress.com/?p=667
permalink: /cannot-read-value-from-readonly-textbox/
ljID:
  - 212
dsq_thread_id:
  - 465387137
categories:
  - .Net
  - Development
  - Microsoft
  - Technical
  - Technology
  - Visual Studio
tags:
  - .Net
  - 'C#.Net'
  - Development
  - Microsoft
  - Technology
  - Visual Studio
  - vs.net
---
While working on the project we came across a problem that, we were not able to read value of read only text box, i.e. TextBox1.Text returned nothing even when the text box had value.

On googling, I found after doing this you can make your text box read only and also it will return the value of the text box. You need to insert this line on your Page_Load

TextBox1.Attributes.Add(&#8220;readonly&#8221;, &#8220;true&#8221;);

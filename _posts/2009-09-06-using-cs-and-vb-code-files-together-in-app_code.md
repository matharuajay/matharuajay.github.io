---
toc: false
id: 1465
title: Using CS and VB code files together in App_Code
date: 2009-09-06T11:48:06+00:00
author: Ajay Matharu
layout: post
guid: https://www.ajaymatharu.com/?p=1465
permalink: /using-cs-and-vb-code-files-together-in-app_code/
dsq_thread_id:
  - 465390579
categories:
  - .Net
  - Development
  - Microsoft
  - Tip of Week
  - Visual Studio
tags:
  - App_Code
  - C-Sharp
  - code lt
  - compilation
  - config
  - CS
  - 'CS &amp; VB'
  - Development
  - different languages
  - Different Languages in project
  - Multi-Language
  - Multiple coding Language
  - VB
  - vb code
  - vb files
  - vbcode
  - web.config
---
Many a times you require to use both C-Sharp (C#) and Visual Basic (VB) code class files in the same project.

If you just place your both the code files in your App_Code directly this is the error you&#8217;ll see,

&#8220;The files &#8216;/BlogEngine.Web/App\_Code/VBCode/Class1.vb&#8217; and &#8216;/BlogEngine.Web/App\_Code/CSCode/Extensions/BreakPost.cs&#8217; use a different language, which is not allowed since they need to be compiled together.&#8221;

But you can get this done, here is a very simple way you can try that out,

1) First make two folders in App_code with foldernames as
  
&#8211; CSCode
  
&#8211; VBCode

2) Modify the Web.config with following code:

<pre name="code" class="xml">&lt;compilation debug="false"&gt;
 &lt;codeSubDirectories&gt;
 &lt;add directoryName="VBCode" /&gt;
 &lt;add directoryName="CSCode" /&gt;
 &lt;/codeSubDirectories&gt;
&lt;/compilation&gt;</pre>

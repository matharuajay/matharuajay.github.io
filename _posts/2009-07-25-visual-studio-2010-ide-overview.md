---
toc: false
id: 509
title: Visual Studio 2010 IDE Overview
date: 2009-07-25T12:03:37+00:00
author: Ajay Matharu
layout: post
guid: http://ajaymatharu.wordpress.com/?p=509
permalink: /visual-studio-2010-ide-overview/
bte_opp_original_pub_date:
  - 2008-12-04 17:23:07
dsq_thread_id:
  - 465387619
categories:
  - Technology
  - Visual Studio
tags:
  - .Net
  - .Net Framework 4.0
  - Visual Studio
  - Visual Studio 2010
  - Visual Studio 2010 IDE
  - vs.net
---
**Understanding existing, and writing new, code**

As the complexity of applications grows so does the
  
challenge of understanding the code that you’re working
  
on. With Visual Studio 2010 the IDE provides integrated
  
support for understanding what is happening in the code
  
section that you’re viewing.

The editor in Visual Studio 2010 has been rebuilt using the
  
Windows Presentation Foundation (WPF) technology. WPF
  
enables the editor to richly present information about the
  
code in the context of presenting the actual source. This ability
  
enables features such as the “Document Map Margin” to render
  
a graphical view of the source file including information such as
  
layout, code coverage, symbol highlights and comments.

This editor ability also enables 3rd parties to create add-ins
  
that show custom views of the underlying source file such as
  
taking the XML Doc Comments and converting them to a rich
  
presentation formation with fonts, colors and highlighting. It
  
enables Visual Studio to display different layers on the editor
  
so an add-in could represent a code-based formula in its
  
traditional mathematical representation.

While the representation of the underlying source code is
  
important so is the ability to understand what the code is
  
actually doing. In Visual Studio 2010, features such as “Inline
  
Call Hierarchy” &#8211; a feature which enables a developer to select
  
an entity or method and see how the code calls inwards or
  
outwards or passes the entity in and out of the code section
  
&#8211; provide developers with the ability to understand the
  
interaction of the code without needing to juggle multiple
  
files. Other features such as “Highlight References”, which
  
provide a visual representation of the references to a selected
  
entity in the code without needing to use the “Find In Files”
  
feature, or “Quick Searching”, which delivers a ‘word wheel’
  
based search tool integrated with “Highlight References”,
  
enable developers to maintain the context of where they are
  
but gain the understanding of other locations in the code.

Additionally the editor integrates with the project system to
  
simplify the pattern of Test Driver Development (TDD). With
  
TDD, developers build the tests that will exercise their application
  
code before they actually write that code. In Visual Studio
  
2010 developers can create tests and the editor will provide
  
functionality to automatically implement the tested classes and
  
code in the file the developer chooses. This enables developers to
  
quickly create the class they are consuming without needing to
  
break out of the test development flow to declare the tested class.

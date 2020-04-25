---
toc: false
id: 665
title: control does not exists in current context
date: 2009-07-22T23:24:49+00:00
author: Ajay Matharu
layout: post
guid: http://ajaymatharu.wordpress.com/?p=665
permalink: /control-does-not-exists-in-current-context/
ljID:
  - 292
dsq_thread_id:
  - 465390156
categories:
  - .Net
  - ASP.Net
  - Visual Studio
tags:
  - .Net
  - .net controls
  - ASP.Net
  - 'C#'
  - 'C#.Net'
  - context
  - Dot Net
  - VB
  - vb.net
  - Visual Studio
  - visual studio.net
  - vs.net
---
<span style="font-size:85%;">Another one of those problems that can stump you for a while. I often make backups of files as I progress and sometimes leave them in the website folder, this was fine with classic ASP but as I have found with ASP.Net can cause all sorts of problems.</span><span style="font-size:85%;">One issue I was having was trying to reference a component in my aspx page from the codebehind page and seeing the following error when trying to reference a label control:</span>

> <span style="font-size:85%;">“Label2 does not exist in the current context”</span>

<span style="font-size:85%;">So I found that the problem was even though I renamed one of my old files it still contained the class that my codebehind was referencing (i.e. the class names were still the same) &#8211; and therefore was not seeing the newly added Label control to my new code.</span><span style="font-size:85%;">Shame the compiler doesn’t realise the duplication and give some indication.</span>

Lesson: Remove any backed up files from the web folder and/or build directory to avoid pain <img class="wp-smiley" src="http://s.wordpress.com/wp-includes/images/smilies/icon_smile.gif" alt=")" />

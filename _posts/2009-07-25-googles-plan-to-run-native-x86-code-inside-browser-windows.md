---
toc: false
id: 649
title: 'Google&#8217;s plan to run native x86 code inside browser windows'
date: 2009-07-25T12:03:33+00:00
author: Ajay Matharu
layout: post
guid: http://ajaymatharu.wordpress.com/?p=649
permalink: /googles-plan-to-run-native-x86-code-inside-browser-windows/
bte_opp_original_pub_date:
  - 2008-12-19 07:09:28
dsq_thread_id:
  - 465385245
categories:
  - Browsers
  - Technology
tags:
  - Browsers
  - Development
  - Google
  - Technology
---
The browser&#8217;s role is ever increasing. It already has become far more than a mere tool for accessing information. Today we use it to communicate, to collaborate, and to interface with applications. And if Google has its way, we&#8217;ll soon be able to use it to chalk up a few righteous frags, too.

Last week, a team of Google engineers demonstrated a copy of Id Software&#8217;s classic first-person shooter Quake running within a browser window at a frame rate comparable to an OS-hosted copy of the game.

How did they do it? Simple. The <a href="http://code.google.com/p/nativeclient/" target="_blank">Google Native Client</a> is a new set of components that allows Web browsers to download and execute native x86 code. It&#8217;s not an emulator, and it&#8217;s not a virtual machine. The code runs on the actual processor with access to memory and system resources and negligible loss of performance. It even gives browser-based apps access to modern, accelerated CPU instruction sets, such as SSE.

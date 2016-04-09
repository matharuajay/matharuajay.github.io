---
id: 151
title: 'Intellisense not working in Visual Studio &#8211; Tip of Week #1'
date: 2008-09-26T17:35:37+00:00
author: Ajay Matharu
layout: post
guid: http://ajaymatharu.wordpress.com/?p=151
permalink: /intellisense-not-working-in-visual-studio/
ljID:
  - 28
dsq_thread_id:
  - 465393194
categories:
  - .Net
  - CodeProject
  - Development
  - Technical
  - Tip of Week
  - Visual Studio
tags:
  - Tip of Week
  - Visual Studio
  - Visual Studio tips
---
Sometimes your intellisence stops working in Visual Studio.

The problem mostly arises when you install some add-in or uninstall the add-in. I faced this problem When I un-installed re-shareper. All you have to do to get back your intellisense is

just close your Visual Studio.

Navigate to Windows -> run, and type &#8220;devenv /resetsettings&#8221; without double quotes. This will reset the settings completely. You can have your intellinsence back this way. You can also write &#8220;devenv /resetsettings&#8221; from your command prompt.
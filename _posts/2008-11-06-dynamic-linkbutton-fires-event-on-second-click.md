---
toc: false
id: 410
title: Dynamic Linkbutton fires event on second click
date: 2008-11-06T15:07:38+00:00
author: Ajay Matharu
layout: post
guid: https://ajaymatharu.wordpress.com/?p=410
permalink: /dynamic-linkbutton-fires-event-on-second-click/
ljID:
  - 80
dsq_thread_id:
  - 465393117
categories:
  - .Net
  - ASP.Net
  - Development
  - Technical
  - Visual Studio
tags:
  - .Net
  - 'C#.Net'
  - Linkbutton
  - Technology
  - Visual Studio
---
I recently ran into a problem involving a dynamically generated <strong class="highlight">linkbutton</strong> control inconsistently requiring two clicks in order to reach its <strong class="highlight">Click</strong> handler method.

Most of the posts I found kept referring people to the page lifecycle, but in the end that had nothing to do with it. The issue was that the controls ID values were being assigned automatically by .NET so they were {ctl001, ctl002, ctl003&#8230;} etc. Because the page displayed and made invisible few controls by clicking <strong class="highlight">on</strong> linkbuttons, these ID values were capable of changing between page loads. This would cause the <strong class="highlight">dynamically</strong> loaded controls to receive different IDs than they had <strong class="highlight">on</strong> the previous page load and would result in a screwed up viewstate.

.NET could not identify which control went with which viewstate/handler. Later I saw and noticed that I had forgoten to assign ID to the linkbutton, which solved my problem. So I would reccomend to anybody dealing with this issue, view source in your browser and look at the IDs assigned to your controls. If there are a lot of ctl002, ctl003, ctl004 type of control IDs in your html try to eliminate those by assigning more explicit and static names that will not be affected by the addition or removal of other controls <strong class="highlight">on</strong> the page.

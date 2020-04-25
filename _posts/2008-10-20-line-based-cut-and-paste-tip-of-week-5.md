---
toc: false
id: 211
title: 'Line-Based Cut and Paste &#8211; Tip of week #5'
date: 2008-10-20T04:08:40+00:00
author: Ajay Matharu
layout: post
guid: https://ajaymatharu.wordpress.com/?p=211
permalink: /line-based-cut-and-paste-tip-of-week-5/
ljID:
  - 43
dsq_thread_id:
  - 465391423
categories:
  - Technical
  - Tip of Week
  - Visual Studio
tags:
  - Tip of Week
  - Visual Studio
  - Visual Studio tips
---
<p class="docText">
  The <a name="visualstudiohks-CHP-2-ITERM-2244"></a><a name="visualstudiohks-CHP-2-ITERM-2245"></a><a name="visualstudiohks-CHP-2-ITERM-2246"></a>clipboard ring is not the only copy and paste feature in Visual Studio; a number of shortcut keys allow you to copy and paste code even faster.
</p>

<p class="docText">
  Most applications rely on you selecting which text you want to cut, copy, or delete. Visual Studio makes the very simple assumption that if you have not selected any text that you want to cut, copy, or delete, <span class="docEmphasis">the editing action will be performed on the entire current line</span>. If you wanted to move one line below another line, you could move the cursor to the first line, press <a name="visualstudiohks-CHP-2-ITERM-2247"></a><a name="visualstudiohks-CHP-2-ITERM-2248"></a>Ctrl-X (Edit.Cut) to cut the line, press the down arrow to move to the next line down, and then press <a name="visualstudiohks-CHP-2-ITERM-2249"></a><a name="visualstudiohks-CHP-2-ITERM-2250"></a>Ctrl-V (Edit.Paste) to paste the entire line. Other shortcuts like Ctrl-C (Edit.Copy) and <a name="visualstudiohks-CHP-2-ITERM-2251"></a><a name="visualstudiohks-CHP-2-ITERM-2252"></a>Ctrl-L (Edit.LineCut) follow this same rule and allow you to copy or delete the current line by simply pressing the shortcut keys without selecting any text. Any time you can avoid reaching for the mouse to select text is time saved.
</p>

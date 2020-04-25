---
toc: false
id: 207
title: 'Block Selection &#8211; Tip of week #4'
date: 2008-10-14T04:52:00+00:00
author: Ajay Matharu
layout: post
guid: https://ajaymatharu.wordpress.com/?p=207
permalink: /block-selection-tip-of-week-4/
ljID:
  - 41
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
  Normal <a name="visualstudiohks-CHP-2-ITERM-2253"></a><a name="visualstudiohks-CHP-2-ITERM-2254"></a><a name="visualstudiohks-CHP-2-ITERM-2255"></a>text selection is done on a line-by-line basis; it is impossible to select parts of multiple lines with normal text selection. <a class="docLink" href="#visualstudiohks-CHP-2-FIG-2">Figure 2-2</a> shows how it is not possible to select just the right side of the equals sign using normal text selection. This is a drawback that most of us have become accustomed to.
</p>

<a name="visualstudiohks-CHP-2-FIG-2"></a>

[<img class="aligncenter size-full wp-image-208" title="normaltext" src="https://ajaymatharu.files.wordpress.com/2008/10/normaltext.jpg" alt="" width="450" height="131" />](https://ajaymatharu.files.wordpress.com/2008/10/normaltext.jpg)

<p class="docText">
  Visual Studio has a feature that allows you to get around this limitation. By holding the Alt key while selecting text, you trigger <span class="docEmphasis">block selection</span>, which allows you to select text regardless of what line it is on. <a class="docLink" href="#visualstudiohks-CHP-2-FIG-3">Figure 2-3</a> shows how block selection can be used to select only text to the right of the equals sign.
</p>

<a name="visualstudiohks-CHP-2-FIG-3"></a>

##### [<img class="aligncenter size-full wp-image-209" title="block" src="https://ajaymatharu.files.wordpress.com/2008/10/block.jpg" alt="" width="450" height="128" />](https://ajaymatharu.files.wordpress.com/2008/10/block.jpg) {.docFigureTitle}

<p class="docText">
  Block selection can be used to select any amount of text in a block, as opposed to line by line. You can use block selection whether you select text with the mouse or the <a name="visualstudiohks-CHP-2-ITERM-2256"></a>keyboard (hold down Alt and Shift, and press the arrow keys to perform a block selection with the keyboard).
</p>

<p class="docText">
  When <a name="visualstudiohks-CHP-2-ITERM-2257"></a>pasting block selections, Visual Studio will insert each line of the block onto a subsequent existing line, unlike normal selections where new lines will be inserted. Thus, it is important to be sure that the destination for your block selection is the same number of lines as the source.<a name="visualstudiohks-CHP-2-ITERM-2258"></a> <a name="visualstudiohks-CHP-2-ITERM-2259"></a>
</p>

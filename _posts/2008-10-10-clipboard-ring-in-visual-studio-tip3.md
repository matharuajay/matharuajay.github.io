---
toc: false
id: 184
title: 'Clipboard Ring in Visual Studio &#8211; Tip of Week #3'
date: 2008-10-10T03:49:03+00:00
author: Ajay Matharu
layout: post
guid: http://ajaymatharu.wordpress.com/?p=184
permalink: /clipboard-ring-in-visual-studio-tip3/
ljID:
  - 38
dsq_thread_id:
  - 465358061
categories:
  - Tip of Week
  - Visual Studio
tags:
  - Tip of Week
  - Visual Studio tips
---
<p class="docText">
  When you copy and paste text in any application, you are usually limited to copying and pasting one item at a time. If you want to copy two separate sentences, you have to copy the first one, paste it, then come back and repeat this for the next sentence. This can become tedious when you have 10 different things to copy and they reside in 10 different places in the document. You end up switching back and forth between the two documents 10 times, once for each sentence you want to copy.
</p>

<p class="docText">
  The clipboard ring eliminates this limitation. The clipboard ring allows you to cut or copy up to 20 selections and access them using a keyboard shortcut. Here is the process for using the<a name="visualstudiohks-CHP-2-ITERM-2235"></a> clipboard ring:
</p>

<div style="font-weight:bold;">
  <ol class="docList" type="1">
    <li>
      <div style="font-weight:normal;">
        <p class="docList">
          <a name="visualstudiohks-CHP-2-ITERM-2236"></a><a name="visualstudiohks-CHP-2-ITERM-2237"></a><a name="visualstudiohks-CHP-2-ITERM-2238"></a><a name="visualstudiohks-CHP-2-ITERM-2239"></a>Copy (Ctrl-C, Edit.Copy) or Cut (Ctrl-X, Edit.Cut) up to 20 text selections, one after the other. These selections are organized as a last-in-first-out (LIFO) stack. That is, the last item you cut or copy will be the top item on the clipboard ring.
        </p>
      </div>
    </li>
    
    <li>
      <div style="font-weight:normal;">
        <p class="docList">
          Press <a name="visualstudiohks-CHP-2-ITERM-2240"></a><a name="visualstudiohks-CHP-2-ITERM-2241"></a>Ctrl-Shift-V to paste the first selection (the item on the top) from the clipboard ring into your document.
        </p>
      </div>
    </li>
    
    <li>
      <div style="font-weight:normal;">
        <p class="docList">
          If you don&#8217;t want to paste the first selection, press Ctrl-Shift-V (Edit.CycleClipboardRing) again, and the first thing you pasted will be replaced with the next selection from the clipboard ring. For example, if you wanted to paste the fourth item in the clipboard ring, you would simply press Ctrl-Shift-V four times. If you want to paste the same item more than once, simply pressing <a name="visualstudiohks-CHP-2-ITERM-2242"></a><a name="visualstudiohks-CHP-2-ITERM-2243"></a>Ctrl-V (Edit.Paste) after the first time will work, since it will now be the current item on the clipboard.
        </p>
      </div>
    </li>
  </ol>
</div>

<p class="docText">
  Instead of moving between two documents a number of times, copying and pasting different selections, you can first copy all of the selections from the first document, then go to the second document and, using the clipboard ring, paste all of those selections. The clipboard ring also comes in handy when you have two or more separate things that you need to paste multiple times; using the clipboard ring, you can switch back and forth between these items easily.
</p>

<p class="docText">
  You can also view the current contents of the clipboard ring by selecting the Clipboard Ring tab in the Toolbox dialog. This tab, shown in <a class="docLink" href="http://ajaymatharu.wordpress.com/wp-admin/#visualstudiohks-CHP-2-FIG-1">Figure 2-1</a>, displays all of the selections currently living in the clipboard ring and allows you to drag the selections to paste them into your document.
</p>

<p class="docText">
  <a href="http://ajaymatharu.files.wordpress.com/2008/10/clipboardring.png"><img class="aligncenter size-medium wp-image-186" title="Clipboard Ring" src="http://ajaymatharu.files.wordpress.com/2008/10/clipboardring.png?w=300" alt="" width="300" height="128" /></a>
</p>

<p class="docText">
   
</p>

<p class="docText">
  While the Clipboard Ring tab is a good way to get a better understanding of the clipboard ring, it is not as efficient as the shortcut keys. Visual Studio .NET 2003 users will find that the Clipboard Ring tab is absent in Visual Studio 2005, so it is best to use the shortcut keys instead of the Toolbox tab.
</p>

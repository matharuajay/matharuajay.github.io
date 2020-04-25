---
toc: false
id: 239
title: 'Add Guidelines to the Text Editor &#8211; Tip of week #7'
date: 2008-11-03T03:36:11+00:00
author: Ajay Matharu
layout: post
guid: https://ajaymatharu.wordpress.com/?p=239
permalink: /add-guidelines-to-the-text-editor-tip-of-week-7/
ljID:
  - 77
dsq_thread_id:
  - 465385973
categories:
  - Tip of Week
  - Visual Studio
tags:
  - Tip of Week
  - Visual Studio tips
---
<p class="docText">
  <span class="docEmphBold">If you&#8217;ve got to have everything line up just right, turn on guidelines and get everything pixel perfect</span>.
</p>

<p class="docText">
  <a name="visualstudiohks-CHP-2-ITERM-2331"></a><a name="visualstudiohks-CHP-2-ITERM-2332"></a>One of the features missing from the text editor in Visual Studio is the ability to add <a name="visualstudiohks-CHP-2-ITERM-2333"></a>vertical guidelines. Vertical guidelines are thin vertical lines that can be used as visual guides when aligning text. This feature is not actually missing though—using a simple <a name="visualstudiohks-CHP-2-ITERM-2334"></a>registry hack, you can add up to 13 different guidelines to Visual Studio&#8217;s text editor.
</p>

<p class="docText">
  To add guidelines:
</p>

<div style="font-weight:bold;">
  <ol class="docList" type="1">
    <li>
      <div style="font-weight:normal;">
        <p class="docList">
          Close Visual Studio.
        </p>
      </div>
    </li>
    
    <li>
      <div style="font-weight:normal;">
        <p class="docList">
          Open <em>regedit</em> (Start &#8211; Run &#8211; type <tt><strong>regedit</strong></tt>).
        </p>
      </div>
    </li>
    
    <li>
      <div style="font-weight:normal;">
        <p class="docList">
          Navigate to <em>HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\<version number>\Text Editor</em>.
        </p>
      </div>
    </li>
    
    <li>
      <div style="font-weight:normal;">
        <p class="docList">
          Right-click on the Text Editor key and choose New &#8211; String Value and name it &#8220;Guides&#8221;.
        </p>
      </div>
    </li>
    
    <li>
      <div style="font-weight:normal;">
        <p class="docList">
          Set the value of the guides to <tt>RGB(128, 128, 128) 4, 16</tt>.
        </p>
      </div>
    </li>
  </ol>
</div>

<p class="docText">
  The first part of the value sets the color of the guidelines using common red, green, and blue values. 128, 128, and 128 sets the color of the guidelines to gray. The second numbers specify where the guidelines should appear. In this example, guidelines will be shown at the 4-space mark as well as the 16-space mark. You can add up to 13 different guidelines by simply adding more numeric values separated by commas.
</p>

<p class="docText">
  After you have created your registry entry, you will see guidelines in the marks specified when you launch Visual Studio. <a class="docLink" href="https://ajaymatharu.wordpress.com/wp-admin/#visualstudiohks-CHP-2-FIG-21">Figure 2-21</a> shows an example of the results from the example settings.
</p>

<p class="docText">
  <a href="https://ajaymatharu.files.wordpress.com/2008/10/guidelines.png"><img class="aligncenter size-full wp-image-240" title="guidelines" src="https://ajaymatharu.files.wordpress.com/2008/10/guidelines.png" alt="" width="450" height="285" /></a>
</p>

<p class="docText">
  Removing these guidelines is simply a matter of deleting the Guides registry key and restarting Visual Studio.
</p>

<p class="docText">
  Guidelines are easy to add and can be very useful when trying to keep your code organized.
</p>

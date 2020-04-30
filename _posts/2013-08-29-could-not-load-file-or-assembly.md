---
toc: false
id: 2787
title: Could not load file or assembly or one of its dependencies
date: 2013-08-29T11:50:37+00:00
author: Ajay Matharu
layout: post
guid: https://www.ajaymatharu.com/?p=2787
permalink: /could-not-load-file-or-assembly/
dsq_thread_id:
  - 1663396311
categories:
  - .Net
  - ASP.Net
  - CodeProject
tags:
  - .Net
  - application pool
  - ASP.Net
  - assembly
  - 'C#.Net'
  - could not load assembly
  - could not load file or assembly
---
&#8220;Could not load file or assembly or one of its dependencies&#8221;. You come across this error message a lot if you are .net developer.

> ## Could not load file or assembly or one of its dependencies. An attempt was made to load a program with an incorrect format.

<div id="attachment_2789" style="width: 1034px" class="wp-caption aligncenter">
  <a href="https://blog.ajaymatharu.com/wp-content/uploads/2013/08/Could-not-load-file-or-assembly-or-one-of-its-dependencies.-An-attempt-was-made-to-load-a-program-with-an-incorrect-format.png"><img class="size-large wp-image-2789" alt="could not load file or assembly" src="https://blog.ajaymatharu.com/wp-content/uploads/2013/08/Could-not-load-file-or-assembly-or-one-of-its-dependencies.-An-attempt-was-made-to-load-a-program-with-an-incorrect-format-1024x511.png" width="1024" height="511" /></a>
  
  <p class="wp-caption-text">
    Could not load file or assembly or one of its dependencies. An attempt was made to load a program with an incorrect format
  </p>
</div>

## There are two solution&#8217;s for this problem

1 &#8211; Make sure you are referencing the correct dll and its there.

2 &#8211; if the above solution doesn&#8217;t work, You need to enable 32 bit application in your IIS application pool. Attached is the screen shot of where you&#8217;ll get that configuration.

<div id="attachment_2790" style="width: 1034px" class="wp-caption aligncenter">
  <a href="https://blog.ajaymatharu.com/wp-content/uploads/2013/08/IIS1.png"><img class="size-large wp-image-2790" alt="Application Pool Advance Settings" src="https://blog.ajaymatharu.com/wp-content/uploads/2013/08/IIS1-1024x543.png" width="1024" height="543" srcset="https://blog.ajaymatharu.com/wp-content/uploads/2013/08/IIS1-300x159.png 300w, https://blog.ajaymatharu.com/wp-content/uploads/2013/08/IIS1-1024x543.png 1024w, https://blog.ajaymatharu.com/wp-content/uploads/2013/08/IIS1.png 1442w" sizes="(max-width: 1024px) 100vw, 1024px" /></a>
  
  <p class="wp-caption-text">
    Application Pool Advance Settings
  </p>
</div>

<div id="attachment_2791" style="width: 1022px" class="wp-caption aligncenter">
  <a href="https://blog.ajaymatharu.com/wp-content/uploads/2013/08/enable32bitapplication.png"><img class="size-full wp-image-2791" alt="Enable 32-bit Applications" src="https://blog.ajaymatharu.com/wp-content/uploads/2013/08/enable32bitapplication.png" width="1012" height="622" srcset="https://blog.ajaymatharu.com/wp-content/uploads/2013/08/enable32bitapplication-300x184.png 300w, https://blog.ajaymatharu.com/wp-content/uploads/2013/08/enable32bitapplication.png 1012w" sizes="(max-width: 1012px) 100vw, 1012px" /></a>
  
  <p class="wp-caption-text">
    Enable 32-bit Applications
  </p>
</div>

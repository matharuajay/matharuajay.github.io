---
toc: false
id: 2847
title: Tweet Old Post Permission Issue
date: 2014-01-17T10:30:04+00:00
author: Ajay Matharu
layout: post
guid: http://www.ajaymatharu.com/?p=2847
permalink: /tweet-old-post-permission-issue/
dsq_thread_id:
  - 2132637187
categories:
  - Development
  - Plugins
  - wordpress
tags:
  - Tweet Old Post
  - Tweet Old Post Permissions
  - wordpress plugin tweet old post
---
# Tweet Old Post permission issue

<span style="line-height: 1.5em;">Lot of people are not able to access the tweet old post and buffer my post admin page. </span><span style="line-height: 1.5em;">If you are not able to see the admin page and you are admin of the site try this fix.</span>

## Problem

&#8220;You do not have enough permission to set the option. Please contact your admin&#8221;

## Solution

<div>
  Login to wordpress -> Go to Plugins -> Editor -> Select Tweet Old Post on right top, in Select plugin to edit.
</div>

<div>
  <div id="attachment_2852" style="width: 173px" class="wp-caption aligncenter">
    <a href="http://www.ajaymatharu.com/wp-content/uploads/2014/01/Edit-Plugins.png"><img class="size-full wp-image-2852" alt="Plugin Editor" src="http://www.ajaymatharu.com/wp-content/uploads/2014/01/Edit-Plugins.png" width="163" height="156" /></a>
    
    <p class="wp-caption-text">
      Plugin Editor
    </p>
  </div>
</div>

<div>
  <div id="attachment_2853" style="width: 723px" class="wp-caption aligncenter">
    <a href="http://www.ajaymatharu.com/wp-content/uploads/2014/01/Edit-Plugins-Tweet-Old-Post.png"><img class="size-full wp-image-2853 " title="Edit Tweet Old Post" alt="Edit Plugin" src="http://www.ajaymatharu.com/wp-content/uploads/2014/01/Edit-Plugins-Tweet-Old-Post.png" width="713" height="626" srcset="http://www.ajaymatharu.com/wp-content/uploads/2014/01/Edit-Plugins-Tweet-Old-Post-300x263.png 300w, http://www.ajaymatharu.com/wp-content/uploads/2014/01/Edit-Plugins-Tweet-Old-Post.png 713w" sizes="(max-width: 713px) 100vw, 713px" /></a>
    
    <p class="wp-caption-text">
      Edit Plugin Tweet Old Post
    </p>
  </div>
</div>

<div>
  Click on top_admin.php on the right and make the below change
</div>

<div>
  <p>
     if (current_user_can(&#8216;edit_<wbr />plugins&#8217;))
  </p>
  
  <p>
    to
  </p>
  
  <p>
    if (current_user_can(&#8216;activate_<wbr />plugins&#8217;))
  </p>
  
  <p>
    &nbsp;
  </p>
  
  <p>
    Let me know if that solved the problem.
  </p>
</div>

&nbsp;

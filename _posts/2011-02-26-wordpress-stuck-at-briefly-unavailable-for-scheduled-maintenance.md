---
id: 2604
title: WordPress stuck at briefly unavailable for scheduled maintenance
date: 2011-02-26T19:44:32+00:00
author: Ajay Matharu
layout: post
guid: http://www.ajaymatharu.com/?p=2604
permalink: /wordpress-stuck-at-briefly-unavailable-for-scheduled-maintenance/
dsq_thread_id:
  - 465391484
categories:
  - Plugins
  - wordpress
tags:
  - Bypass maintenance mode in wordpress
  - disable maintenance check in wordpress
  - disable maintenance mode in wordpress
  - Maintenance mode in wordpress
  - prevent maintenance check
  - prevent maintenance message
  - prevent scheduled maintenance message
---
Today while updating a plugin, update window got stuck at following image,

<div id="attachment_2606" style="width: 710px" class="wp-caption aligncenter">
  <a rel="attachment wp-att-2606" href="http://www.ajaymatharu.com/wordpress-stuck-at-briefly-unavailable-for-scheduled-maintenance/wordpress_maintenance/"><img class="size-full wp-image-2606" title="Wordpress_Maintenance" src="http://www.ajaymatharu.com/wp-content/uploads/2011/02/Wordpress_Maintenance.png" alt="Wordpress scheduled maintenance message" width="700" height="169" /></a>
  
  <p class="wp-caption-text">
    Wordpress scheduled maintenance message
  </p>
</div>

And I was not able to figure out why was it. Then I went back to the update page and saw the following message,

<div id="attachment_2609" style="width: 744px" class="wp-caption aligncenter">
  <a rel="attachment wp-att-2609" href="http://www.ajaymatharu.com/wordpress-stuck-at-briefly-unavailable-for-scheduled-maintenance/enabling_maintenance/"><img class="size-full wp-image-2609" title="Enabling maintenance mode in wordpress" src="http://www.ajaymatharu.com/wp-content/uploads/2011/02/Enabling_maintenance.png" alt="Enabling maintenance mode in wordpress" width="734" height="172" srcset="http://www.ajaymatharu.com/wp-content/uploads/2011/02/Enabling_maintenance-300x70.png 300w, http://www.ajaymatharu.com/wp-content/uploads/2011/02/Enabling_maintenance.png 734w" sizes="(max-width: 734px) 100vw, 734px" /></a>
  
  <p class="wp-caption-text">
    Enabling maintenance mode in wordpress
  </p>
</div>

Here you can see the wordpress enables maintenance mode before pushing any update. But what if  update is not completed successfully?

If update does not happen successfully your page gets stuck on above image and your site shows message in first image.

How can you remove this annoying messages? After googling out I figured out wordpress creates a .maintenance page in the root directory where your wordpress is installed. You need to delete this file, which I did. After deleting the site was up again.

<div id="attachment_2610" style="width: 255px" class="wp-caption aligncenter">
  <a rel="attachment wp-att-2610" href="http://www.ajaymatharu.com/wordpress-stuck-at-briefly-unavailable-for-scheduled-maintenance/maintenance_file/"><img class="size-full wp-image-2610" title="Wordpress maintenance file" src="http://www.ajaymatharu.com/wp-content/uploads/2011/02/maintenance_file.png" alt="Wordpress maintenance file" width="245" height="237" /></a>
  
  <p class="wp-caption-text">
    Wordpress maintenance file
  </p>
</div>

But this happened everytime I tried to update that plugin. So I searched for place where wordpress was checking if it is in maintenance mode.

WordPress has a file called as &#8220;wp-settings.php&#8221; in the root directory. It has line of code that checks if maintenance mode is enabled. So just comment that line and wordpress will not go in maintenance mode again.

<div id="attachment_2611" style="width: 479px" class="wp-caption aligncenter">
  <a rel="attachment wp-att-2611" href="http://www.ajaymatharu.com/wordpress-stuck-at-briefly-unavailable-for-scheduled-maintenance/comment_maintenance/"><img class="size-full wp-image-2611" title="Bypass maintenance mode check in wordpress" src="http://www.ajaymatharu.com/wp-content/uploads/2011/02/comment_maintenance.png" alt="Bypass maintenance mode check in wordpress" width="469" height="232" srcset="http://www.ajaymatharu.com/wp-content/uploads/2011/02/comment_maintenance-300x148.png 300w, http://www.ajaymatharu.com/wp-content/uploads/2011/02/comment_maintenance.png 469w" sizes="(max-width: 469px) 100vw, 469px" /></a>
  
  <p class="wp-caption-text">
    Bypass maintenance mode check in wordpress
  </p>
</div>

It will show you the message enabling maintenance mode but still your site will be up.

Hope this helps.
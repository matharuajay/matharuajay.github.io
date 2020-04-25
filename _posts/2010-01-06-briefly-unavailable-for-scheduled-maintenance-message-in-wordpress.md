---
toc: false
id: 1978
title: 'Briefly unavailable for scheduled maintenance &#8211; message in wordpress'
date: 2010-01-06T11:30:48+00:00
author: Ajay Matharu
layout: post
guid: https://www.ajaymatharu.com/?p=1978
permalink: /briefly-unavailable-for-scheduled-maintenance-message-in-wordpress/
aktt_notify_twitter:
  - no
dsq_thread_id:
  - 465387370
categories:
  - wordpress
tags:
  - problems while upgrading wordpress
  - upgrading wordpress issues
  - wordpress
  - wordpress maintenance
  - wordpress maintenance check
  - wordpress maintenance message
  - Wordpress upgrade
---
Recently I upgraded my wordpress to 2.9. I was really impressed with the option to upgrade all the plugins together, It really rocks. You don&#8217;t have to manually upgrade individual plugins like in older versions. May be, this feature may be present in the older version as well, I would have not checked that out 😛

When I tried upgrading all the plugins together, One of them failed. When I refreshed the page, all I got was the following message

> <div>
>   Briefly unavailable for scheduled maintenance. Check back in a minute.
> </div>

And I checked back again after around 5 minutes, but the message still persists. I was very annoyed with this wired behavior of wordpress. That message was there ever after checking the site after 30 mins. I really thought, what the f\***.

Finally I started googling about the message and this strange behavior of wordpress and found a solution to this.

## Cause of Maintenance message in wordpress

During an automatic upgrade, WordPress places a file in the blog root directory called “.maintenance” to prevent visitors from being confronted with ugly, broken pages during the upgrade process. That’s a great little built-in feature, but if the upgrade gets interrupted or fails for any reason, that file doesn’t get deleted and nobody, including you, can access your blog.

## Removing the maintenance message in wordpress

All you have to do is delete the .maintenance file from the blog root directory. Simple as it gets. After you’ve deleted the files you should be able to access the site just fine, but you may have to run the automatic upgrade again. How do you know if you should run it again? You’ll see a notification on the dashboard page that a new version of WordPress is available, same as you always see when a new upgrade is available. If you don’t see that message, you’re good to go.

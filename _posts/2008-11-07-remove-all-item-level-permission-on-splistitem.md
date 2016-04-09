---
id: 414
title: Remove all item level permission on SPListItem
date: 2008-11-07T15:34:00+00:00
author: Ajay Matharu
layout: post
guid: http://ajaymatharu.wordpress.com/?p=414
permalink: /remove-all-item-level-permission-on-splistitem/
ljID:
  - 81
dsq_thread_id:
  - 465389268
categories:
  - .Net
  - ASP.Net
  - Sharepoint
  - Technical
  - Technology
tags:
  - .Net
  - ASP.Net
  - Item level permission
  - MOSS
  - Sharepoint
  - Sharepoint permissions
---
It&#8217;s been very long, I have been finding a way to remove all the item level permission.

My requirement was to set permission only to particular users and groups on an item and remove rest all. I almost spend 3 weeks in finding a way to remove all the permission on the item so that later I can add the permissions which I want. Atlast I found a way to remove all the permission set on item let it be user specific or group specific. Here is the code snippet that helps you to do that,
  
for (int k = itm.RoleAssignments.Count &#8211; 1; k >= 0; k&#8211;)
  
{
  
itm.RoleAssignments.Remove(k);
  
}

here itm is an SPListItem object from which you want to remove all permissions.

You can loop through all the SPListCollection and then for each SPListItem you can remove all the permission on that item.
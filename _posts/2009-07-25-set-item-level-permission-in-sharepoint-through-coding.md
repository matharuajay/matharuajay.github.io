---
toc: false
id: 417
title: Set Item level permission in sharepoint through coding
date: 2009-07-25T12:03:31+00:00
author: Ajay Matharu
layout: post
guid: http://ajaymatharu.wordpress.com/?p=417
permalink: /set-item-level-permission-in-sharepoint-through-coding/
bte_opp_original_pub_date:
  - 2008-11-07 15:54:21
dsq_thread_id:
  - 465392522
categories:
  - .Net
  - ASP.Net
  - Development
  - Sharepoint
  - Technical
  - Technology
tags:
  - .Net
  - ASP.Net
  - Permissions
  - Sharepoint
  - Sharepoint Permission
---
Here is the way we can add item level permission for a user on an item,
  
SPRoleDefinition oUserRole;
  
SPRoleAssignment oUserRoleAssignment;
  
SPListItem itm;
  
SPSite site = null;
  
SPWeb web = null;
  
string siteUrl = Request.Url.ToString();

site = new SPSite(siteUrl);
  
web = site.OpenWeb();
  
SPGroup grp = web.Groups[groupname];

itm=web.Lists[&#8220;Shared Documents&#8221;].Items[0];

oUserRole = web.RoleDefinitions.GetByType(SPRoleType.Administrator);

oUserRoleAssignment = new SPRoleAssignment(loginName, emailId, userDisplayName, notes);//for user
  
or
  
oUserRoleAssignment = new SPRoleAssignment(grp);//for group

oUserRoleAssignment.RoleDefinitionBindings.Add(oUserRole);
  
itm.RoleAssignments.Add(oUserRoleAssignment);
  
web.AllowUnsafeUpdates = true;
  
itm.Update();
  
web.Update();
  
web.AllowUnsafeUpdates = false;

This is useful for setting item level permission via code.

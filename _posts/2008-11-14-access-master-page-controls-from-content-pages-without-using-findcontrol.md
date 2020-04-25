---
toc: false
id: 447
title: Access Master Page Controls from Content Pages without using FindControl
date: 2008-11-14T14:47:09+00:00
author: Ajay Matharu
layout: post
guid: http://ajaymatharu.wordpress.com/?p=447
permalink: /access-master-page-controls-from-content-pages-without-using-findcontrol/
ljID:
  - 91
dsq_thread_id:
  - 465358356
categories:
  - .Net
  - ASP.Net
  - Development
  - Visual Studio
tags:
  - .Net
  - ASP.Net
  - 'C#.Net'
  - content pages
  - MasterPages
  - MasterType
---
Assume in the master page, we have a user control which we need to access and set its visiblity from content page. We create a public property in the master page called controlVisiblity

public bool LoginControlVisible
  
{
  
get
  
{
  
return LoginControl.Visible;
  
}
  
set
  
{
  
LoginControl.Visible = value;
  
}
  
}

To gain access to the master page file from the content page, you just need to add the below directive to the content page

<%@ MasterType VirtualPath=&#8221;~/siteMaster.master&#8221;%>

When ASP.NET realizes the existance of this directive, it generates a strongly typed property &#8220;Master&#8221;. this property will give you access to the MasterPage file. So directly in the content page code behind you would use the below instead of trying to use the FindControl method.

Master.LoginControlVisible = true;

or

Master.LoginControlVisible = false;

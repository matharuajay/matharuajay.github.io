---
id: 1349
title: 'Impersonation in Sharepoint &#8211; MOSS/WSS'
date: 2009-06-10T10:42:12+00:00
author: Ajay Matharu
layout: post
guid: http://www.ajaymatharu.com/?p=1349
permalink: /impersonation-in-sharepoint-mosswss/
ljID:
  - 252
dsq_thread_id:
  - 465387701
categories:
  - .Net
  - ASP.Net
  - Sharepoint
tags:
  - .Net
  - 'C#.Net'
  - Impersonation
  - Microsoft
  - MOSS
  - Sharepoint
  - Visual Studio
  - vs.net
  - WSS
---
Here is the little code that you can use to impersonate any user in sharepoint. This will code will pretend that you are logged in as the user who is impersonated and will be allowed access to all the features and inherits all the rights for that person. This is mainly used to do something for which the impersonating person has rights and you other user do not have rights.

<pre name="code" class="c-sharp">SPWeb web = SPContext.Current.Web.Site.OpenWeb();
SPUser user = web.AllUsers[username];
SPUserToken userToken = user.UserToken;
SPSite site = new SPSite(SPContext.Current.Web.Site.Url.ToString(), userToken);
web = site.OpenWeb();
</pre>

Here username is the name username of the user who you want to impersonate as.

Hope this helps <img src="http://www.ajaymatharu.com/wp-includes/images/smilies/simple-smile.png" alt=":)" class="wp-smiley" style="height: 1em; max-height: 1em;" />
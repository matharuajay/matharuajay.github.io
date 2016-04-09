---
id: 1177
title: Changing appSettings value in web.config
date: 2009-05-14T10:32:05+00:00
author: Ajay Matharu
layout: post
guid: http://www.ajaymatharu.com/?p=1177
permalink: /changing-appsettings-value-in-webconfig/
aktt_notify_twitter:
  - no
ljID:
  - 233
dsq_thread_id:
  - 465391791
categories:
  - .Net
  - ASP.Net
  - Development
  - Visual Studio
tags:
  - .Net
  - appSettings
  - ASP.Net
  - black vs white
  - Change appSettings value
  - Update Web.config
  - vs.net
  - web.config
---
Following is the simple code to change the value of the appSettings key,

<pre name="code" class="c-sharp">private void UpdateConfig(string strKey, string strValue)
{
Configuration objConfig = WebConfigurationManager.OpenWebConfiguration(”~”); 
AppSettingsSection objAppsettings = (AppSettingsSection)objConfig.GetSection(”appSettings”);
if (objAppsettings != null)
{
objAppsettings.Settings[strKey].Value = strValue; 
objConfig.Save();
}
}
</pre>
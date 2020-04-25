---
toc: false
id: 1051
title: Change SQL Server Account Password
date: 2009-03-14T16:04:40+00:00
author: Ajay Matharu
layout: post
guid: http://www.ajaymatharu.com/?p=1051
permalink: /change-sql-server-account-password/
ljID:
  - 202
dsq_thread_id:
  - 465390111
categories:
  - SQL
tags:
  - Development
  - Microsoft
  - SQL
  - Technical
---
Here is the SQL statement that helps you to change the SQL account password,

[cc lang=&#8221;sql&#8221;]
  
ALTER LOGIN Account_Name WITH
  
PASSWORD = &#8216;New_Password&#8217;
  
OLD\_PASSWORD = &#8216;Old\_Password&#8217;;
  
[/cc]

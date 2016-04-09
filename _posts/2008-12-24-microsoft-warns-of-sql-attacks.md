---
id: 670
title: Microsoft Warns of SQL Attacks
date: 2008-12-24T03:21:48+00:00
author: Ajay Matharu
layout: post
guid: http://ajaymatharu.wordpress.com/?p=670
permalink: /microsoft-warns-of-sql-attacks/
ljID:
  - 135
dsq_thread_id:
  - 465384745
categories:
  - Development
  - Misc
  - SQL
  - Technology
tags:
  - Development
  - Hacking
  - Microsoft
  - SQL
  - SQL 2000
  - SQL 2005
  - SQL Attacks
  - Technology
---
Just days after patching a critical flaw in its Internet Explorer browser, Microsoft is now warning users of a serious bug in its SQL Server database software.

Microsoft issued a security advisory late Monday, saying that the bug could be exploited to run unauthorized software on systems running versions of Microsoft SQL Server 2000 and SQL Server 2005.

Attack code that exploits the bug has been published, but Microsoft said that it has not yet seen this code used in online attacks. Database servers could be attacked using this flaw if the criminals somehow found a way to log onto the system, and Web applications that suffered from relatively common SQL injection bugs could be used as stepping stones to attack the back-end database, Microsoft said.

Desktop users running the Microsoft SQL Server 2000 Desktop Engine or SQL Server 2005 Express could be at risk in some circumstances, Microsoft said.

The bug lies in a stored procedure called &#8220;sp_replwritetovarbin,&#8221; which is used by Microsoft&#8217;s software when it replicates database transactions. It was publicly disclosed on December 9 by SEC Consult Vulnerability Lab, which said it had notified Microsoft of the issue in April.

&#8220;Systems with Microsoft SQL Server 7.0 Service Pack 4, Microsoft SQL Server 2005 Service Pack 3, and Microsoft SQL Server 2008 are not affected by this issue,&#8221; Microsoft said in its advisory.
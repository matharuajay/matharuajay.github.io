---
toc: false
id: 1374
title: Finding a column in database
date: 2009-07-25T12:03:32+00:00
author: Ajay Matharu
layout: post
guid: https://www.ajaymatharu.com/?p=1374
permalink: /finding-a-column-in-database/
bte_opp_original_pub_date:
  - 2009-06-26 12:39:00
dsq_thread_id:
  - 465388904
categories:
  - Development
  - SQL
tags:
  - Development
  - Query
  - SQL
  - System Query
  - System Table
---
Here is the query that will help you to find a particular column in the database. This query will return you the table name in which that column is found.

<pre name="code" class="sql">select so.name, sc.name
from syscolumns sc
inner join sysobjects so on sc.id = so.id
where sc.name = 'SystemColumn'
</pre>

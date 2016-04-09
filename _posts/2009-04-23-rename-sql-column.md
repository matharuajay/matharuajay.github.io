---
id: 973
title: Rename SQL column
date: 2009-04-23T10:06:20+00:00
author: Ajay Matharu
layout: post
guid: http://www.ajaymatharu.com/?p=973
permalink: /rename-sql-column/
aktt_notify_twitter:
  - no
ljID:
  - 222
dsq_thread_id:
  - 465391319
categories:
  - Microsoft
  - SQL
tags:
  - EXEC
  - rename
  - rename column
  - SQL
---
Here is the script to rename an SQL column,

<pre name="code" class="sql">EXEC sp_rename
@objname = 'table_name.old_column_name',
@newname = 'new_column_name',
@objtype = 'COLUMN'
</pre>
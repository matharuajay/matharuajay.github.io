---
toc: false
id: 1371
title: Query to list all tables and columns in database
date: 2009-06-25T10:30:41+00:00
author: Ajay Matharu
layout: post
guid: http://www.ajaymatharu.com/?p=1371
permalink: /query-to-list-all-tables-and-columns-in-database/
ljID:
  - 267
dsq_thread_id:
  - 465387878
categories:
  - Development
  - SQL
tags:
  - Development
  - Query
  - SQL
  - System Tables
---
Here is the SQL query that will help you list all the tables and columns along with its data type and length in a particular database. 

This query fires query to the system table that stores all the information about the database.

<pre name="code" class="sql">select table_name, column_name, data_type, character_maximum_length, is_nullable from information_schema.columns where table_name in (select name from sysobjects where xtype='U') order by table_name
</pre>

Hope this helps, enjoy <img src="http://www.ajaymatharu.com/wp-includes/images/smilies/simple-smile.png" alt=":)" class="wp-smiley" style="height: 1em; max-height: 1em;" />

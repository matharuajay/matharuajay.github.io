---
id: 364
title: Data Scripter Add-in for SQL
date: 2009-07-24T09:34:43+00:00
author: Ajay Matharu
layout: post
guid: http://ajaymatharu.wordpress.com/?p=364
permalink: /data-scripter-add-in-for-sql/
bte_opp_original_pub_date:
  - 2008-11-13 08:35:37
dsq_thread_id:
  - 465392156
categories:
  - SQL
tags:
  - data scripter
  - SQL
  - sql script
  - table data scripter
---
Many a times you feel the need to script databases, tables, stored procedures etc. But you already have these utilities that help you to script these database objects. There is no script generator for the data present in the table. For e.g. you want to move data from one server to another, to accomplish this you have the script generator for table but not for data within it.

There is an Add-on for the SQL Management studio that helps you to generate the Table data scripts. You can download the add-in from <a href="http://www.box.net/shared/gmqsoj5c7p" target="_blank">here</a>.

  * After installing, when you right-click on a table node in Management Studio, you will see a &#8220;Script Data for [table name] option in the menu.
  * Selecting this will bring up a dialog letting you choose a few file options (File, Clipboard, New Query Window) and a few script options. (Disable Constraints, Triggers, etc&#8230;)

This add-in works best for tables with small amounts of data. If you have a large amount of data then you should use the &#8220;Script to File&#8221; option, as you are likely to run out of memory.
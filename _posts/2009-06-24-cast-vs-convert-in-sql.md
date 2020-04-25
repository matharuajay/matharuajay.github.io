---
toc: false
id: 1376
title: Cast Vs Convert in SQL
date: 2009-06-24T16:24:17+00:00
author: Ajay Matharu
layout: post
guid: http://www.ajaymatharu.com/?p=1376
permalink: /cast-vs-convert-in-sql/
ljID:
  - 266
dsq_thread_id:
  - 465383950
categories:
  - Development
  - SQL
tags:
  - Cast
  - Cast Vs Convert
  - Convert
  - Development
  - SQL
  - SQL 2005
  - SQl Datatype
  - SQL Query
---
Because SQL Server provides both functions, there may be some confusion about which is best to use and under what circumstances. CONVERT is specific to SQL Server, and allows for a greater breadth of flexibility when converting between date and time values, fractional numbers, and monetary signifier.

CAST is the more ANSI-standard of the two functions, meaning that while it&#8217;s more portable (i.e., a function that uses CAST can be used in other database applications more or less as-is), it&#8217;s also less powerful. CAST is also required when converting between decimal and numeric values to preserve the number of decimal places in the original expression. For those reasons, it&#8217;s best to use CAST first, unless there is some specific thing that only CONVERT can provide in the work you&#8217;re doing.

CAST and CONVERT can also be used in conjunction with each other to achieve certain effects. For instance, a typical way to produce a char variable with the current date would be to use:

<pre class="sql">SELECT CONVERT(CHAR(10), CURRENT_TIMESTAMP, 102)</pre>

(The 102 indicates that the ANSI date format, yy.mm.dd, is to be used.)

However, if you wanted to cast this variable explicitly as a datetime or smalldatetime value for compatibility in a specific database column, you could use:

<pre class="sql">SELECT CAST(CONVERT(CHAR(10),CURRENT_TIMESTAMP,102) AS DATETIME)</pre>

This would return the value yy.mm.dd 00:00:00 (i.e., 12:00AM as the timestamp; the time information from CURRENT_TIMESTAMP would be discarded).

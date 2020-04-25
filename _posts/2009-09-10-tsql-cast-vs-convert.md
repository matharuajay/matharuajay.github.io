---
toc: false
id: 663
title: TSQL Cast Vs Convert
date: 2009-09-10T11:02:43+00:00
author: Ajay Matharu
layout: post
guid: http://ajaymatharu.wordpress.com/?p=663
permalink: /tsql-cast-vs-convert/
dsq_thread_id:
  - 465387714
categories:
  - Development
  - SQL
tags:
  - Cast
  - Convert
  - Convert Vs Cast
  - SQL
  - TSQL
---
<span class="a3">SQL Server programmers can choose between two functions in SQL Server 7 and 2000 for converting expressions from one type to another. In many cases there will be a need within a stored procedure or other routine to convert data from, say, a <strong>datetime</strong> type to a <strong>varchar</strong> type; <strong>CONVERT</strong> and <strong>CAST</strong> are used for such things.</p> 

<p>
  Because SQL Server provides both functions, there may be some confusion about which is best to use and under what circumstances. <strong>CONVERT</strong> is specific to SQL Server, and allows for a greater breadth of flexibility when converting between date and time values, fractional numbers, and monetary signifiers.
</p>

<p>
  <strong>CAST</strong> is the more ANSI-standard of the two functions, meaning that while it&#8217;s more portable (i.e., a function that uses <strong>CAST</strong> can be used in other database applications more or less as-is), it&#8217;s also less powerful. <strong>CAST</strong> is also required when converting between <strong>decimal</strong> and <strong>numeric</strong> values to preserve the number of decimal places in the original expression. For those reasons, it&#8217;s best to use <strong>CAST</strong> first, unless there is some specific thing that only <strong>CONVERT</strong> can provide in the work you&#8217;re doing.
</p>

<p>
  <strong>CAST</strong> and <strong>CONVERT</strong> can also be used in conjunction with each other to achieve certain effects. For instance, a typical way to produce a <strong>char</strong> variable with the current date would be to use:
</p>

<pre>SELECT CONVERT(CHAR(10), CURRENT_TIMESTAMP, 102)</pre>

<p>
  (The <strong>102</strong> indicates that the ANSI date format, <em>yy.mm.dd</em>, is to be used.)
</p>

<p>
  However, if you wanted to cast this variable explicitly as a <strong>datetime</strong> or <strong>smalldatetime</strong> value for compatibility in a specific database column, you could use:
</p>

<pre>SELECT CAST(CONVERT(CHAR(10),CURRENT_TIMESTAMP,102) AS DATETIME</pre>

<p>
  This would return the value <em>yy.mm.dd</em> 00:00:00 (i.e., 12:00AM as the timestamp; the time information from <strong>CURRENT_TIMESTAMP</strong> would be discarded).
</p>

<p>
  </span>
</p>

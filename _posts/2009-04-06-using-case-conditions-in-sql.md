---
id: 1115
title: Using case conditions in SQL
date: 2009-04-06T10:28:43+00:00
author: Ajay Matharu
layout: post
guid: http://www.ajaymatharu.com/?p=1115
permalink: /using-case-conditions-in-sql/
aktt_notify_twitter:
  - no
ljID:
  - 213
dsq_thread_id:
  - 465387581
categories:
  - Development
  - SQL
tags:
  - Case
  - Select
  - SQL
---
This is how you can user select case in sql statements, 

<pre name="code" class="sql">USE AdventureWorks;
GO
SELECT   ProductNumber, Category =
CASE ProductLine
WHEN 'R' THEN 'Road'
WHEN 'M' THEN 'Mountain'
WHEN 'T' THEN 'Touring'
WHEN 'S' THEN 'Other sale items'
ELSE 'Not for sale'
END,
Name
FROM Production.Product
ORDER BY ProductNumber;
GO
</pre>

<pre name="code" class="sql">USE AdventureWorks;
GO
SELECT   ProductNumber, Name, 'Price Range' =
CASE
WHEN ListPrice =  0 THEN 'Mfg item - not for resale'
WHEN ListPrice &lt; 50 THEN 'Under $50'
WHEN ListPrice &gt;= 50 and ListPrice &lt; 250 THEN 'Under $250'
WHEN ListPrice &gt;= 250 and ListPrice &lt; 1000 THEN 'Under $1000'
ELSE 'Over $1000'
END
FROM Production.Product
ORDER BY ProductNumber ;
GO
</pre>

this is similar to if condition that you use in any other programming language but this you can use within a query to check the value and perform the respective task.
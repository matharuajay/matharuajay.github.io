---
toc: false
id: 1367
title: Find out Nth highest value in SQL
date: 2009-06-21T13:51:52+00:00
author: Ajay Matharu
layout: post
guid: https://www.ajaymatharu.com/?p=1367
permalink: /find-out-nth-highest-value-in-sql/
ljID:
  - 263
dsq_thread_id:
  - 465390325
categories:
  - Development
  - Microsoft
  - SQL
tags:
  - Development
  - Microsoft
  - Nth highest
  - Query
  - SQL
  - SQL 2005
---
Since I am looking for a job change and this is the question I&#8217;m being asked in all of my interviews, I am sharing this with everyone hoping this will help you guys.

The most common type of question is find out the 5th highest value, find out the 2nd highest value, and so on.

The solution for this question goes like this, I am going to fetch 5th highest salary for an employee.

<pre name="code" class="sql">Select top 1 FirstName, Salary From Employees Where Salary Not In (Select Distinct Top 4 Salary From Employees order by Salary desc) order by Salary desc
</pre>

Enjoy and have fun 

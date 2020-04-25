---
toc: false
id: 2194
title: SQL Query to calculate top nth salary Interview Question
date: 2010-03-29T10:40:11+00:00
author: Ajay Matharu
layout: post
guid: http://www.ajaymatharu.com/?p=2194
permalink: /sql-query-to-calculate-top-nth-salary-interview-question/
aktt_notify_twitter:
  - no
dsq_thread_id:
  - 465387225
categories:
  - SQL
tags:
  - finding nth highest
  - finding nth highest salary in sql
  - finding salary
  - SQL Query
---
Previously I have written a post on [Find out Nth highest value in SQL](../find-out-nth-highest-value-in-sql/ "How to find nth highest value in SQL") but that is not a good solution. You should try to avoid using &#8220;In&#8221; clause in your queries. The &#8220;In&#8221; clause uses lot of memory and should be avoided. So this post tells how to do the same using &#8220;Joins&#8221; rather than &#8220;In&#8221; clause.

The below query will fetch the 3rd highest salary,

<pre name="code" class="sql">select top 1 e.firstname, e.lastname, e.salary from employees e
left outer join (select top 2 employeeid from employees order by salary desc) b on e.employeeid=b.employeeid where b.employeeid is null
order by e.salary desc
</pre>



If you want to fetch some other number change the &#8220;2&#8221; in the following line in the above query

<pre name="code" class="sql">(select top 2 employeeid from employees order by salary desc) b
</pre>



If you know a better way, please let us know.
  
Hope this helps <img src="http://www.ajaymatharu.com/wp-includes/images/smilies/simple-smile.png" alt=":)" class="wp-smiley" style="height: 1em; max-height: 1em;" />

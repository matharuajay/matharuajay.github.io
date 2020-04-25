---
toc: false
id: 2199
title: Using IF UPDATE() in SQL Trigger
date: 2010-03-30T11:35:10+00:00
author: Ajay Matharu
layout: post
guid: https://www.ajaymatharu.com/?p=2199
permalink: /using-if-update-in-sql-trigger/
aktt_notify_twitter:
  - no
dsq_thread_id:
  - 465386605
categories:
  - SQL
tags:
  - if update in trigger
  - if update() in sql trigger
  - sql trigger
  - Update function in sql
---
At times you have to update a particular record only when particular field has been updated. In that case you don&#8217;t necessary have to handle that on front end, you can handle that in SQL as well.

If you have a SQL Trigger and you need to make sure SQL Trigger fires only if value of particular field/column has been modified then you can use &#8220;IF UPDATE()&#8221; in trigger.

Following is the syntax of using the &#8220;IF UPDATE()&#8221; in SQL trigger,

<pre name="code" class="sql">create trigger trgUpdate 
on employees 
for update 
As 
Begin 
    if update (Dept) 
    Begin 
        update employees 
        set updated=1 
        where id=(select id from inserted) 
    End 
End 
</pre>



The following line check if the Dept of particular employee has been updated, If it has, then only it executes the further query,

<pre name="code" class="sql">if update (Dept) 
</pre>

Hope this helps <img src="https://www.ajaymatharu.com/wp-includes/images/smilies/simple-smile.png" alt=":)" class="wp-smiley" style="height: 1em; max-height: 1em;" />

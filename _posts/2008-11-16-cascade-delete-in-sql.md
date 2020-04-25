---
toc: false
id: 451
title: Cascade Delete in SQL
date: 2008-11-16T07:28:47+00:00
author: Ajay Matharu
layout: post
guid: https://ajaymatharu.wordpress.com/?p=451
permalink: /cascade-delete-in-sql/
ljID:
  - 92
dsq_thread_id:
  - 465389675
categories:
  - Development
  - SQL
tags:
  - Cascade delete
  - SQL
  - sql script
  - TSQL
---
Many a times you need to delete the record but at the same time you need to make sure all the related or referenced records are also deleted. This is because you can not delete a record if it is referenced in another table. In this case you can either delete the referenced record or you can set the &#8220;Cascade Delete On&#8221;.

Here is the code to implement cascade delete in SQL

ALTER TABLE B  ADD (
  
CONSTRAINT FK\_1 FOREIGN KEY (PARENT\_ID)
  
REFERENCES A ([ID](void(0)){.tfTextLink}) ON DELETE CASCADE)

This code will delete all the referenced records on deletion of primary record. You can use this because deleting the referenced records becomes very tedious at times.

Similar to Cascade Delete there is also Cascade Update. For that stay tuned for my next post :).

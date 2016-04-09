---
id: 1175
title: Insert multiple records with single Insert statement in SQL
date: 2009-09-08T10:31:26+00:00
author: Ajay Matharu
layout: post
guid: http://www.ajaymatharu.com/?p=1175
permalink: /insert-multiple-records-with-single-insert-statement-in-sql/
aktt_notify_twitter:
  - no
dsq_thread_id:
  - 465390902
categories:
  - Development
  - SQL
tags:
  - Insert
  - Microsoft SQL
  - Multiple Inserts
  - Multiple Records
  - Query
  - Select
  - SQL
  - SQL Insert
  - SQL Query
  - TSQL Query
---
This is the traditional method for inserting multiple values in a table. 

<pre name="code" class="sql">USE YourDBName
GO
INSERT INTO MyTableName (FirstCol, SecondCol)
VALUES (‘First’,1);
INSERT INTO MyTableName (FirstCol, SecondCol)
VALUES (‘Second’,2);
INSERT INTO MyTableName (FirstCol, SecondCol)
VALUES (‘Third’,3);
INSERT INTO MyTableName (FirstCol, SecondCol)
VALUES (‘Fourth’,4);
INSERT INTO MyTableName (FirstCol, SecondCol)
VALUES (‘Fifth’,5);
GO
</pre>

However this cannot be used if you want to insert multiple values into the table via your code because in this case you&#8217;ll have to write the code to insert the value in the DB in a for loop which is not at all feasible.

So you can write the code to generate the insert statement like,

<pre name="code" class="sql">USE YourDB
GO
INSERT INTO MyTableName (FirstCol, SecondCol)
SELECT ‘First’ ,1
UNION ALL
SELECT ‘Second’ ,2
UNION ALL
SELECT ‘Third’ ,3
UNION ALL
SELECT ‘Fourth’ ,4
UNION ALL
SELECT ‘Fifth’ ,5
GO
</pre>

The above code inserts multiple values into DB with a single SQL insert query. This is the best means to use in your code as you&#8217;ll just have to create this query in your for loop and the query will run only once.

Also you can use the following query syntax for multiple inserts in SQL 2008

<pre name="code" class="sql">USE YourDB
GO
INSERT INTO MyTableName (FirstCol, SecondCol)
VALUES (‘First’,1),
(‘Second‘,2),
(‘Third‘,3),
(‘Fourth‘,4),
(‘Fifth‘,5)

</pre>

Please let me know if you have any better ideas than this one.
  
Njoy coding!!!
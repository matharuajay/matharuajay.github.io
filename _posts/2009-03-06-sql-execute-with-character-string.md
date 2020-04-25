---
toc: false
id: 844
title: SQL Execute with character string
date: 2009-03-06T14:18:55+00:00
author: Ajay Matharu
layout: post
guid: https://ajaymatharu.wordpress.com/?p=844
permalink: /sql-execute-with-character-string/
ljID:
  - 197
dsq_thread_id:
  - 465388960
categories:
  - Development
  - Microsoft
  - SQL
  - Technical
  - Technology
tags:
  - EXEC
  - Execute
  - Microsoft
  - SQL
  - SQL Exec
  - SQL Execute
  - String Execute
  - Technology
  - TSQL
---
Today I just got went though this, this helps you to execute a string in SQL. This is how you can execute a string in SQL,

Declare @query Varchar(500)

Set @query = &#8216;Select * From Employees&#8217;

Exec (@query)

OR

EXEC (&#8216;USE AdventureWorks; SELECT EmployeeID, Title FROM HumanResources.Employee;&#8217;)

This way you can execute a string in SQL.

This is extremely helpful when you need to add the Where clause based on some criteria. You can have your query in a string and based on that criteria you can append the clause in that string and finally execute the string at the end. This works perfectly.

However this does not work if you want to execute the query and get the result in the Dataset in your .Net application. For that you need to create a #Temp table execute the string and get the result in the #Temp table and then fire the select again on your #Temp table.

Note: Don&#8217;t forget to get the brackets ( & ) around your query else SQL will throw an error, Unrecognized stored procedure.

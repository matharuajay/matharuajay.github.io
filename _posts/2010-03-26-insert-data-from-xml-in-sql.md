---
toc: false
id: 2188
title: Insert data from XML in SQL
date: 2010-03-26T10:56:37+00:00
author: Ajay Matharu
layout: post
guid: https://www.ajaymatharu.com/?p=2188
permalink: /insert-data-from-xml-in-sql/
aktt_notify_twitter:
  - no
dsq_thread_id:
  - 465391956
categories:
  - Microsoft
  - SQL
tags:
  - Insert xml in sql
  - Multiple Records
  - OpenXML
  - SQL
  - SQL with XML
  - xml format
  - XML in SQL
  - XML with SQL
---
Its been very long since I have written any technical post. So here I am, with small example of how to insert data from XML into SQL. This is extremely helpful if you want to insert multiple records in one go into SQL, you just need to create the XML and pass it to SQL. SQL will fetch the data from the XML and save it into its tables you have mapped.

Just to demonstrate I am creating a sample table. Since it is sample I have not created any Primary Key on it.

<pre class="sql" name="code">CREATE TABLE [dbo].[Employees](
	[EmpId] [int] NOT NULL,
	[FirstName] [varchar](50) NULL,
	[Dept] [varchar](50) NULL
)
</pre>

Once table has been created you are ready to insert data into it,

<pre class="sql" name="code">declare @TestDoc int
declare @TestDoc int
exec sp_xml_preparedocument @TestDoc output,
N'&lt;Root>
&lt;Employees Dept="Marketing">
&lt;Employee EmpID="1231" FirstName="Ethan">&lt;/Employee>
&lt;Employee EmpID="1232" FirstName="Ashish">&lt;/Employee>
&lt;/Employees>
&lt;Employees Dept="IT">
&lt;Employee EmpID="1241" FirstName="Ajay">&lt;/Employee>
&lt;Employee EmpID="1242" FirstName="Rahul">&lt;/Employee>
&lt;/Employees>
&lt;Employees Dept="DBA">
&lt;Employee EmpID="1251" FirstName="AJ">&lt;/Employee>
&lt;Employee EmpID="1251" FirstName="Nilesh">&lt;/Employee>
&lt;/Employees>
&lt;/Root>'
insert into employees(empid, firstname, dept)
select empid, firstname, dept
from openxml(@TestDoc, N'/Root/Employees/Employee')
With (EmpId varchar(5) '@EmpID',
    FirstName varchar(10) '@FirstName',
    Dept varchar(10) '../@Dept')
exec sp_xml_removedocument @TestDoc
</pre>

Alternatively, you can change your XML format like this,

<pre class="sql" name="code">declare @TestDoc int
exec sp_xml_preparedocument @TestDoc output,
N'&lt;Root>
&lt;Employees Dept="Marketing">
&lt;Employee EmpID="1231">Ethans&lt;/Employee>
&lt;Employee EmpID="1232">Ajay&lt;/Employee>
&lt;/Employees>
&lt;Employees Dept="IT">
&lt;Employee EmpID="1241">Rahul&lt;/Employee>
&lt;Employee EmpID="1242">Sneha&lt;/Employee>
&lt;/Employees>
&lt;Employees Dept="DBA">
&lt;Employee EmpID="1251">Nilesh&lt;/Employee>
&lt;Employee EmpID="1251">Matharu&lt;/Employee>
&lt;/Employees>
&lt;/Root>'
select *
from openxml(@TestDoc, N'/Root/Employees/Employee')
With (EmpId varchar(5) '@EmpID',
    FirstName varchar(10) '.',
    Dept varchar(10) '../@Dept')
exec sp_xml_removedocument @TestDoc
</pre>



If you want to fetch your existing data from SQL in XML format,
  
With values as attributes,

<pre class="sql" name="code">select * from employees
for xml auto
</pre>

<div id="attachment_2189" style="width: 574px" class="wp-caption aligncenter">
  <img class="size-full wp-image-2189" title="Output Data as Attributes" src="https://www.ajaymatharu.com/wp-content/uploads/2010/03/Data-as-attribute.png" alt="Output Data as Attributes" width="564" height="119" srcset="https://www.ajaymatharu.com/wp-content/uploads/2010/03/Data-as-attribute-300x63.png 300w, https://www.ajaymatharu.com/wp-content/uploads/2010/03/Data-as-attribute.png 564w" sizes="(max-width: 564px) 100vw, 564px" />
  
  <p class="wp-caption-text">
    Output Data as Attributes
  </p>
</div>


  

  
With values as elements,

<pre class="sql" name="code">select * from employees
for xml auto, elements
</pre>

<div id="attachment_2190" style="width: 319px" class="wp-caption aligncenter">
  <img class="size-full wp-image-2190" title="Output Data as Elements" src="https://www.ajaymatharu.com/wp-content/uploads/2010/03/data-as-elements.png" alt="Output Data as Elements" width="309" height="519" />
  
  <p class="wp-caption-text">
    Output Data as Elements
  </p>
</div>

---
toc: false
id: 361
title: Which SQL Statements Are Currently Executing
date: 2008-11-11T15:20:47+00:00
author: Ajay Matharu
layout: post
guid: https://ajaymatharu.wordpress.com/?p=361
permalink: /which-sql-statements-are-currently-executing/
ljID:
  - 88
dsq_thread_id:
  - 465390528
categories:
  - SQL
tags:
  - SQL
  - sql utility
  - Stored procedure
---
sp_who2 is a well known utility that shows what spids are currently executing. However the information it shows is relatively limited. For example, it only shows the type of command executing as SELECT, DELETE etc, with no reference to the actual underlying SQL executing.

Knowing what SQL is executing can be vital in debugging why a query is taking a long time, or determining if it is being blocked. It can also be useful in showing the progress of a stored procedure i.e. what statement within the stored procedure is currently executing.

The utility makes use of Dynamic Management Views (DMVs)

The Dynamic Management View (DMV) sys.db\_exec\_requests shows which requests are currently executing, the information shown includes the handle to the whole SQL text of the batch or stored procedure (sql\_handle), together with offsets relating to the section of SQL within the batch that is currently executing (statement\_start\_offset and statement\_end_offset).

To determine the current section of SQL currently executing, we need to call the Dynamic Management Function (DMF) sys.dm\_exec\_sql_text, passing in the handle of the SQL batch that is currently executing, and then apply the relevant offsets.

We can get more information about the query by combining the sys.db\_exec\_requests DMV with the sys.processes system view (joined on spid/session_id). This information includes who is executing the query, the machine they are running from, and the name of the database.

The utility selects relevant fields from the sys.db\_exec\_requests and sys.sysprocesses views. The selected fields are described here.

<table border="1" cellspacing="0" cellpadding="0" width="100%">
  <tr>
    <td>
      <strong>Column name</strong>
    </td>
    
    <td>
      <strong>Data type</strong>
    </td>
    
    <td>
      <strong>Description</strong>
    </td>
  </tr>
  
  <tr>
    <td>
      <strong>spid</strong>
    </td>
    
    <td>
      smallint
    </td>
    
    <td>
      SQL Server process ID.
    </td>
  </tr>
  
  <tr>
    <td>
      <strong>ecid</strong>
    </td>
    
    <td>
      smallint
    </td>
    
    <td>
      Execution context ID used to uniquely identify the subthreads operating on behalf of a single process.
    </td>
  </tr>
  
  <tr>
    <td>
      <strong>dbid</strong>
    </td>
    
    <td>
      smallint
    </td>
    
    <td>
      ID of the database currently being used by the process.
    </td>
  </tr>
  
  <tr>
    <td>
      <strong>nt_username</strong>
    </td>
    
    <td>
      nchar(128)
    </td>
    
    <td>
      Windows user name for the process, if using Windows Authentication, or a trusted connection.
    </td>
  </tr>
  
  <tr>
    <td>
      <strong>status</strong>
    </td>
    
    <td>
      nchar(30)
    </td>
    
    <td>
      Process ID status. For example, running and sleeping.
    </td>
  </tr>
  
  <tr>
    <td>
      <strong>wait_type</strong>
    </td>
    
    <td>
      bigint
    </td>
    
    <td>
      Current wait time in milliseconds.
    </td>
  </tr>
  
  <tr>
    <td>
      <strong>Individual Query</strong>
    </td>
    
    <td>
      varchar
    </td>
    
    <td>
      SQL Statement currently running.
    </td>
  </tr>
  
  <tr>
    <td>
      <strong>Parent Query</strong>
    </td>
    
    <td>
      varchar
    </td>
    
    <td>
      Routine that contains the Individual Query.
    </td>
  </tr>
  
  <tr>
    <td>
      <strong>program_name</strong>
    </td>
    
    <td>
      nchar(128)
    </td>
    
    <td>
      Name of the application program.
    </td>
  </tr>
  
  <tr>
    <td>
      <strong>Hostname</strong>
    </td>
    
    <td>
      nchar(128)
    </td>
    
    <td>
      Name of the workstation.
    </td>
  </tr>
  
  <tr>
    <td>
      <strong>nt_domain</strong>
    </td>
    
    <td>
      nchar(128)
    </td>
    
    <td>
      Microsoft Windows domain for the client, if using Windows Authentication, or a trusted connection.
    </td>
  </tr>
  
  <tr>
    <td>
      <strong>Start_time</strong>
    </td>
    
    <td>
      datetime
    </td>
    
    <td>
      Time when the request is scheduled to run.
    </td>
  </tr>
</table>

Utility :

CREATE PROC [dbo].[dba_WhatSQLIsExecuting]
  
AS
  
/*&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8211;
  
Purpose: Shows what individual SQL statements are currently executing.
  
&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;-

Example Usage:
  
1. exec YourServerName.master.dbo.dba_WhatSQLIsExecuting
  
&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;*/
  
BEGIN
  
&#8212; Do not lock anything, and do not get held up by any locks.
  
SET TRANSACTION ISOLATION LEVEL READ UNCOMMITTED

&#8212; What SQL Statements Are Currently Running?
  
SELECT [Spid] = session_Id
  
, ecid
  
, [Database] = DB_NAME(sp.dbid)
  
, [User] = nt_username
  
, [Status] = er.status
  
, [Wait] = wait_type
  
, [Individual Query] = SUBSTRING (qt.text,
  
er.statement\_start\_offset/2,
  
(CASE WHEN er.statement\_end\_offset = -1
  
THEN LEN(CONVERT(NVARCHAR(MAX), qt.text)) * 2
  
ELSE er.statement\_end\_offset END &#8211;
  
er.statement\_start\_offset)/2)
  
,[Parent Query] = qt.text
  
, Program = program_name
  
, Hostname
  
, nt_domain
  
, start_time
  
FROM sys.dm\_exec\_requests er
  
INNER JOIN sys.sysprocesses sp ON er.session_id = sp.spid
  
CROSS APPLY sys.dm\_exec\_sql\_text(er.sql\_handle)as qt
  
WHERE session_Id > 50              &#8212; Ignore system spids.
  
AND session_Id NOT IN (@@SPID)     &#8212; Ignore this current statement.
  
ORDER BY 1, 2
  
END

This utility allows you to observe the progress of a stored procedure or SQL batch, additionally it can be used to identify the cause of a long running query or blocking query.

Since the utility uses existing data held in DMVs it is relatively non-intrusive and should have little affect on performance.

If the identified queries are long running or causing blocking, it might be worthwhile running them inside the Database Tuning Advisor (DTA), this might identify the cause of the slow running (e.g. a missing index).

For more information visit : <https://www.sqlservercentral.com/articles/DMV/64425/>

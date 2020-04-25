---
toc: false
id: 978
title: Debug SQL Server (Stored Procedures or Functions)
date: 2009-03-02T10:08:26+00:00
author: Ajay Matharu
layout: post
guid: https://www.ajaymatharu.com/?p=978
permalink: /debug-sql-server-stored-procedures-or-functions/
ljID:
  - 194
dsq_thread_id:
  - 465383876
categories:
  - .Net
  - Development
  - SQL
  - Technology
  - Visual Studio
tags:
  - .Net
  - Breakpoints
  - Database
  - Debug
  - Execute
  - Management
  - Microsoft
  - SQL
  - Stored procedure
  - Technology
  - Visual Studio
  - Visual Studio Tip
  - Visual Studio Tip Of Week
  - Visual Studio tips
  - vs.net
---
SQL <a name="visualstudiohks-CHP-5-ITERM-2858"></a><a name="visualstudiohks-CHP-5-ITERM-2859"></a>statements <a name="visualstudiohks-CHP-5-ITERM-2860"></a>can be difficult to diagnose and debug. SQL Server does not include any default way to debug and step through a stored procedure, but Visual Studio does. Using the Server Explorer, you can step through the execution of a stored procedure or function right inside of Visual Studio. The first step is to open the Server Explorer and create a data connection to your database.

You will then see the stored procedures and functions of your database listed in the Server Explorer.

<img class="aligncenter" title="Step 1" src="https://ajaymatharu.files.wordpress.com/2009/03/stp1.png?w=311&h=330" alt="" width="222" height="185" />

From the Server Explorer, you can right-click on a stored procedure or function and you will see a menu item named Step Into Stored Procedure,

<p style="text-align: left;">
  <img class="aligncenter" title="Step 2" src="https://ajaymatharu.files.wordpress.com/2009/03/stp2.png?w=311&h=330" alt="" width="222" height="185" />
</p>

<p style="text-align: left;">
  When you select Step Into Stored Procedure, you will see the Run Stored Procedure dialog,
</p>

<p style="text-align: left;">
  <img class="aligncenter" title="Step 3" src="https://ajaymatharu.files.wordpress.com/2009/03/stp3.png?w=311&h=330" alt="" width="311" height="146" />After specifying the values for any parameters the stored procedure has, click the OK button. Visual Studio will now execute the stored procedure and open it in the document window, stopping in the first line of execution.
</p>

<p style="text-align: left;">
  You can now step through the stored procedure as it executes. You can set breakpoints just as you would in normal code—the only limitation is that you can specify only location and hit count breakpoints.
</p>

<p class="docText">
  Because T-SQL is inherently different than .NET languages, the debugging experience is a little bit different. Here are some of the limitations with SQL debugging:
</p>

  * <p class="docList">
      You can use only location and hit count breakpoints in T-SQL stored procedures and functions.
    </p>

  * <p class="docList">
      You cannot use Step Into to step from .NET managed code to T-SQL. You can set breakpoints in the stored procedure though, and the debugger will break when it comes across them.
    </p>

  * <p class="docList">
      You cannot use Break while a SQL statement is already running.
    </p>

  * <p class="docList">
      You can&#8217;t use the Set Next Statement function as you might in managed code.
    </p>

<p class="docText">
  Some other differences are the facts that you can&#8217;t use the memory or registers windows, as they just don&#8217;t apply to SQL. Unfortunately, SQL Print statements are not shown in the output window either.
</p>

<p class="docText">
  You cannot run triggers directly, but you can set <a name="visualstudiohks-CHP-5-ITERM-2861"></a>breakpoints in triggers, and if they are triggered, Visual Studio will break into their execution on those breakpoints.<a name="visualstudiohks-CHP-5-ITERM-2862"></a>
</p>

<p style="text-align: left;">

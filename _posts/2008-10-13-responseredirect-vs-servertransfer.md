---
id: 201
title: Response.Redirect VS Server.Transfer
date: 2008-10-13T05:22:04+00:00
author: Ajay Matharu
layout: post
guid: http://ajaymatharu.wordpress.com/?p=201
permalink: /responseredirect-vs-servertransfer/
ljID:
  - 40
dsq_thread_id:
  - 465358062
categories:
  - .Net
  - ASP.Net
tags:
  - Response.Redirect
  - Server.Transfer
---
<span style="font-family:Verdana,Arial,Helvetica;"><span style="text-decoration:underline;">Response.Redirect</span> simply sends a message down to the browser, telling it to move to another page. So, you may run code like: </span>

<pre><span style="font-family:Verdana,Arial,Helvetica;">Response.Redirect("Form2.aspx")</span></pre>

<span style="font-family:Verdana,Arial,Helvetica;">or</span>

<pre><span style="font-family:Verdana,Arial,Helvetica;">Response.Redirect("http://www.yahoo.com/")</span></pre>

<span style="font-family:Verdana,Arial,Helvetica;">to send the user to another page.</span>

<span style="font-family:Verdana,Arial,Helvetica;"><span style="text-decoration:underline;">Server.Transfer</span> is similar in that it sends the user to another page with a statement such as <span style="text-decoration:underline;">Server.Transfer(&#8220;Form2.aspx&#8221;)</span>. However, the statement has a number of distinct advantages and disadvantages.</span>

<span style="font-family:Verdana,Arial,Helvetica;">Firstly, transferring to another page using <span style="text-decoration:underline;">Server.Transfer</span> conserves server resources. Instead of telling the browser to redirect, it simply changes the &#8220;focus&#8221; on the Web server and transfers the request. This means you don&#8217;t get quite as many HTTP requests coming through, which therefore eases the pressure on your Web server and makes your applications run faster.</span>

<span style="font-family:Verdana,Arial,Helvetica;">But watch out: because the &#8220;transfer&#8221; process can work on only those sites running on the server, you can&#8217;t use <span style="text-decoration:underline;">Server.Transfer</span> to send the user to an external site. <span style="text-decoration:underline;">Only Response.Redirect</span> can do that.</span>

<span style="font-family:Verdana,Arial,Helvetica;">Secondly, <span style="text-decoration:underline;">Server.Transfer</span> maintains the original URL in the browser. This can really help streamline data entry techniques, although it may make for confusion when debugging.</span>

<span style="font-family:Verdana,Arial,Helvetica;">That&#8217;s not all: The <span style="text-decoration:underline;">Server.Transfer</span> method also has a second parameter—&#8221;preserveForm&#8221;. If you set this to <span style="text-decoration:underline;">True</span>, using a statement such as <span style="text-decoration:underline;">Server.Transfer(&#8220;Form2.aspx&#8221;, True)</span>, the existing query string and any form variables will still be available to the page you are transferring to.</span>

<span style="font-family:Verdana,Arial,Helvetica;">For example, if your WebForm1.aspx has a TextBox control called TextBox1 and you transferred to WebForm2.aspx with the <span style="text-decoration:underline;">preserveForm</span> parameter set to <span style="text-decoration:underline;">True</span>, you&#8217;d be able to retrieve the value of the original page TextBox control by referencing <span style="text-decoration:underline;">Request.Form(&#8220;TextBox1&#8221;)</span>.</span>

<span style="font-family:Verdana,Arial,Helvetica;">This technique is great for wizard-style input forms split over multiple pages. But there&#8217;s another thing you&#8217;ll want to watch out for when using the <span style="text-decoration:underline;">preserveForm</span> parameter. ASP.NET has a bug whereby, in certain situations, an error will occur when attempting to transfer the form and query string values. You&#8217;ll find this documented at <a href="http://support.microsoft.com/default.aspx?id=kb;en-us;Q316920" target="new">http://support.microsoft.com/default.aspx?id=kb;en-us;Q316920</a>.</span>

<span style="font-family:Verdana,Arial,Helvetica;">The unofficial solution is to set the <span style="text-decoration:underline;">enableViewStateMac</span> property to <span style="text-decoration:underline;">True</span> on the page you&#8217;ll be transferring to, then set it back to <span style="text-decoration:underline;">False</span>. This records that you want a definitive <span style="text-decoration:underline;">False</span> value for this property and resolves the bug.</span>

<span style="font-family:Verdana,Arial,Helvetica;">So, in brief: <span style="text-decoration:underline;">Response.Redirect</span> simply tells the browser to visit another page. <span style="text-decoration:underline;">Server.Transfer</span> helps reduce server requests, keeps the URL the same and, with a little bug-bashing, allows you to transfer the query string and form variables.</span>
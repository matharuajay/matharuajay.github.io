---
toc: false
id: 494
title: 'Extract Method &#8211; Tip of week #11'
date: 2008-12-01T12:44:23+00:00
author: Ajay Matharu
layout: post
guid: http://ajaymatharu.wordpress.com/?p=494
permalink: /extract-method-tip-of-week-11/
ljID:
  - 105
dsq_thread_id:
  - 465358448
categories:
  - .Net
  - Development
  - Tip of Week
  - Visual Studio
tags:
  - .Net
  - Extract Method
  - Extract Method in Visual Studio
  - Tip of Week
  - Visual Studio
  - Visual Studio Tip
  - Visual Studio Tip Of Week
  - vs.net
---
Refactoring is very essential part of coding. You need to refactor your code, to give optimal result. Visual Studio have an inbuilt option for refactoring your code. Right click &#8211; Refactor, today I am going to talk about Extract Method.

Suppose this is my sample code, althogh not good but just to demonstrate.

<div style="font-family:Courier New;font-size:10pt;color:black;background:white;">
  <p style="margin:0;">
    <span style="color:#2b91af;">   27</span> <span style="color:blue;">public</span> <span style="color:blue;">void</span> fillControl()
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   28</span>     {
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   29</span>         <span style="color:blue;">try</span>
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   30</span>         {
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   31</span>             <span style="color:#2b91af;">OleDbDataAdapter</span> adapter;
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   32</span>             <span style="color:#2b91af;">DataSet</span> dataset;
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   33</span>             <span style="color:#2b91af;">OleDbConnection</span> conn;
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   34</span> 
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   35</span>             conn = <span style="color:blue;">new</span> <span style="color:#2b91af;">OleDbConnection</span>();
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   36</span>             conn.ConnectionString = <span style="color:#a31515;">&#8220;PROVIDER=MICROSOFT.Jet.Oledb.4.0;Data Source=&#8221;</span> + Server.MapPath(<span style="color:#a31515;">&#8220;mydatabase.mdb&#8221;</span>);
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   37</span> 
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   38</span>             <span style="color:blue;">string</span> sqlQuery = <span style="color:#a31515;">&#8220;SELECT * from employee&#8221;</span>;
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   39</span>             adapter = <span style="color:blue;">new</span> <span style="color:#2b91af;">OleDbDataAdapter</span>(sqlQuery, conn);
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   40</span>             dataset = <span style="color:blue;">new</span> <span style="color:#2b91af;">DataSet</span>();
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   41</span>             adapter.Fill(dataset);
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   42</span> 
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   43</span>             datagrid1.DataSource = dataset;
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   44</span>             datagrid1.DataBind();
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   45</span>         }
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   46</span>         <span style="color:blue;">catch</span> (<span style="color:#2b91af;">Exception</span> ex)
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   47</span>         {
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   48</span>             Response.Write(<span style="color:#a31515;">&#8220;ERROR :: &#8220;</span> + ex.Message);
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   49</span>         }
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   50</span>     }
  </p>
  
  <p style="margin:0;">
     
  </p>
  
  <p style="margin:0;">
    In this code you can see there is connection object created. But there may be numerous occasions where I&#8217;ll have to use the connection, so rather than writing this code again at that place, what I&#8217;ll do is just simply select the two lines of connection right click &#8211; refactor &#8211; extract method
  </p>
  
  <p style="margin:0;">
     
  </p>
  
  <p style="margin:0;">
    <a href="http://ajaymatharu.files.wordpress.com/2008/11/extract-method1.png"></a><a href="http://ajaymatharu.files.wordpress.com/2008/11/extractmethod.jpg"><img class="aligncenter size-full wp-image-497" title="extractmethod" src="http://ajaymatharu.files.wordpress.com/2008/11/extractmethod.jpg" alt="extractmethod" width="500" height="374" /></a><a href="http://ajaymatharu.files.wordpress.com/2008/11/extract-method.png"></a>
  </p>
</div>

[<img class="aligncenter size-full wp-image-498" title="name" src="http://ajaymatharu.files.wordpress.com/2008/11/name.jpg" alt="name" width="500" height="196" />](http://ajaymatharu.files.wordpress.com/2008/11/name.jpg)

After this, all you get is extracted method,

<div style="font-family:Courier New;font-size:10pt;color:black;background:white;">
  <p style="margin:0;">
    <span style="color:#2b91af;">   27</span> <span style="color:blue;">public</span> <span style="color:blue;">void</span> fillControl()
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   28</span>     {
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   29</span>         <span style="color:blue;">try</span>
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   30</span>         {
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   31</span>             <span style="color:#2b91af;">OleDbDataAdapter</span> adapter;
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   32</span>             <span style="color:#2b91af;">DataSet</span> dataset;
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   33</span>             <span style="color:#2b91af;">OleDbConnection</span> conn;
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   34</span> 
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   35</span>             conn = ConnectDb();
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   36</span> 
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   37</span>             <span style="color:blue;">string</span> sqlQuery = <span style="color:#a31515;">&#8220;SELECT * from employee&#8221;</span>;
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   38</span>             adapter = <span style="color:blue;">new</span> <span style="color:#2b91af;">OleDbDataAdapter</span>(sqlQuery, conn);
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   39</span>             dataset = <span style="color:blue;">new</span> <span style="color:#2b91af;">DataSet</span>();
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   40</span>             adapter.Fill(dataset);
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   41</span> 
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   42</span>             datagrid1.DataSource = dataset;
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   43</span>             datagrid1.DataBind();
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   44</span>         }
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   45</span>         <span style="color:blue;">catch</span> (<span style="color:#2b91af;">Exception</span> ex)
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   46</span>         {
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   47</span>             Response.Write(<span style="color:#a31515;">&#8220;ERROR :: &#8220;</span> + ex.Message);
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   48</span>         }
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   49</span>     }
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   50</span> 
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   51</span>     <span style="color:blue;">private</span> <span style="color:#2b91af;">OleDbConnection</span> ConnectDb()
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   52</span>         {
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   53</span>         <span style="color:#2b91af;">OleDbConnection</span> conn;
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   54</span>         conn = <span style="color:blue;">new</span> <span style="color:#2b91af;">OleDbConnection</span>();
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   55</span>         conn.ConnectionString = <span style="color:#a31515;">&#8220;PROVIDER=MICROSOFT.Jet.Oledb.4.0;Data Source=&#8221;</span> + Server.MapPath(<span style="color:#a31515;">&#8220;mydatabase.mdb&#8221;</span>);
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   56</span>         <span style="color:blue;">return</span> conn;
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;">   57</span>         }
  </p>
  
  <p style="margin:0;">
     
  </p>
  
  <p style="margin:0;">
    So now you can use this ConnectDb() function where ever you need to use the Database connection.
  </p>
</div>

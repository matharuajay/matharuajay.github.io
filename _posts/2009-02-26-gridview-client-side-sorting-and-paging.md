---
toc: false
id: 842
title: 'Gridview &#8211; Client side sorting and paging'
date: 2009-02-26T19:00:27+00:00
author: Ajay Matharu
layout: post
guid: http://ajaymatharu.wordpress.com/?p=842
permalink: /gridview-client-side-sorting-and-paging/
ljID:
  - 193
dsq_thread_id:
  - 465391757
categories:
  - .Net
  - ASP.Net
  - Development
  - Microsoft
  - Technical
  - Technology
  - Visual Studio
tags:
  - Agile Development
  - ASP.Net
  - 'C#.Net'
  - Microsoft
  - Technology
  - Visual Studio
  - vs.net
---
<!-- {\rtf1\ansi\ansicpg\lang1024\noproof65001\uc1 \deff0{\fonttbl{\f0\fnil\fcharset0\fprq1 Courier New;}}{\colortbl;??\red0\green0\blue0;\red255\green238\blue98;\red0\green0\blue255;\red255\green255\blue255;\red163\green21\blue21;\red255\green0\blue0;\red43\green145\blue175;}??\fs20 \cb2\highlight2 <%\cf3\cb0\highlight0 @\cf0  \cf5 Page\cf0  \cf6 Language\cf3 ="C#"\cf0  \cf6 AutoEventWireup\cf3 ="true"\cf0  \cf6 CodeFile\cf3 ="Default.aspx.cs"\cf0  \cf6 Inherits\cf3 ="_Default"\cf0  \cb2\highlight2 %>\par ??\par ??\cf3\cb0\highlight0 <!\cf5 DOCTYPE\cf0  \cf6 html\cf0  \cf6 PUBLIC\cf0  \cf3 "-//W3C//DTD XHTML 1.0 Transitional//EN"\cf0  \cf3 "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">\par ??<\cf5 html\cf3 >\par ??<\cf5 head\cf0  \cf6 id\cf3 ="Head1"\cf0  \cf6 runat\cf3 ="server">\par ??\cf0     \cf3 <\cf5 title\cf3 >\cf0 Callback GridView\cf3 </\cf5 title\cf3 >\par ??</\cf5 head\cf3 >\par ??<\cf5 body\cf3 >\par ??\cf0     \cf3 <\cf5 form\cf0  \cf6 id\cf3 ="Form1"\cf0  \cf6 runat\cf3 ="server">\par ??\cf0     \cb2\highlight2 <%\cf3\cb0\highlight0 =\cf7 DateTime\cf0 .Now \cb2\highlight2 %>\par ??\cb0\highlight0     \cf3 <\cf5 asp\cf3 :\cf5 GridView\cf0  \cf6 ID\cf3 ="GridView1"\cf0  \cf6 DataSourceID\cf3 ="TitlesSource"\cf0  \cf6 EnableSortingAndPagingCallbacks\cf3 ="true"\par ??\cf0         \cf6 AllowPaging\cf3 ="true"\cf0  \cf6 AllowSorting\cf3 ="true"\cf0  \cf6 runat\cf3 ="Server"\cf0  \cf3 />\par ??\cf0     \cf3 <\cf5 asp\cf3 :\cf5 SqlDataSource\cf0  \cf6 ID\cf3 ="TitlesSource"\cf0  \cf6 ConnectionString\cf3 ="Server=localhost;Database=northwind;Trusted_Connection=true"\par ??\cf0         \cf6 SelectCommand\cf3 ="SELECT * FROM customers"\cf0  \cf6 runat\cf3 ="Server"\cf0  \cf3 />\par ??\cf0     \cf3 </\cf5 form\cf3 >\par ??</\cf5 body\cf3 >\par ??</\cf5 html\cf3 >\par ??} -->

<div style="background:white none repeat scroll 0 0;font-family:Courier New;font-size:10pt;color:black;">
  <p>
    The <strong>GridView</strong> control provides you with the option of sorting and paging records without requiring a form-post back to the Web server. In other words, you can re-render the contents of a <strong>GridView</strong> when sorting and paging, without needing to re-render the entire page.
  </p>
  
  <p>
    You enable client paging and sorting by assigning the value <strong>true</strong> to the <strong>EnableSortingAndPagingCallback</strong> property. When this property has the value <strong>true</strong>, the <strong>GridView</strong> uses JavaScript to request an updated set of records from the Web server.
  </p>
  
  <p style="margin:0;">
    <span style="color:red;"><br /> </span>
  </p>
  
  <p style="margin:0;">
    <p style="margin:0;">
      <span style="color:red;"> 1</span> <span style="background:#ffee62 none repeat scroll 0 0;"><%</span><span style="color:blue;">@</span> <span style="color:#a31515;">Page</span> <span style="color:red;">Language</span><span style="color:blue;">=&#8221;C#&#8221;</span> <span style="color:red;">AutoEventWireup</span><span style="color:blue;">=&#8221;true&#8221;</span> <span style="color:red;">CodeFile</span><span style="color:blue;">=&#8221;Default.aspx.cs&#8221;</span> <span style="color:red;">Inherits</span><span style="color:blue;">=&#8221;_Default&#8221;</span> <span style="background:#ffee62 none repeat scroll 0 0;">%></span>
    </p>
    
    <p style="margin:0;">
      <span style="color:red;"> 2</span>
    </p>
    
    <p style="margin:0;">
      <span style="color:red;"> 3</span> <span style="color:blue;"><!</span><span style="color:#a31515;">DOCTYPE</span> <span style="color:red;">html</span> <span style="color:red;">PUBLIC</span> <span style="color:blue;">&#8220;-//W3C//DTD XHTML 1.0 Transitional//EN&#8221;</span> <span style="color:blue;">&#8220;http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd&#8221;></span>
    </p>
    
    <p style="margin:0;">
      <span style="color:red;"> 4</span> <span style="color:blue;"><</span><span style="color:#a31515;">html</span><span style="color:blue;">></span>
    </p>
    
    <p style="margin:0;">
      <span style="color:red;"> 5</span> <span style="color:blue;"><</span><span style="color:#a31515;">head</span> <span style="color:red;">id</span><span style="color:blue;">=&#8221;Head1&#8243;</span> <span style="color:red;">runat</span><span style="color:blue;">=&#8221;server&#8221;></span>
    </p>
    
    <p style="margin:0;">
      <span style="color:red;"> 6</span> <span style="color:blue;"><</span><span style="color:#a31515;">title</span><span style="color:blue;">></span>Callback GridView<span style="color:blue;"></</span><span style="color:#a31515;">title</span><span style="color:blue;">></span>
    </p>
    
    <p style="margin:0;">
      <span style="color:red;"> 7</span> <span style="color:blue;"></</span><span style="color:#a31515;">head</span><span style="color:blue;">></span>
    </p>
    
    <p style="margin:0;">
      <span style="color:red;"> 8</span> <span style="color:blue;"><</span><span style="color:#a31515;">body</span><span style="color:blue;">></span>
    </p>
    
    <p style="margin:0;">
      <span style="color:red;"> 9</span> <span style="color:blue;"><</span><span style="color:#a31515;">form</span> <span style="color:red;">id</span><span style="color:blue;">=&#8221;Form1&#8243;</span> <span style="color:red;">runat</span><span style="color:blue;">=&#8221;server&#8221;></span>
    </p>
    
    <p style="margin:0;">
      <span style="color:red;"> 10</span> <span style="background:#ffee62 none repeat scroll 0 0;"><%</span><span style="color:blue;">=</span><span style="color:#2b91af;">DateTime</span>.Now <span style="background:#ffee62 none repeat scroll 0 0;">%></span>
    </p>
    
    <p style="margin:0;">
      <span style="color:red;"> 11</span> <span style="color:blue;"><</span><span style="color:#a31515;">asp</span><span style="color:blue;">:</span><span style="color:#a31515;">GridView</span> <span style="color:red;">ID</span><span style="color:blue;">=&#8221;GridView1&#8243;</span> <span style="color:red;">DataSourceID</span><span style="color:blue;">=&#8221;TitlesSource&#8221;</span> <span style="color:red;">EnableSortingAndPagingCallbacks</span><span style="color:blue;">=&#8221;true&#8221;</span>
    </p>
    
    <p style="margin:0;">
      <span style="color:red;"> 12</span> <span style="color:red;">AllowPaging</span><span style="color:blue;">=&#8221;true&#8221;</span> <span style="color:red;">AllowSorting</span><span style="color:blue;">=&#8221;true&#8221;</span> <span style="color:red;">runat</span><span style="color:blue;">=&#8221;Server&#8221;</span> <span style="color:blue;">/></span>
    </p>
    
    <p style="margin:0;">
      <span style="color:red;"> 13</span> <span style="color:blue;"><</span><span style="color:#a31515;">asp</span><span style="color:blue;">:</span><span style="color:#a31515;">SqlDataSource</span> <span style="color:red;">ID</span><span style="color:blue;">=&#8221;TitlesSource&#8221;</span> <span style="color:red;">ConnectionString</span><span style="color:blue;">=&#8221;Server=localhost;Database=northwind;Trusted_Connection=true&#8221;</span>
    </p>
    
    <p style="margin:0;">
      <span style="color:red;"> 14</span> <span style="color:red;">SelectCommand</span><span style="color:blue;">=&#8221;SELECT * FROM customers&#8221;</span> <span style="color:red;">runat</span><span style="color:blue;">=&#8221;Server&#8221;</span> <span style="color:blue;">/></span>
    </p>
    
    <p style="margin:0;">
      <span style="color:red;"> 15</span> <span style="color:blue;"></</span><span style="color:#a31515;">form</span><span style="color:blue;">></span>
    </p>
    
    <p style="margin:0;">
      <span style="color:red;"> 16</span> <span style="color:blue;"></</span><span style="color:#a31515;">body</span><span style="color:blue;">></span>
    </p>
    
    <p style="margin:0;">
      <span style="color:red;"> 17</span> <span style="color:blue;"></</span><span style="color:#a31515;">html</span><span style="color:blue;">></span>
    </p>
    
    <p style="margin:0;">
      <span style="color:blue;"><br /> </span>
    </p>
    
    <p style="margin:0;">
      <p style="margin:0;">
        <span style="color:blue;"><span style="color:#000000;">Here when you will sort the page or click on the page number the time will not change as it is being set on the page load but the data will get sorted. </span></span>The time doesn&#8217;t change because the page is not reloaded.
      </p>
      
      <p style="margin:0;">
        <p style="margin:0;">
          Behind the scenes, the <strong>GridView</strong> uses the Microsoft Internet Explorer <strong>XMLHTTPRequest</strong> object to communicate with the Web server. This object is supported by Internet Explorer version 5.0 and higher.
        </p>
        
        <p style="margin:0;">
          <p style="margin:0;">
            However this does not work when you have a templatefield in your Gridview. If you have a templatefield in your Gridview you need to perform the pagination like traditional way handling the events.
          </p></div>

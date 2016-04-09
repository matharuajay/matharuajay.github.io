---
id: 1489
title: Using JSON to send objects across pages
date: 2009-07-15T21:20:17+00:00
author: Ajay Matharu
layout: post
guid: http://www.ajaymatharu.com/?p=1489
permalink: /using-json-to-send-objects-across-pages/
ljID:
  - 284
dsq_thread_id:
  - 465385809
categories:
  - .Net
  - ASP.Net
  - Development
  - Javascript
  - Visual Studio
tags:
  - .Net
  - Arraylist
  - ASP.Net
  - 'C#'
  - DeSerialize
  - HttpRequest
  - Javascript
  - JSON
  - Microsoft .Net
  - Request Object
  - Serialize
---
Recently our team came across a situation where our job was to retrieve ArrayList in a page requested by flex application using HttpService.Which are accessed using **Request[keyName]
  
** 
  
Request objects always returns data in string format, so there was no point in trying that solution, so we were looking for some reliable and optimal solution. Googling around I came across JSON (Javascript Object Notation).JSON can be used in various languages, you can find the list of langauges and the resources requied to use [JSON](http://json.org/) over here.

JSON allows us to serialize a object and send across a page in string format.All we need to do is to perform Deserialization on the requested page.

This is the sample code which demonstrates the use of JSON to send arraylist to another page.

The code below contains 2 arraylist which need to be send on another page.The arraylist are serialized and sent to different page with the help of querystring.

<pre name="code" class="c#">ArrayList list = new ArrayList();
ArrayList list1 = new ArrayList();
list1.Add("one-one");
list1.Add("one-two");
list1.Add("one-three");
list1.Add("one-four");
list.Add(list1);
list.Add("two");
list.Add("three");
string arrayList = JavaScriptConvert.SerializeObject(list);
Response.Redirect("Process.aspx?list="+arrayList);
</pre>

The code below Deserialize and typecast the object to JavaScriptArray.

<pre name="code" class="c#">string arrayList = Request["list"];
JavaScriptArray list = (JavaScriptArray)JavaScriptConvert.DeserializeObject(arrayList);
</pre>

You can download sample code from [here](http://www.box.net/shared/g0nahe7979).

Enjoy Coding <img src="http://www.ajaymatharu.com/wp-includes/images/smilies/simple-smile.png" alt=":)" class="wp-smiley" style="height: 1em; max-height: 1em;" />
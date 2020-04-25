---
toc: false
id: 1169
title: 'Validating html tags in textbox &#8211; Cross site scripting'
date: 2010-03-18T04:26:26+00:00
author: Ajay Matharu
layout: post
guid: https://www.ajaymatharu.com/?p=1169
permalink: /validating-html-tags-in-textbox-cross-site-scripting/
aktt_notify_twitter:
  - no
thumbnail:
  - https://www.ajaymatharu.com/wp-content/uploads/2009/05/hackers-300x85.jpg
dsq_thread_id:
  - 465384940
categories:
  - Development
  - Javascript
  - Web
tags:
  - Cross page scripting issue
  - Javascript
  - validate HTML
  - validate html in textbox
  - validate html tags
  - validate HTML tags in input
  - validate html tags in textbox
  - validation
---
Following is the code to validate any textbox or input text against html tags.

<pre name="code" class="js">//source and args are required if calling from custom validator in asp.net else its not required
function htmlValidation(source,args) 
{
var re = /(&lt;([^>]+)>)/gi;

if (document.getElementById(’&lt;%=TextBox2.ClientID%>’).value.match(re)) {
document.getElementById(’&lt;%=TextBox2.ClientID%>’).value = “”;
alert(’Invalid content’);
//args.IsValid = false; // you can use this if you are calling this from custom validator in asp.net
return false;
}
if (document.getElementById("textboxid").value.match(re)) {
document.getElementById("textboxid").value = “”;
alert(’Invalid content’);
return false;
}
return true;
}

</pre>

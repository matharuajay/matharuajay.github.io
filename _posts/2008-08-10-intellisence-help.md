---
tags: 
  - misc
toc:  false
id: 25
title: Intellisence help in user-defined functions, properties etc in Visual Studio
date: 2008-08-10T12:48:57+00:00
author: Ajay Matharu
layout: post
guid: https://ajaymatharu.wordpress.com/?p=25
permalink: /intellisence-help/
ljID:
  - 9
dsq_thread_id:
  - 465391616
categories:
  - Visual Studio
---
I just went through one of the video which showed how can you enhance intellisence feature in Visual Studio for the user-defined things. 

Let me explain this to you in detail, suppose you have a class containing few functions and properties, When you create an object for that class and access its function all you can see in the intellisence is the name of the function without the description, but when you look at the inbuilt function in any of the inbuilt class you can see the description of that function.

Have you ever thought why so?

This is just because they have commented their code. You can also have your function showing the description of what it does in the intellisence and even pass the description for the parameters. All you have to do is provide a proper comment for your code. That is what a good programmer does. Here is the sample of the comment you must provide,

 

<div id="attachment_34" style="width: 310px" class="wp-caption aligncenter">
  <a href="https://ajaymatharu.files.wordpress.com/2008/08/intellisencexml.png"><img class="size-medium wp-image-34" src="https://ajaymatharu.files.wordpress.com/2008/08/intellisencexml.png?w=300" alt="Intellisence Help" width="300" height="139" /></a>
  
  <p class="wp-caption-text">
    Intellisence Help
  </p>
</div>

<span style="font-size:x-small;">Here you can see the summary which appears as the description and the parameter list which will show the description for the parameters too. So keep practicing this to be a good programmer although there are various things which you should practice but this is one of them.</span>

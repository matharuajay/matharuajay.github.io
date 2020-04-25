---
toc: false
id: 500
title: 'Encapsulate Field &#8211; Tip of week #12'
date: 2008-12-09T03:00:05+00:00
author: Ajay Matharu
layout: post
guid: http://ajaymatharu.wordpress.com/?p=500
permalink: /encapsulate-field-tip-of-week-12/
ljID:
  - 118
dsq_thread_id:
  - 465383935
categories:
  - .Net
  - Tip of Week
  - Visual Studio
tags:
  - .Net
  - Encapsulation
  - OOPS
  - Refactor
  - Visual Studio Tip
  - Visual Studio Tip Of Week
  - vs.net
---
Last week I told you guys about, Extract Method. Today I am going to talk about Encapsulate Field in Refactor.

Encapsulation is very essintial part of OOPS. You can eaily encapsulate your field in VS.net using your Refactor option.

Its very simple to Encapsulate the field in VS.net you just need to right click on field &#8211; refactor &#8211; encapsulate field.

[<img class="aligncenter size-full wp-image-501" title="encapsulate" src="http://ajaymatharu.files.wordpress.com/2008/11/encapsulate.jpg" alt="encapsulate" width="500" height="128" />](http://ajaymatharu.files.wordpress.com/2008/11/encapsulate.jpg)

[<img class="aligncenter size-full wp-image-502" title="encapsulate1" src="http://ajaymatharu.files.wordpress.com/2008/11/encapsulate1.jpg" alt="encapsulate1" width="352" height="275" />](http://ajaymatharu.files.wordpress.com/2008/11/encapsulate1.jpg)

After this the output is like,

<div style="font-family:Courier New;font-size:10pt;color:black;background:white;">
  <p style="margin:0;">
    <span style="color:#2b91af;"> 14</span> <span style="color:blue;">private</span> <span style="color:blue;">bool</span> _isValid;
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;"> 15</span>
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;"> 16</span> <span style="color:blue;">public</span> <span style="color:blue;">bool</span> IsValid1
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;"> 17</span> {
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;"> 18</span> <span style="color:blue;">get</span> { <span style="color:blue;">return</span> _isValid; }
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;"> 19</span> <span style="color:blue;">set</span> { _isValid = <span style="color:blue;">value</span>; }
  </p>
  
  <p style="margin:0;">
    <span style="color:#2b91af;"> 20</span> }
  </p>
  
  <p style="margin:0;">
    <p style="margin:0;">
      So you&#8217;ll have no troubles implementing Encapsulation in your code. VS.Net does this all for you.
    </p>
    
    <p style="margin:0;">
      <p style="margin:0;">
        Enjoy Coding!!!
      </p></div>

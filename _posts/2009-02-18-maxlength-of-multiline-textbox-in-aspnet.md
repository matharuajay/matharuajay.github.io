---
id: 966
title: Maxlength of multiline textbox in ASP.Net
date: 2009-02-18T11:03:53+00:00
author: Ajay Matharu
layout: post
guid: http://www.ajaymatharu.com/?p=966
permalink: /maxlength-of-multiline-textbox-in-aspnet/
ljID:
  - 189
dsq_thread_id:
  - 465388132
categories:
  - ASP.Net
  - Technical
  - Visual Studio
tags:
  - .Net
  - ASP.Net
  - Javascript
  - Microsoft Visual Studio
  - Mulitine textbox
  - vs.net
---
Many times you need to restrict the number of character&#8217;s in multi-line textbox in asp.net. However the maxlength property does not helps in this case what you can do is use this javascript code to restrict the number of input characters in multiline textbox.

<script language=&#8221;javascript&#8221;>
  
function textboxMultilineMaxNumber(txt, maxLen) {
  
try {
  
if (txt.value.length > (maxLen &#8211; 1)) return false;
  
} catch (e) {
  
}
  
}
  
</script>

use javascript like this,

<asp:textbox id=&#8221;TextBox1&#8243; runat=&#8221;server&#8221; Width=&#8221;232px&#8221; TextMode=&#8221;MultiLine&#8221; Height=&#8221;48px&#8221; style=&#8221;Z-INDEX: 104; LEFT: 136px; TOP: 336px&#8221;
  
onkeypress=&#8221;return textboxMultilineMaxNumber(this,10)&#8221;></asp:textbox>
---
id: 1473
title: 'Disable Cut, Copy &#038; Paste in ASP.Net textbox'
date: 2009-07-09T00:57:44+00:00
author: Ajay Matharu
layout: post
guid: http://www.ajaymatharu.com/?p=1473
permalink: /disable-cut-copy-paste-in-asp-net-textbox/
ljID:
  - 280
dsq_thread_id:
  - 465392332
categories:
  - .Net
  - ASP.Net
  - HTML
  - Javascript
  - Tip of Week
  - Visual Studio
tags:
  - asp textbox
  - ASP.Net
  - ASP.Net textbox
  - Copy
  - copy paste
  - Cut
  - Disable Cut
  - Disable Cut Copy Paste
  - Javascript
  - Paste
---
You can disable cut, copy & paste in ASP.Net textbox in very simple way,

here is how you can disable the cut, copy, paste,

<pre class="html" name="code">&lt;asp:TextBox ID=”TextBox1″ runat=”server” oncopy=”return false” onpaste=”return false” oncut=”return false”&gt;&lt;/asp:TextBox&gt;</pre>
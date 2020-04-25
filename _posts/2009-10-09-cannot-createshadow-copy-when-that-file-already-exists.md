---
toc: false
id: 1593
title: Cannot create/shadow copy when that file already exists
date: 2009-10-09T12:49:21+00:00
author: Ajay Matharu
layout: post
guid: http://www.ajaymatharu.com/?p=1593
permalink: /cannot-createshadow-copy-when-that-file-already-exists/
robotsmeta:
  - index,follow
dsq_thread_id:
  - 465390005
categories:
  - .Net
  - ASP.Net
  - Visual Studio
tags:
  - .Net
  - ASP.Net
  - Cache
  - Hosting Environment
  - Shadow Copy
  - web.config
---
The .Net Framework has a feature called <span style="font-weight: bold;">Shadow Copy</span>.

Shadow copy is enabled on every appdomain created by ASP.NET by default. By default assemblies loaded will be copied to a shadow copy cache directory, and will be used from that location.

<pre class="xml" name="code">&lt;hostingenvironment shadowcopybinassemblies="false">
&lt;/hostingenvironment>
</pre>

But this may create <a title="Side effects of shadow copy bin assemblies" href="http://www.ajaymatharu.com/side-effect-of-shadowcopybinassemblies/" target="_blank">problem</a> sometimes.

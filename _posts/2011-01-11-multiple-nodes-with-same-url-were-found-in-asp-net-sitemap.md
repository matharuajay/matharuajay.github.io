---
toc: false
id: 2487
title: Multiple nodes with same URL were found in asp.net Sitemap
date: 2011-01-11T21:15:00+00:00
author: Ajay Matharu
layout: post
guid: http://www.ajaymatharu.com/?p=2487
permalink: /multiple-nodes-with-same-url-were-found-in-asp-net-sitemap/
dsq_thread_id:
  - 465387162
categories:
  - .Net
  - ASP.Net
  - Visual Studio
tags:
  - multiple nodes in asp.net
  - Multiple nodes in sitemap
  - multiple nodes in sitemap in asp.net
  - multiple nodes with same url in asp.net
  - multiple nodes with same url in sitemap in asp.net
  - multiple nodes with the same url
---
If you run through the following error in asp.net sitemap,

<div id="attachment_2489" style="width: 310px" class="wp-caption aligncenter">
  <a href="http://www.ajaymatharu.com/multiple-nodes-with-same-url-were-found-in-asp-net-sitemap/sitemaperror-2/" rel="attachment wp-att-2489"><img src="http://www.ajaymatharu.com/wp-content/uploads/2011/01/sitemapError1-300x86.png" alt="Multiple notes asp.net sitemap error" title="Multiple notes asp.net sitemap error" width="300" height="86" class="size-medium wp-image-2489" srcset="http://www.ajaymatharu.com/wp-content/uploads/2011/01/sitemapError1-300x86.png 300w, http://www.ajaymatharu.com/wp-content/uploads/2011/01/sitemapError1-1024x295.png 1024w, http://www.ajaymatharu.com/wp-content/uploads/2011/01/sitemapError1.png 1237w" sizes="(max-width: 300px) 100vw, 300px" /></a>
  
  <p class="wp-caption-text">
    Multiple notes asp.net sitemap error
  </p>
</div>


  
The best solution to overcome this is to have the URL with a new querystring. Even if you are not using the querystring but if you pass any querystring it will resolve the above error.

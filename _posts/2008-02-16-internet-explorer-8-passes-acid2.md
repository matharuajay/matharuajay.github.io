---
tags: 
  - misc
toc:  false
id: 933
title: Internet Explorer 8 passes Acid2
date: 2008-02-16T09:43:00+00:00
author: Ajay Matharu
layout: post
guid: https://ajaymatharu.wordpress.com/?p=3
permalink: /internet-explorer-8-passes-acid2/
ljID:
  - 2
dsq_thread_id:
  - 465386116
categories:
  - Technical
---
![Acid2 Face](https://ieblog.members.winisp.net/images/AcidTest2.PNG)

While [web developers](https://msdn2.microsoft.com/en-us/ie/default.aspx) will immediately recognize what [Acid2](https://en.wikipedia.org/wiki/Acid2) means, I want to step back and offer some context for other readers of this blog who may not be familiar with web standards. Briefly: Acid2 is one test of how modern browsers work with some specific features across several different web standards.

At first glance, this test seems simple. I think it actually offers a view into the subtle and complex world of web standards in a number of ways. Showing the Acid2 page correctly is a good indication of being standards compliant, but Acid2 itself isn’t a web standard or a web standards compliance [test](https://www.webstandards.org/action/acid2/guide/). The publisher of the test, the [Web Standards Project](https://www.webstandards.org/), is an advocacy group, not a web standards defining body.

When we look at the long lists of standards (even from just one standards body, like the [W3C](https://www.w3.org)), which standards are the most important for us to support? The web has many kinds of standards – true industry standards, like those from the W3C, de facto standards, unilateral standards, open standards, and more. Some standards like RSS or OpenSearch lack a formal standards body yet work pretty well today across multiple implementations. Many advances in web technologies, [like the img tag](https://1997.webhistory.org/www.lists/www-talk.1993q1/0182.html), start out as unilateral extensions by a [vendor](https://developer.mozilla.org/en/docs/CSS_Reference:Mozilla_Extensions). The [X](https://msdn2.microsoft.com/en-us/library/ms537505.aspx) in AJAX, for example, has only started the formal standardization process relatively recently. As some [comments](https://www.webstandards.org/2007/12/13/opera-complains-to-europe-over-ie-lock-in/#comment-59176) have pointed out, CSS 2.1, one of the key standards that Acid2 exercises, is not “finalized” yet. Different individuals have [different](https://blogs.msdn.com/ie/archive/2007/12/05/internet-explorer-8.aspx#6717629) [opinions](https://blogs.msdn.com/ie/archive/2007/12/05/internet-explorer-8.aspx#6679356) about different standards. The important thing about the Acid2 test is that it reflects what one particular group of smart people “consider [most important](https://www.webstandards.org/action/acid2/guide/) for the future of the web.”

The key goal (for the Web Standards Project as well as many other groups and [individuals](https://www.microsoft.com/mscorp/execmail/2005/02-03interoperability.mspx)) is _interoperability_. As a developer, I’d prefer to not have to write the same site multiple times for different browsers. Standards are a (critical!) means to this end, and we focus on the standards that will help actual, real-world interoperability the most. As a consumer and a developer, I expect stuff to just work, and I also expect _backwards compatibility_. When I get a new version of my current browser, I expect all the sites that worked before will still work.

On Wednesday, December 12, Internet Explorer correctly rendered the Acid2 page in IE8 standards mode. While supporting the features tested in Acid2 is important for many reasons, it is just one of several milestones for the interoperability, standards compliance, and backwards compatibility.

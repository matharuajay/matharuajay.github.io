---
tags: 
  - misc
toc:  false
id: 1727
title: Using Canonical URL to help solve duplicate content issues
date: 2009-10-09T17:23:10+00:00
author: Ajay Matharu
layout: post
guid: https://www.ajaymatharu.com/?p=1727
permalink: /using-canonical-url-to-help-solve-duplicate-content-issues/
robotsmeta:
  - index,follow
aktt_notify_twitter:
  - no
dsq_thread_id:
  - 465389479
categories:
  - Google
  - Information
  - Search Engine
  - SEO
  - Technical
  - Technology
  - Web
---
### **What is the issue?**

One of the most common challenges search engines run into when indexing a website is identifying and consolidating duplicate pages. Duplicates can occur when any given webpage has multiple URLs that point to it. For example:

<table style="height: 202px;" border="0" cellspacing="0" cellpadding="2" width="675">
  <tr>
    <td width="190" valign="top">
      <strong>URL</strong>
    </td>
    
    <td width="291" valign="top">
      <strong>Description</strong>
    </td>
  </tr>
  
  <tr>
    <td width="190" valign="top">
      https://mysite.com
    </td>
    
    <td width="291" valign="top">
      A webmaster may consider this their authoritative or <em>canonical</em> URL for their homepage.
    </td>
  </tr>
  
  <tr>
    <td width="190" valign="top">
      https://www.mysite.com
    </td>
    
    <td width="291" valign="top">
      However, you can add &#8216;www&#8217; to most websites and still get the same home page.
    </td>
  </tr>
  
  <tr>
    <td width="190" valign="top">
      https://mysite.com/default.aspx
    </td>
    
    <td width="291" valign="top">
      You can also often add the specific filename of the homepage and get the same page
    </td>
  </tr>
  
  <tr>
    <td width="190" valign="top">
      https://mysite.com/default.aspx?promo=ABC
    </td>
    
    <td width="291" valign="top">
      Many times websites use parameters to track things like where customers are coming from (in this case an offline promotion), or parameters that determine how the content on the page is formatted.
    </td>
  </tr>
</table>

These four cases are just a few of the many possibilities. When you consider all the combinations of these, you could have more than 10 clone URLs for every page on your site. That means if there are 1 million pages on your site, we could possibly find 10 million or more cloned URLs pointing to them. Determining your canonical URL amongst all the duplicate clutter has been an onerous challenge for search engines as we all work to reduce cost and improve relevance.

### How to resolve this issue?

To help solve this issue, a new tag attribute that will help webmasters identify the single authoritative (or _canonical_) URL for a given page. The link tag defines a relationship between a document and an external resource. In this case, that resource is the canonical URL. The following is an example of the new link tag attribute for canonicalization:

<pre><pre style="margin: 0em; background-color: #ffffff; width: 100%; font-family: consolas,'Courier New',courier,monospace; font-size: 12px;"><span style="color: #0000ff;">&lt;</span><span style="color: #800000;">link</span> <span style="color: #ff0000;">rel</span>=<span style="color: #0000ff;">"canonical"</span> <span style="color: #ff0000;">href</span>=<span style="color: #0000ff;">"https://mysite.com"</span><span style="color: #0000ff;">/&gt;
</span></pre>


<p>
  now, the search engine will suddenly count the links it has seen to that campaign tagged URL, towards the canonical URL, and not index the campaign tagged URL anymore. Simple, yet effective. This feature works with Google, and both Live Search and Yahoo!.
</p>


<p>
  The &#8220;canonical&#8221; feature represents a timely, relevant, and positive partnership between major search engines. It is a step to ensuring more consistency with regard to treatment of duplicates among all of the engines. It will also put more control into the hands of site designers over how their sites are represented within the search indexes.
</p>


<h3>
  <strong>A couple of notes:</strong>
</h3>


<p>
  1) This tag is a suggestion to search engines and is not guaranteed to be used. 301 redirects and good link strategy is still important
</p>


<p>
  2) You can not use this tag to redirect between domains. We can&#8217;t redirect Domain1.com to Domain2.com using this tag
</p>


<p>
  3) You CAN suggest SSL urls as the preferred format. http<strong>s</strong>://www.domain.com
</p>


<p>
  4) Don&#8217;t abuse the tag to redirect users to non-similar content. The search engines are smarter than that now.
</p>


<p>
  5) Try and use absolute URLs instead of relative ones. Point directly to the final destination because a chain of canonical links may not be followed.
</p>


<h3>
  <strong><span style="color: #000000;">Some questions you may have that are answered by google?</span></strong>
</h3>


<pre style="margin: 0em; background-color: #ffffff; width: 100%; font-family: consolas,'Courier New',courier,monospace; font-size: 12px;"><strong>Is rel="canonical" a hint or a directive? </strong></pre>


<p>
  It&#8217;s a hint that we honor strongly. We&#8217;ll take your preference into account, in conjunction with other signals, when calculating the most relevant page to display in search results.
</p>


<pre style="margin: 0em; background-color: #ffffff; width: 100%; font-family: consolas,'Courier New',courier,monospace; font-size: 12px;"><strong>Can I use a relative path to specify the canonical, such as <span style="color: #006600;"><span style="font-family: 'Courier New';">&lt;link rel="canonical" href="product.php?item=swedish-fish" /&gt;</span></span>?</strong></pre>


<p>
  Yes, relative paths are recognized as expected with the <strong><span style="color: #006600;"><span style="font-family: Courier New;"><link></span></span></strong> tag. Also, if you include a <strong><span style="color: #006600;"><span style="font-family: Courier New;"><base></span></span></strong> link in your document, relative paths will resolve according to the base URL.
</p>


<pre style="margin: 0em; background-color: #ffffff; width: 100%; font-family: consolas,'Courier New',courier,monospace; font-size: 12px;"><strong>Is it okay if the canonical is not an exact duplicate of the content?</strong></pre>


<p>
  We allow slight differences, e.g., in the sort order of a table of products. We also recognize that we may crawl the canonical and the duplicate pages at different points in time, so we may occasionally see different versions of your content. All of that is okay with us.
</p>


<pre style="margin: 0em; background-color: #ffffff; width: 100%; font-family: consolas,'Courier New',courier,monospace; font-size: 12px;"><strong>What if the rel="canonical" returns a 404?</strong></pre>


<p>
  We&#8217;ll continue to index your content and use a heuristic to find a canonical, but we recommend that you specify existent URLs as canonicals.
</p>


<pre style="margin: 0em; background-color: #ffffff; width: 100%; font-family: consolas,'Courier New',courier,monospace; font-size: 12px;"><strong>What if the rel="canonical" hasn't yet been indexed?</strong></pre>


<p>
  Like all public content on the web, we strive to discover and crawl a designated canonical URL quickly. As soon as we index it, we&#8217;ll immediately reconsider the rel=&#8221;canonical&#8221; hint.
</p>


<pre style="margin: 0em; background-color: #ffffff; width: 100%; font-family: consolas,'Courier New',courier,monospace; font-size: 12px;"><strong>Can rel="canonical" be a redirect?</strong></pre>


<p>
  Yes, you can specify a URL that redirects as a canonical URL. Google will then process the redirect as usual and try to index it.
</p>


<pre style="margin: 0em; background-color: #ffffff; width: 100%; font-family: consolas,'Courier New',courier,monospace; font-size: 12px;"><strong>What if I have contradictory rel="canonical" designations?</strong></pre>


<p>
  Our algorithm is lenient: We can follow canonical chains, but we strongly recommend that you update links to point to a single canonical page to ensure optimal canonicalization results.
</p>


<pre style="margin: 0em; background-color: #ffffff; width: 100%; font-family: consolas,'Courier New',courier,monospace; font-size: 12px;"><strong>Can this link tag be used to suggest a canonical URL on a completely different domain?</strong></pre>


<p>
  No. To migrate to a completely different domain, permanent (301) redirects are more appropriate. Google currently will take canonicalization suggestions into account across subdomains (or within a domain), but not across domains.
</p>

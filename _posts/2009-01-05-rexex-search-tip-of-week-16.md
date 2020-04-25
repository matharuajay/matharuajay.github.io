---
toc: false
id: 743
title: 'RexEx Search &#8211; Tip of Week #16'
date: 2009-01-05T00:00:02+00:00
author: Ajay Matharu
layout: post
guid: https://ajaymatharu.wordpress.com/?p=743
permalink: /rexex-search-tip-of-week-16/
delicious:
  - 's:86:"s:78:"a:3:{s:5:"count";s:1:"0";s:9:"post_tags";s:0:"";s:4:"time";s:10:"1231563588";}";";'
reddit:
  - 's:63:"s:55:"a:2:{s:5:"count";s:1:"0";s:4:"time";s:10:"1231563648";}";";'
ljID:
  - 149
dsq_thread_id:
  - 465387854
categories:
  - .Net
  - Microsoft
  - Tip of Week
  - Visual Studio
tags:
  - .Net
  - Development
  - Microsoft
  - Technology
  - Tip of Week
  - Visual Studio
  - Visual Studio Tip
  - Visual Studio Tip Of Week
  - Visual Studio tips
  - vs.net
---
Regular expressions are an extremely versatile text-matching language that gives you incredible power when searching your documents and when used with replace operations, can greatly assist with repetitive changes to blocks of code.

<img class="aligncenter size-full wp-image-744" title="regex" src="https://ajaymatharu.files.wordpress.com/2009/01/regex.jpg" alt="regex" width="251" height="273" />

The basic regular expression search is easily done. You simply open the Find dialog through the Edit &#8211; Find and Replace &#8211; Find menu or with Ctrl-F (Edit.Find). Enable regular expression searching by ensuring the Use checkbox is selected and the drop-down list has Regular Expressions selected.

Enter your regular expression into the Find What text box and click on Find Next. The next match of your expression will be found in the document. As with normal matches, clicking Find Next again will find the next match. The next step is to learn the regular expression (also known as <span class="docEmphasis">regex</span> or <span class="docEmphasis">regexp</span>) syntax.

<p class="docText">
  <strong>Regular expressions</strong> :
</p>

<p class="docText">
  Regular expressions<strong> </strong>can be very complex, but basic expressions can be easy to master. Unlike normal searches, regular expressions designate a pattern of characters to match instead of a constant string. For example, square brackets in a regular expression define a set of characters (a <span class="docEmphasis">character class</span>). When you execute the search, it will match any one character out of the set of characters inside the brackets, so the expression <tt>[abcd]</tt> would match <em>a</em>, <em>b</em>, <em>c</em>, and <em>d</em>—but not <em>z</em>. You can also specify character ranges inside the brackets, so <tt>[a-d]</tt> is equivalent to the expression <tt>[abcd]</tt>. If you need to specify more than one range, simply add it to the first, so <tt>[a-z0-9]</tt> will match any letter or number. Regular expression characters in Visual Studio are not case sensitive unless you select the Match Case option in the Find dialog. This is a departure from most other regular expression syntax.
</p>

<p class="docText">
  Normal alphabetic characters outside of special expressions match characters literally, similar to a normal Find, but can be combined with regular expressions to make them more flexible. This means that combining the set match with a literal match gives us a pattern such as <tt>var[12]</tt>, which will match <tt>var1</tt> and <tt>var2</tt> but not <tt>var3</tt>.
</p>

<p class="docText">
  If you want to match the string <tt>var[12]</tt>, you&#8217;d need to escape the special characters, as in <tt>var\[12\]</tt>.
</p>

<p class="docText">
  More <a href="https://regexlib.com/" target="_blank">Regular Expressions</a>.
</p>

<p class="docText">

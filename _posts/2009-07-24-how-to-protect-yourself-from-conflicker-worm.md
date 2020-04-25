---
toc: false
id: 861
title: 'How to protect yourself from &#8220;Conflicker&#8221; Worm'
date: 2009-07-24T09:34:40+00:00
author: Ajay Matharu
layout: post
guid: http://ajaymatharu.wordpress.com/?p=861
permalink: /how-to-protect-yourself-from-conflicker-worm/
delicious:
  - 's:86:"s:78:"a:3:{s:5:"count";s:1:"0";s:9:"post_tags";s:0:"";s:4:"time";s:10:"1232690437";}";";'
reddit:
  - 's:63:"s:55:"a:2:{s:5:"count";s:1:"0";s:4:"time";s:10:"1232690438";}";";'
bte_opp_original_pub_date:
  - 2009-01-20 11:07:06
dsq_thread_id:
  - 465383513
categories:
  - Microsoft
  - Technology
tags:
  - Anti-Virus
  - Conflicker
  - Downadup
  - Kido
  - Technology
  - Virus
  - Windows
  - Worm
---
Millions of Windows computers have been infected by a new computer worm dubbed &#8220;Conficker.&#8221; The situation is &#8220;not getting better,&#8221; but rather is &#8220;getting worse,&#8221; according to security software vendor F-Secure.

In a [blog post](http://www.f-secure.com/weblog/archives/00001584.html), F-Secure security researchers report that the number of machines infected by the Downadup worm has skyrocketed from roughly 2.4 million to over 8.9 million in the last four days alone.

Downadup is a malicious worm that &#8220;uses computer or network resources to make complete copies of itself,&#8221; according to F-Secure. And it may also include code or other malware that damages both a computer and network. The worm also goes by the names &#8220;Kido&#8221; and &#8220;Conflicker.&#8221; Details on how it operates and how to remove it are [here](http://www.f-secure.com/v-descs/worm_w32_downadup_al.shtml#details).

Once executed, Downadup disables a number of system services, including Windows Automatic Update, Windows Security Center, Windows Defender, and Windows Error Reporting. The worm then connects to a malicious server, where it downloads additional malware to install on the infected computer. Computerworld provides a more detailed report on Downadup&#8217;s potential dangers.

Since Downadup uses random extension names to avoid detection, Windows users should make sure their security software is set to scan all files, rather than checking on specific extensions, F-Secure recommends.

The alarmingly high number of Downadup infections led Microsoft last Tuesday to enable its anti-malware utility, Microsoft Software Removal Tool (MSRT), to detect the worm. So it&#8217;s important that Windows users, if they haven&#8217;t already, download the latest Microsoft security patch that went out earlier this week.

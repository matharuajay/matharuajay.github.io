---
toc: false
id: 908
title: Is Firefox secured enough
date: 2009-02-20T13:08:12+00:00
author: Ajay Matharu
layout: post
guid: http://ajaymatharu.wordpress.com/?p=908
permalink: /is-firefox-secured-enough/
ljID:
  - 190
dsq_thread_id:
  - 465388108
categories:
  - Browsers
  - Firefox
  - Technology
  - Web
tags:
  - Browsers
  - Firefox
  - Internet
  - Mozilla
  - Security
  - Technology
  - Web
---
Mozilla&#8217;s open source Firefox browser has made a significant dent in Internet Explorer&#8217;s dominant market share. Much of its popularity is due to the wide availability of third-party add-ons that significantly extend Firefox&#8217;s functionality &#8212; allowing Firefox to disable Java or JavaScript on the fly, perform JavaScript whitelisting, even host ActiveX controls, for example. Firefox has always pushed the boundary in terms of features and functionality, and it can boast both growing enterprise support and the ability to run on Windows, Mac, and Linux. One claim Firefox can&#8217;t make is a high granularity of security control.

Firefox does not automatically ask for elevation when installing, so be sure to run as administrator beforehand if you want it to install the browser into the normal Program Files folder in Windows Vista or another user-securable location. If installed on Vista, Firefox runs as a single process (Firefox.exe) with medium integrity, DEP (Data Execution Prevention) and ASLR (Address Space Layout Randomization) enabled, and file system and registry virtualization disabled. The latter is a feature in Vista that allows users to run applications without having administrative privileges.

Like Google Chrome, Firefox has a JavaScript engine that converts JavaScript source code into native machine code; Firefox uses an open source engine called <a href="https://wiki.mozilla.org/JavaScript:TraceMonkey" target="_blank">TraceMonkey</a>. Unlike Chrome, in which the V8 JavaScript engine is always on, Firefox&#8217;s JavaScript support can be enabled or disabled across the browser. By using the [NoScript add-on](http://noscript.net/), you can enable JavaScript (and Java and Flash) on a per-site basis.

Although add-ons such as NoScript, and plug-ins such as Adobe Flash, bring many useful capabilities to Firefox, at the same time they come with problems and security issues of their own. Firefox has a built-in add-on manager that allows you to browse available extensions, install and uninstall them, and enable and disable them, but again, they can&#8217;t be enabled or disabled with per-site granularity.

Security can be defined through the normal Tools > Options menu or by typing &#8220;about:config&#8221; in the URL bar. The latter option opens up hundreds of behind-the-scenes settings, similar to what might only be found among the registry settings of other browsers. Serious users always configure security using the about:config method, although detailed descriptions on each option can be a little hard to find.

Firefox has a &#8220;safe mode&#8221; that can be launched to recover from disasters. Even better, whereas Internet Explorer only disables all add-ons by default, Firefox Safe Mode allows you to erase the history files, return browser settings to the defaults, make other necessary changes, and then automatically restart in normal mode. It&#8217;s a great little feature.

Firefox passed 9 of the 21 password handling tests on the <a href="http://www.info-svc.com/news/2008/12-12/pm-evaluator/" target="_blank">Password Manager Evaluator</a>. Firefox allows locally stored passwords to be protected by a separate master password, and even tells you how strong your master password is.

Naturally, Firefox&#8217;s popularity has brought out the attackers. Many different attacks &#8220;in the wild&#8221; specifically target Firefox users, making it the second-most-attacked browser behind Internet Explorer. Firefox 3.0 has had at least 39 separate vulnerabilities in less than six months (as compared to 154 vulnerabilities for Firefox 2.0 during its lifetime). Seventy-five percent of these exploits were ranked high-criticality, and a third allowed complete system compromise.

One of the common complaints about Firefox is its lack of support for the enterprise. Although Mozilla doesn&#8217;t directly offer tools to ease large installations or to centrally manage Firefox through Group Policy, these are available from independent providers including FirefoxADM and FrontMotion.

All in all, Firefox is a sophisticated open source browser that has earned its place as a market leader. Like Internet Explorer, Firefox enjoys widespread popularity and third-party support. And like Internet Explorer, it continues to struggle with frequently found vulnerabilities, perhaps due in part to the vendor&#8217;s commitment to SDL (Security Development Lifecycle) processes, which initially lead to more vulnerabilities being uncovered during testing. Firefox makes a good browser choice for anyone, but especially for users who want to purposefully avoid Internet Explorer (and ActiveX) or who don&#8217;t need the finest granularity (e.g., multiple security zones) in their browser&#8217;s security.

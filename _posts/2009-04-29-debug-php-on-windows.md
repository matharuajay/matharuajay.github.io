---
toc: false
id: 1153
title: Debug PHP on Windows
date: 2009-04-29T10:31:47+00:00
author: Ajay Matharu
layout: post
guid: https://www.ajaymatharu.com/?p=1153
permalink: /debug-php-on-windows/
aktt_notify_twitter:
  - no
ljID:
  - 224
dsq_thread_id:
  - 465389889
categories:
  - Development
  - Featured Articles
  - PHP
  - Web
tags:
  - Debug
  - Execute
  - Extensions
  - PHP Debug
  - Wamp
  - Windows
  - Zend
  - Zend Debugger
---
Following are the steps to debug your PHP code using Zend Debugger on Windows machine via WAMP,

1. Download <a rel="nofollow" href="https://downloads.zend.com/pdt/server-debugger/ZendDebugger-5.2.12-cygwin_nt-i386.zip" target="_blank">https://downloads.zend.com/pdt/server-debugger/ZendDebugger-5.2.12-cygwin_nt-i386.zip</a> or check for new version at <a rel="nofollow" href="https://downloads.zend.com/pdt/server-debugger/" target="_blank">https://downloads.zend.com/pdt/server-debugger/</a>

2. Locate ZendDebugger.so or ZendDebugger.dll file that is compiled for the
  
correct version of PHP (4.3.x, 4.4.x, 5.0.x, 5.1.x, 5.2.x) in the
  
appropriate directory.

Get debugger from folder called &#8220;5\_2\_x\_comp&#8221; or you may receive some errors about a non-thread   safe debugger if you take it from &#8220;5\_2\_x\_nts_comp&#8221;

3. Configure php.ini for output buffering when debugging

 <span style="color: #000000;">implicit_flush </span><span style="color: #000000;">=</span> <span style="color: #000000;">On ; Default: Off<br /> output_buffering </span><span style="color: #000000;">=</span> <span style="color: #000000;">Off ; Default: 4096</span>

4. Add the following line to the php.ini file:
  
Linux and Mac OS X:     zend_extension=/full/path/to/ZendDebugger.so
  
Windows:                zend\_extension\_ts=/full/path/to/ZendDebugger.dll
  
Windows non-tread safe: zend_extension=/full/path/to/ZendDebugger.dll

(*) the windows non-thread safe is used only with Zend Core 2.0

Note:
  
if you don&#8217;t have a Zend section you may add this at the end of the fie.
  
correct the php path if it is not installed in c:\wamp\www and extension directory.

5. Add the following lines to the php.ini file:
  
zend\_debugger.allow\_hosts=<ip_addresses>
  
zend\_debugger.expose\_remotely=always

This willl allow connections from local host and from your local network to addresses which start        with 192.168.1.

6. Place dummy.php file in the document root directory.

7. Restart web(Apache/Wamp) server.

8. To activate the debugger please use following query string:
  
?start\_debug=1&debug\_port=10000&debug\_fastfile=1&debug\_host=192.168.1.59%2C127.0.0.1

<span style="font-weight: bold;">Note: </span>
  
above statement assumes that the debugger listens at 192.168.0.2 or 127.0.0.1 on port 10000.

Here are some of the screen shots from my debugger,

<div style="width: 635px" class="wp-caption aligncenter">
  <img title="Breakpoint in Zend" src="https://ajaymatharu.wordpress.com/files/2009/04/main.gif" alt="Breakpoint in Zend" width="625" height="350" />
  
  <p class="wp-caption-text">
    Breakpoint in Zend
  </p>
</div>

This is watch window in Zend which will show the values of the variables, you need to add the variable to the watch window to view its values.

<div style="width: 495px" class="wp-caption aligncenter">
  <img title="Watch Window in Zend" src="https://ajaymatharu.wordpress.com/files/2009/04/watch_window.gif" alt="Watch Window in Zend" width="485" height="169" />
  
  <p class="wp-caption-text">
    Watch Window in Zend
  </p>
</div>

This is the output window that shows the output generated by the code executed till now,

<div style="width: 635px" class="wp-caption aligncenter">
  <img title="Output Window in Zend" src="https://ajaymatharu.wordpress.com/files/2009/04/output_window.gif" alt="Output Window in Zend" width="625" height="400" />
  
  <p class="wp-caption-text">
    Output Window in Zend
  </p>
</div>

Hope this helps <img src="https://www.ajaymatharu.com/wp-includes/images/smilies/simple-smile.png" alt=":-)" class="wp-smiley" style="height: 1em; max-height: 1em;" />
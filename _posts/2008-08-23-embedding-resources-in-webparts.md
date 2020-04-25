---
tags: 
  - misc
toc:  false
id: 60
title: Embedding resources in WebParts
date: 2008-08-23T14:02:41+00:00
author: Ajay Matharu
layout: post
guid: https://ajaymatharu.wordpress.com/?p=60
permalink: /embedding-resources-in-webparts/
ljID:
  - 11
dsq_thread_id:
  - 465357972
categories:
  - Sharepoint
---
Today I came across a requirement of showing an swf file in the webpart. So I thought I will upload the swf file in folder and give its url to the webpart. But then that will be hardcoded path. What will happen if the user deleted that folder or rather deleted that file itself? So my webpart will not run.

So I found some alternative to this and thought of embedding my swf file and js file in webpart itself. I googled on how can I do this, and here are the steps for embedding the files in the webpart itself.

I ll assume that you are ready with the Webpart and you just need to remove the hard coded file&#8217;s url&#8217;s in your webpart. And i ll be using swfobject.js file in this example you can change the file and the type though, as per your requirements.

&#8211; Add swfobject.js file in the same project as webpart.

&#8211; Right click on js file select properties and change build action to &#8220;Embedded Resource&#8221;.

&#8211; Make an entry in AssemblyInfo.cs or AssemblyInfo.vb file like

[assembly: WebResource(&#8220;ReadENote.swfobject.js&#8221;, &#8220;text/js&#8221;)]

format : [assembly: WebResource(&#8220;<project namespace>.<filename>.<extension>&#8221;, &#8220;<content type>&#8221;)]

Note : Make sure you specify the namespace along with filename else it will not recognize the file.

&#8211; You can access this embedded resource in your webpart code like this

Type t = typeof(<webpartname>); //e.g. Type t = typeof(ReadENote);
  
string js = &#8220;<namespace>.<filename>.<extension>&#8221;; //e.g. string js = &#8220;ReadENote.swfobject.js&#8221;;
  
jslocation = Page.ClientScript.GetWebResourceUrl(t, js);
  
Page.ClientScript.RegisterClientScriptResource(t, js);

This code will embed the specified file, in this case swfobject.js file in my webpart.

Note: you only need to use the last line &#8220;Page.ClientScript.RegisterClientScriptResource(t, js);&#8221; if you are using the javascript file. If you are using some other file like an image file or swf file, you can use the jslocation in place of your hard coded location.

&#8211; my previous code to embed swf file looks like this

strBody = strBody + &#8220;var so = new SWFObject(\&#8221;notes.swf\&#8221;, \&#8221;stickies\&#8221;, \&#8221;250\&#8221;, \&#8221;250\&#8221;, \&#8221;9\&#8221;, \&#8221;#FF6600\&#8221;);&#8221;;

&#8211; my code after using these steps will look like this

Type t = typeof(<webpartname>);

string js = &#8220;<namespace>.<filename>.<extension>&#8221;;

jslocation = Page.ClientScript.GetWebResourceUrl(t, js);

strBody = strBody + &#8220;var so = new SWFObject(\&#8221;&#8221; + swflocation + &#8220;\&#8221;, \&#8221;stickies\&#8221;, \&#8221;250\&#8221;, \&#8221;250\&#8221;, \&#8221;9\&#8221;, \&#8221;#FF6600\&#8221;);&#8221;;

Make these changes, build and deploy your web part.

Enjoy dynamic coding and prevent hard code.

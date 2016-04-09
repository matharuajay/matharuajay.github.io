---
id: 2827
title: The operation has timed out with HttpWebRequest
date: 2013-12-30T14:42:15+00:00
author: Ajay Matharu
layout: post
guid: http://www.ajaymatharu.com/?p=2827
permalink: /the-operation-has-timed-out/
dsq_thread_id:
  - 2081442091
categories:
  - .Net
  - ASP.Net
---
Recently we were using HttpWebRequest. Things were working fine until we bumped into, &#8220;The Operation has timed out&#8221;.

## ERROR

> ##  The operation has timed out

It was running perfectly fine but all of a sudden it stopped working. Later we identified that the request URL was HTTPS. We just changed HTTPS to HTTP and the code worked again. But changing HTTPS to HTTP is not the solution. It is a quick fix.

The site with HTTPS was working in the browser. We got all the responses from the browser. However, We get this error with HttpWebRequest. HttpWebRequest worked with Http URL but not with HTTPS.

Later we started to look into the problem. We made sure our firewall was configured correctly. We contacted the third party guys they said they are not getting the request with HTTPS. It was clear there is some problem. We figured out that HttpWebRequest got stuck at a stage where it&#8217;s supposed to send back a client key exchange which it didn&#8217;t.

## Solution

Then we forced HttpWebRequest to use SSL3 instead of TLS. Although TLS automatically turns into SSL3 but it din&#8217;t happen. So the fix to the problem was

> ## ServicePointManager.SecurityProtocol = SecurityProtocolType.Ssl3;

 Just place the above line before calling GetResponse() and that was it.

To read more about ServicePointManager &#8211; http://msdn.microsoft.com/en-us/library/system.net.servicepointmanager.securityprotocol(v=vs.110).aspx
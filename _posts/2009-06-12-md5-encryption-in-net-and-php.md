---
toc: false
id: 1273
title: MD5 Encryption in .Net and PHP
date: 2009-06-12T10:32:32+00:00
author: Ajay Matharu
layout: post
guid: http://www.ajaymatharu.com/?p=1273
permalink: /md5-encryption-in-net-and-php/
ljID:
  - 254
dsq_thread_id:
  - 465390472
categories:
  - .Net
  - PHP
  - Visual Studio
tags:
  - .Net
  - ASP.Net
  - 'C#.Net'
  - Development
  - Encryption
  - MD5
  - PHP
  - vs.net
---
To get MD5 hash in C# use this method. It returns same value AS MD5() function in PHP

<pre name="code" clas="c-sharp">public string GetMD5Hash(string input)
        {
            System.Security.Cryptography.MD5CryptoServiceProvider x = new System.Security.Cryptography.MD5CryptoServiceProvider();
            byte[] bs = System.Text.Encoding.UTF8.GetBytes(input);
            bs = x.ComputeHash(bs);
            System.Text.StringBuilder s = new System.Text.StringBuilder();
            foreach (byte b in bs)
            {
                s.Append(b.ToString("x2").ToLower());
            }
            string password = s.ToString();
            return password;
        }
</pre>

And this one is in PHP

<pre name="code" class="php"><?php 
echo md5("pathfinder");
?>
</pre>

These both will return the same value

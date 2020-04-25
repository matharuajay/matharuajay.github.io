---
toc: false
id: 950
title: A Free Defense Against the Conficker Worm
date: 2009-02-10T00:48:19+00:00
author: Ajay Matharu
layout: post
guid: https://ajaymatharu.com/?p=950
permalink: /a-free-defense-against-the-conficker-worm/
ljID:
  - 182
dsq_thread_id:
  - 465389544
categories:
  - Technology
  - Virus
tags:
  - Conflicker
  - Downadup
  - Technology
  - Virus
---
The rampaging Conficker worm (aka Downadup) has managed to infect millions of PCs across the globe, but it has an Achilles heel. One that a company called OpenDNS plans to strike starting Monday.

Many types of malicious software like Conficker have to connect to a command center to receive orders, which in the case of Conficker might be to download additional software like a keylogger or data-stealing Trojan. Without those orders, the malware just sits there.

Conficker uses an algorithm to create a list of 250 domain names each day that it will check for commands, according to David Ulevitch, CEO of OpenDNS. So its creators can register any of those 250 domains for any given day and be able to issue orders to the millions of worms.

Antivirus companies like F-Secure and Kaspersky have cracked that algorithm and can predict which domains Conficker will attempt to contact on any given day, and F-Secure has previously offered that predictive list to network administrators who could use it to block computers in their network from connecting to any of those domains.

Come Monday, OpenDNS will use a similar approach to block any computer or network that uses the company for its domain name system (DNS) service, which translates the human-friendly names like ajaymatharu.com into the IP addresses used by machines, from getting a DNS record for a Conficker domain. Using a list from Kaspersky, OpenDNS will refrain from sending a requested domain-name-to-IP-address translation for any such domain, effectively neutering the worm by blocking it from reaching a command center.

Those who have signed up for a free OpenDNS account will receive a warning e-mail that a computer within their home or business network is likely infected with Conficker if OpenDNS blocks a connection attempt, says Ulevitch. But you can also use the service without signing up for an account, which will still block the connection attempt without sending a warning e-mail. Account holders will also be able to check the service dashboard for a warning.

This is a good, layered defefnse approach that can be of particular use for small businesses or home networks who aren&#8217;t able to use blocklists themselves. If you&#8217;re at all concerned that you might have computers in your home or business network infected with Conficker, it&#8217;s quick and easy to begin using OpenDNS. The company says it plans to expand the approach in the future.

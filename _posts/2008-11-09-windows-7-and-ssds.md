---
toc: false
id: 432
title: 'Windows 7 and SSD&#8217;s'
date: 2008-11-09T16:29:57+00:00
author: Ajay Matharu
layout: post
guid: http://ajaymatharu.wordpress.com/?p=432
permalink: /windows-7-and-ssds/
ljID:
  - 85
dsq_thread_id:
  - 465392810
categories:
  - Technology
tags:
  - NVMHCI
  - SSD
  - Technology
  - Windows 7
---
The first generation of solid-state drives (SSDs) introduced in PCs last year failed to live up to the hype.

Though praised for using less power and generating less heat than conventional hard disk drives, SSDs weren&#8217;t as fast as promised. Their capacity and longevity, especially with low-end models found in netbooks, left a lot to be desired.

Much of that was due to the poor quality of the SSDs themselves. But another problem was that neither the hardware nor the software had caught up to SSDs.

At its Windows Hardware Engineering Conference (WinHEC) in Los Angeles this week, Microsoft Corp. promised that the upcoming Windows 7 would work better with SSDs , though SSD makers and PC makers will need to do their part, too.

Optimizing SSDs for Windows 7 is key. Sales of laptops, especially netbooks , are on the rise. Meanwhile, SSD prices are plummeting, while capacities and quality grows. According to Gartner Inc. data shared by Microsoft, a 512GB SSD that costs almost $600 today should be less than $300 by 2010, when Windows 7 is expected to be officially released.
  
First, Windows 7 will turn off disk defragmentation when it detects an SSD instead of a spinning disk drive.

Defragging disks speed ups the reading of data from conventional hard drives by moving similar data together. But flash-based SSDs are already fast at reading data. Rather, SSDs are slow at writing data. Moreover, the process of erasing and moving data requires &#8220;flashing&#8221; the memory cells with high voltage. That gradually wears out the SSD.

Defragmentation thus shortens an SSD&#8217;s lifespan without improving performance, Shu said.

Second, Windows 7&#8217;s new &#8220;trim&#8221; feature will improve performance three ways. It will: Reduce the amount of data to be deleted, which improves the SSD&#8217;s lifespan; delete garbage data in advance, which speeds up writing of data; and maximize the amount of unused data, which helps even out the wear and tear on the SSD.

Third, Windows 7 will partition the SSD more efficiently to cut down on unnecessary read-write cycles, Shu said. This requires Windows 7 to be installed fresh and not upgraded from XP, since the latter OS formats SSDs in an inefficient way.

Finally, Microsoft plans to create a certification program for SSDs. To win the software maker&#8217;s logo of approval, SSDs must identify themselves to Windows 7 properly, prioritize data reads over slower data writes, comply with the Serial ATA (SATA) drive interface for faster connections, and more.

On the other hand, Microsoft is not taking more radical steps. For instance, it&#8217;s not trying any tricks to decrease the number of times data is written, such as using RAM to cache data.

Writing data to flash memory, especially small amounts of it, takes 100 times longer than reading it, according to SanDisk.

SanDisk&#8217;s Barnetson agrees that Microsoft is limited by what it can do in this vein.
  
Moreover, Microsoft appears unlikely to have Windows 7 adopt a new disk interface technology written specifically to boost the speed and longevity of SSDs. It&#8217;s called Non-Volatile Memory Host Controller Interface. Developed by Intel, NVMHCI would replace the ATA interface that was developed originally for hard disk drives (though, out of necessity, also used by SSDs today).

Ironically, Microsoft has publicly backed NVMHCI&#8217;s development as a potential future standard, but it is unwilling to commit yet to using NVMHCI.

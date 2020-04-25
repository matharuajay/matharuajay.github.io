---
toc: false
id: 617
title: 'Visual Studio 2010 &#8211; My Review'
date: 2009-07-25T12:03:31+00:00
author: Ajay Matharu
layout: post
guid: https://ajaymatharu.wordpress.com/?p=617
permalink: /visual-studio-2010-my-review/
bte_opp_original_pub_date:
  - 2008-12-12 11:54:38
dsq_thread_id:
  - 465385442
categories:
  - .Net
  - Development
  - Technology
  - Visual Studio
tags:
  - .Net
  - .Net Framework 4.0
  - Development
  - Technology
  - Visual Studio
  - Visual Studio 2010
  - Visual Studio 2010 Review
  - vs.net
---
Hi Guys, Microsoft released Visual Studio 2010 CTP in October. You&#8217;ll be amazed with the download size its near about 7 GB. You can download it from <a href="https://www.microsoft.com/downloads/details.aspx?familyid=922b4655-93d0-4476-bda4-94cf5f8d4814&displaylang=en" target="_blank">here</a>.

After you download you&#8217;ll run the .exe file to extract the setup and the setup is of the .vhd format that is Virtual PC hard disk. So you&#8217;ll need Virtual PC to run Visual Studio 2010.

But, but, but guys please check out the minimum requirement for this CTP to run. Hard disk space required is 75 GB, yes, its not 7.5 but 75 GB. Well that&#8217;s not true you can have this CTP run if you have upto 25 GB on one drive.

When you extract the .exe file the .vhd file extracted is of size 23 GB.  Also when you bind the .vhd file to the virtual pc, you need minimum 1GB ram allocated to the Virtual PC disk.

When I ran the Visual Studio for the first time the screen took around 10 mins to load and I just shut down the CTP and got back to work.

The reason for the extracted file to be of 23 GB is because that VHD when you map to Virtual PC will have Visual Studio 2010, Visual Studio 2008,  SQL  Server 2008, SQL Server 2005 + many more software installed.

When you execute the Virtual PC which is mapped to VHD, Virtual PC will load Windows Server 2008 and it takes lots of  burden it killed my laptop. Although I have fair enough configuration. My processor is Core 2 Duo, 1.83 GHZ and with 1 GB ram. Yet it just killed my PC performance.

I even tried to extract the file on an External Hard Disk and Even on my IPod classic. But I was able to extract only first rar file. I googled the reason and found it was because the External Hard Disk is of FAT32 format and they do not support data transfer of more than 4GB. So I had to clean up my Hard Disk and extract 23 GB .vhd file there.

I really did not understood why Microsoft shipped Visual Studio 2010 this way. With 7GB download size and 23 GB extracted file. I was really disappointed with such strategy. Microsoft must have shipped Visual Studio 2010 as a single file. What could be the reason for adopting this process?

Here is my Virtual PC screen shot with Visual Studio 2010

<p style="text-align:center;">
  <img class="aligncenter size-full wp-image-616" title="vs2010" src="https://ajaymatharu.files.wordpress.com/2008/12/vs2010.jpg" alt="vs2010" width="650" height="406" />
</p>

---
toc: false
id: 1143
title: To add an unknown extension in IIS
date: 2009-04-20T19:54:18+00:00
author: Ajay Matharu
layout: post
guid: https://www.ajaymatharu.com/?p=1143
permalink: /to-add-an-unknown-extension-in-iis/
aktt_notify_twitter:
  - no
ljID:
  - 220
dsq_thread_id:
  - 465391680
categories:
  - Microsoft
  - Technical
  - Technology
tags:
  - Extensions
  - IIS
  - Management
  - Microsoft
---
To add an unknown extension in IIS for your IIS to detect that extension perform the following steps.

To define a MIME type for a specific extension, follow these steps:

  1. Open the IIS Microsoft Management Console (MMC), right-click the local computer name, and then click **Properties**.
  2. Click **MIME Types**.
  3. Click **New**.
  4. In the **Extension** box, type the file name extension that you want (for example, <span class="userInput">.pdb</span>).
  5. In the **MIME Type** box, type <span class="userInput">application/octet-stream</span>.
  6. Apply the new settings. Note that you must restart the World Wide Web Publishing Service or wait for the worker process to recycle for the changes to take effect. In this example, IIS now serves files with the .pdb extension.

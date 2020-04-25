---
toc: false
id: 512
title: Visual Studio 2010 Parallel Development Overview
date: 2008-12-17T11:22:23+00:00
author: Ajay Matharu
layout: post
guid: http://ajaymatharu.wordpress.com/?p=512
permalink: /visual-studio-2010-parallel-development-overview/
ljID:
  - 126
dsq_thread_id:
  - 465387094
categories:
  - Technology
  - Visual Studio
tags:
  - .Net
  - .Net Framework 4.0
  - Parallel Development
  - Visual Studio
  - Visual Studio 2010
  - Visual Studio Parallel Development
  - vs.net
---
**Parallel Development**

As demands for application performance increased, customers
  
have traditionally solved the problem by simply increasing the
  
underlying power of the hardware that the application is running
  
on. Over the last several years developers have seen the CPUs
  
that their applications run on start to include 2, 4 or more cores.
  
While the power of the hardware has increased, the transition
  
to a multi-core environment has impacted the applications that
  
developers write. The majority of applications will not be able to
  
automatically take advantage of this multi-core hardware change.
  
Developers will need to modify the way they write applications
  
and the architectures they use for these applications.

Creating parallel capable code using current technologies is
  
unfortunately not trivial. Multi-thread programming introduces
  
not only application architecture challenges to complexity and
  
robustness but also exposes the tooling developers use as being
  
optimized for single-threaded development.

Microsoft is making a major commitment to make parallel
  
development accessible to a wide range of developers, whether
  
they are using native code or the .NET Framework. With Visual
  
Studio 2010 we are delivering:

• Visual Studio IDE support for Parallel development
  
• Native C++ libraries and compiler support
  
for Parallel applications

The .NET Framework 4.0 also provides the core framework
  
support to build parallel applications through technologies such
  
as P-LIINQ and parallel language semantics and framework
  
components. Visual Studio 2010 provides integrated parallel
  
development support. In Visual Studio 2010 the debugger is
  
aware of the parallel nature of code and can present the state of
  
the application execution during debugging across the different
  
parallel execution units. The debugger also has custom displays
  
for parallel code such as task & thread windows and a &#8220;multi&#8221; or
  
&#8220;cactus&#8221; stack view window that graphically shows the execution
  
path of the individual tasks.

Being able to develop and debug your application doesn&#8217;t
  
mean that it takes advantage of all the available power. To
  
help developers do this, Visual Studio 2010 also includes
  
a parallel capable performance analyzer that enables you
  
to extensively instrument you code to visually see the
  
concurrency issues that are in your applications. Combine
  
this with the features of the Visual Studio IDE, and developers
  
have a highly productive, visual environment for building the
  
best parallel capable applications available.

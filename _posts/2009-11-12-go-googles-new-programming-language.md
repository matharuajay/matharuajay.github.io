---
toc: false
id: 1824
title: 'Go &#8211; Google&#8217;s new programming language'
date: 2009-11-12T17:10:53+00:00
author: Ajay Matharu
layout: post
guid: http://www.ajaymatharu.com/?p=1824
permalink: /go-googles-new-programming-language/
aktt_notify_twitter:
  - no
dsq_thread_id:
  - 465392418
categories:
  - Development
  - Google
  - Technology
tags:
  - Development
  - Go
  - Go Programming
  - Go programming language
  - Google
  - Programming
---
Google created their own programming language. But is there a need to create a new language?
  
Well here is some details about the Go programming language.

Go offers an expressive type system, fast compilation, good performance, and built-in language features that simplify threaded programming and concurrency. The language has been under development for roughly two years. It started out as a 20 percent project—time that Google&#8217;s engineers are given to use as they choose for undirected experimentation—and evolved into a serious full-time undertaking. Google is releasing the source code under the BSD license with the hope that a community will emerge around the new programming language and participate in the effort to make it a compelling choice for software development.

Go language itself and the current implementation are relatively mature, but it&#8217;s not quite ready for adoption in production environments. The ecosystem around the programming language is still a work in progress. There is no IDE integration, the standard libraries are a bit thin, and there aren&#8217;t a whole lot of real-world code examples yet. Opening up Go to the broader programming community could help to vastly accelerate its advancement in all of those critical areas.

The native Go compilers, called 6g and 8g (for 64-bit and x86), are designed to be extremely fast. There is also an alternative compiler called Gccgo that is based on the GNU Compiler Collection (GCC). The GCC-based compiler isn&#8217;t as fast but is said to generate more efficient code. I was initially a bit surprised that Google chose not to use the Low-Level Virtual Machine (LLVM) compiler framework—it has a lot of LLVM expertise internally and is using it extensively for their awesome Python optimization effort. Pike says that LLVM was considered during the early stages of the Go project, but its compile-time performance was judged to be inadequate.

The compiled executables are completely native binaries, so it&#8217;s not like a managed code language where the compiler generates bytecode for a virtual machine. Go does, however, have some runtime components that get embedded in the executables. Actual execution performance is said to be comparable to that of native C.

Some of Google&#8217;s sample Go code reveals that the syntax is C-like and encourages a conventional imperative programming style. There are functions, &#8220;for&#8221; loops, standard conditional expressions, and many other features that you&#8217;d expect to find in a C-like language, but with a handful of nice twists. For example, there is a shorthand syntax for variable assignment that supports simple type inference. It also has anonymous function syntax that lets you use real closures. There are some Python-like features too, including array slices and a map type with constructor syntax that looks like Python&#8217;s dictionary concept. The following code snippet is an example from Google&#8217;s documentation:

<pre name="code" type="c++">package main

    import (
        "os";
        "flag";  // command line option parser
    )

    var omitNewline = flag.Bool("n", false, "don't print final newline")

    const (
        Space = " ";
        Newline = "\n";
    )

    func main() {
        flag.Parse();   // Scans the arg list and sets up flags
        var s string = "";
        for i := 0; i &lt; flag.NArg(); i++ {
            if i &gt; 0 {
                s += Space
            }
            s += flag.Arg(i)
        }
        if !*omitNewline {
            s += Newline
        }
        os.Stdout.WriteString(s);
    }

</pre>

One of the distinguishing characteristics of Go is its unusual type system. It eschews some typical object-oriented programming concepts such as inheritance. You can define struct types and then create methods for operating on them. You can also define interfaces, much like you can in Java. In Go, however, you don&#8217;t manually specify which interface a class implements. Pike explained to me that the interface mechanism gives developers some of the flexibility of duck-typing, but it goes further by providing the advantages of compile-time checking.

Parallelism is emphasized in Go&#8217;s design. The language introduces the concept of &#8220;goroutines&#8221; which are executed concurrently. Any function can be executed as a goroutine by prefixing the function call with the &#8220;go&#8221; keyword. The language provides a &#8220;channel&#8221; mechanism that can be used to safely pass data in and out of goroutines.

For more details, check out the project&#8217;s [official website](http://golang.org/).

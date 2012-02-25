---
date: '2006-06-09 20:34:56'
layout: post
comments: true
slug: gmp-421-on-solaris-10sparcv9-64-bit
status: publish
title: GMP 4.2.1 on Solaris 10/sparcv9, 64-bit
wordpress_id: '123'
categories:
- Code
- News
---


With the loaner Sun T2000, we're trying to build code that does serious math, using the C++ STL and the magnificent [GNU GMP](http://www.swox.com/gmp/) library. I finally got to the point of getting a clean build and link on Solaris, only to get this:

    
    
      ld.so.1: radical: fatal: /usr/local/lib/libstdc++.so.6: wrong ELF class: ELFCLASS32
    



Much googling led to [the email thread](http://lists.gnu.org/archive/html/bug-gmp/2002-10/msg00051.html). The fix?


    
    
      typeset LD_LIBRARY_PATH_64=/usr/local/lib/sparcv9:/usr/local/lib 
    



Now we'll see how fast this machine is compared to my G4 laptop. Lots of integer math, lots of data movement, should be well suited to [the Niagara architecture](http://www.theinquirer.net/?article=19423):


> 
Niagara signals the first volley in a new way of thinking about servers, or at least a class of servers. The whole idea of Disruptive Threads, as Marc Tremblay calls, it is quite real, and it will take a while for many people to understand, much less use. Threads, threads and more threads, that is what this chip lives for.


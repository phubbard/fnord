---
date: '2008-07-16 12:06:17'
layout: post
slug: man-sometimes-i-feel-really-dumb
status: publish
title: Man, sometimes I feel really dumb.
wordpress_id: '747'
categories:
- Code
- Macintosh
---

[![](http://fnord.phfactor.net/wp-content/uploads/2008/07/picture-11.png)](http://fnord.phfactor.net/wp-content/uploads/2008/07/picture-11.png)So I'm trying to fix a bug in some old C code, where I want to add the ability to bind to a specific IP instead of INADDR_ANY. This is on my Apple laptop, which has the latest Apple Xcode (3.1) build on it. Oddly, the C compiler starts spewing bizarro error messages on code that I'm pretty sure is valid. So I backtrack, download Xcode 3.0 (gigs!), and that compiles it OK.

But the binary segfaults when you run it! So now I don't have a working compiler. This is a problem for a code monkey...

Today, I tried again:



	
  * Code builds and runs on Linux

	
  * Download latest Xcode 3.1 from Apple, install.

	
  * Compile fails.

	
  * Go digging around hard drive, find copy of hello.c I have parked. (Yes, real nerds keep 'hello world' saved, in several languages, for just such occasions as this!)

	
  * Compile hello.c:


` cc hello.c
/var/folders/Sw/SwEOWKQ7FdihT03Yr5CBOU+++TI/-Tmp-//ccNBFXHP.s:15:section difference divide by two expression, "LC0" minus "L00000000001$pb" divide by 2 will not produce an assembly time constant
`
Well. Same errors as my code, though only one of them. It's not (prolly) libraries, so WTF? Guess I'm off to flog the DSL downloading Xcode 3.0. Man, this sucks. Fink? Something else I've installed? No luck googling the error, oddly. Since I'm pretty sure others would've noticed a broken C compiler, it's probably my problem. Crap.

**Update 8/18/08**: See Per Mildner's comment - the secret is MallocScribble.

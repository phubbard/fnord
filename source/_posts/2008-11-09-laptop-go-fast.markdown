---
date: '2008-11-09 16:57:23'
layout: post
slug: laptop-go-fast
status: publish
title: Laptop Go Fast
wordpress_id: '824'
categories:
- Code
- Macintosh
---

I was fiddling around with [the CUDA code](http://fnord.phfactor.net/2008/10/28/cuda-on-the-macbook-aluminum/) on the new Macbook and got some interesting-to-me benchmarks. Keep in mind that this is the cheaper of the Mac laptop lineup, using the slower Nvidia chip:

[![](http://fnord.phfactor.net/wp-content/uploads/2008/11/picture-5-450x401.png)](http://fnord.phfactor.net/wp-content/uploads/2008/11/picture-5.png)

Yeesh!  1.6GB/sec to the device, and 5.8GB/sec once there!

[![](http://fnord.phfactor.net/wp-content/uploads/2008/11/picture-6-450x401.png)](http://fnord.phfactor.net/wp-content/uploads/2008/11/picture-6.png)

Not sure how to interpret all of these yet; clearly each core has a fixed allocation of memory to play with. 800MHz seems slow, not sure if that's correct or not.

16 cores on a laptop! Wow.

[![](http://fnord.phfactor.net/wp-content/uploads/2008/11/picture-7-450x401.png)](http://fnord.phfactor.net/wp-content/uploads/2008/11/picture-7.png)

This seems to be a benchmark based on the [Black-Scholes option pricing PDE](http://en.wikipedia.org/wiki/Black-scholes). Again over 5GB/sec of usable device bandwidth. Damned impressive.

I've yet to try writing code, just running the sample code from the download, but it's still amazing. Laptops are now portable supercomputers, particularly if you get the Macbook Pro - 24 vs 16 cores, even faster. This is really looking good for tightly-coupled code, it'll be a challenge to port [the lock-free ABC code](http://code.google.com/p/alphabet/) to this model and make it run well.

---
date: '2008-10-28 16:53:34'
layout: post
slug: cuda-on-the-macbook-aluminum
status: publish
title: CUDA on the MacBook Aluminum
wordpress_id: '811'
categories:
- Code
- Macintosh
---

One of the reasons to upgrade to the new MacBook is the new motherboard/chipset combo. It went from an Intel system to an Nvidia one, with the consequent addition of the NV9400M GPU. If you've not looked recently, this is a mobile part, which usually means slower and older than desktop chips. This one, however,


> With 16 parallel processing cores and a 128-bit memory interface, the GeForce 9400M is able to deliver up to 54 Gigaflops of processor power


(That's from [this article](http://www.hexus.net/content/item.php?item=15932))

54 gigaflops is fifty four _billion_ floating point operations per second. That's really, really fast. Nvidia has a programming system called [CUDA](http://www.nvidia.com/object/cuda_get.html) that allows you to tap all of that goodness, and it's available for OSX too. Version 2.0 works for me, but I had the following two problems that I wanted to mention:



	
  1. The initial 'make' from /Developer/CUDA fails with a library error. Running

    
    
     ranlib * 
    


in /Developer/CUDA/lib solves this and then the build succeeds.

	
  2. The programs then all fail to run with this error

    
    dyld: Library not loaded: @rpath/libcudart.dylib


The fix for that, found [here, ](http://forums.nvidia.com/index.php?s=4cf93eec89d41d761b8e1f1f626f4e7b&showtopic=79062&pid=455362&st=0&#entry455362) is to define DYLD_LIBRARY_PATH. My zshrc looks like this, also showing the modified path:

    
    typeset CUDA_HOME=/usr/local/cuda
    
    typeset DYLD_LIBRARY_PATH=$CUDA_HOME/lib
    
    typeset PATH=${HOME}/bin:${ANT_HOME}/bin:/usr/local/bin:$CUDA_HOME/bin:/Library/
    OpenSC/bin:${PATH}





I'm now experimenting to see how fast it runs the examples, so more later. I wonder how well this'd run [the alphabet code](http://www.phfactor.net/abc/)? Hmm.

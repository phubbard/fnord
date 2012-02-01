---
date: '2008-08-15 10:01:20'
layout: post
slug: progress-in-ray-tracing
status: publish
title: Progress in ray tracing
wordpress_id: '769'
categories:
- Geek stuff
---

Way back in 98 or so, Chris Woody and I built a 8-CPU Linux cluster using NFS, Povray and homebuilt task partitioning code in C. Ahh, good times - thinnet & hand-installs on freaky flaky hardware. 

![Stack of 486\'s](http://www.phfactor.net/clusterfsck/pile.jpg)

Overall, we got about half the performance of a Pentium-II, which was decent, mostly due to the efficiency with which Povray can slice up a rendering job. You can see more details [on the project page](http://www.phfactor.net/clusterfsck/).

I bring this up because today I see t[he newest nVidia hardware/software](http://www.hothardware.com/News/NVIDIA-Shows-Interactive-Ray-Tracing-on-GPUs/) that does raytracing a la Povray... in real time, at 30 frames per second, at 1920x1200:

[![](http://fnord.phfactor.net/wp-content/uploads/2008/08/big_nvidia_rt_demo2-450x253.jpg)](http://fnord.phfactor.net/wp-content/uploads/2008/08/big_nvidia_rt_demo2.jpg)

Yowza. The times, they _are_ amazing.

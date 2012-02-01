---
date: '2006-11-28 20:54:37'
layout: post
slug: raid5-initial-benchmarks
status: publish
title: RAID5 initial benchmarks
wordpress_id: '251'
categories:
- Debian
- Linux
---


Now that its been up a few weeks, the [hardware RAID5 card](http://www.phfactor.net/wp/2006/11/11/hardware-and-software-raid5-under-linux/) seems to be running well. 

Whew.

Today, with an idling system, I did some simplest block-IO benchmarks. This just writes and then reads a large number of 1B blocks to and from disk. There's 1GB of memory in the system, so this should well exceed the IO kernel cache.


    
    
    
    time dd if=/dev/zero of=1G bs=1M count=1024
    1024+0 records in
    1024+0 records out
    1073741824 bytes (1.1 GB) copied, 17.27 seconds, 62.2 MB/s
    
    real    0m17.283s
    user    0m0.000s
    sys     0m2.720s
    usul:/mnt# sync
    usul:/mnt# time dd if=1G of=/dev/null bs=1M
    1024+0 records in
    1024+0 records out
    1073741824 bytes (1.1 GB) copied, 25.9455 seconds, 41.4 MB/s
    
    real    0m25.947s
    user    0m0.004s
    sys     0m2.700s
    usul:/mnt# time dd if=/dev/zero of=2G bs=1M count=2048
    2048+0 records in
    2048+0 records out
    2147483648 bytes (2.1 GB) copied, 46.3935 seconds, 46.3 MB/s
    
    real    0m46.410s
    user    0m0.016s
    sys     0m5.428s
    usul:/mnt# time dd if=2G of=/dev/null bs=1M
    2048+0 records in
    2048+0 records out
    2147483648 bytes (2.1 GB) copied, 55.5036 seconds, 38.7 MB/s
    
    real    0m55.573s
    user    0m0.008s
    sys     0m5.480s
    usul:/mnt# time dd if=2G of=/dev/null bs=1M
    2048+0 records in
    2048+0 records out
    2147483648 bytes (2.1 GB) copied, 56.2326 seconds, 38.2 MB/s
    
    real    0m56.294s
    user    0m0.020s
    sys     0m5.624s
    



Not bad at all, not fibre channel but respectable. I expected a bit faster, so I'll have to dig a bit and see what's going on. OK for now, though.


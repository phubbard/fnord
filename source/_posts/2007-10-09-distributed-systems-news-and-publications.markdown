---
date: '2007-10-09 20:18:28'
layout: post
comments: true
slug: distributed-systems-news-and-publications
status: publish
title: Distributed systems news and publications
wordpress_id: '497'
categories:
- Code
- Geek stuff
- Networking
---

First off, [a nice paper](http://www.allthingsdistributed.com/2007/10/amazons_dynamo.html) that talks about how Amazon builds their system to be scalable and reliable.

(I blogged about [a related item](http://www.phfactor.net/wp/2007/09/18/interesting-biz-tips-from-amazon/) not long ago)

Next up, a bit of _very_ good news. I've been bummed that the brilliant (and I do not exaggerate) Google innovation of '[map-reduce](http://labs.google.com/papers/mapreduce.html)' for parallelism is proprietary. As in, I can't look at it, try it, deploy it, etc. Ditto for [GoogleFS](http://labs.google.com/papers/gfs.html) and [BigTable](http://labs.google.com/papers/bigtable.html). Bummer, that, but it makes corporate sense.

Today, I found the Apache [Hadoop project](http://lucene.apache.org/hadoop/), which as far as I can tell explicitly recreates map-reduce **and** gfs! This pic is from their site:


![](http://www.phfactor.net/wp-pics/hadoop-architecture-wpa.jpg)


What's more, it's not a toy project either:


> Hadoop has been demonstrated on clusters with 2000 nodes. The current design target is 10,000 node clusters.


The filesystem is similarly designed:


> The Hadoop Distributed File System (HDFS) is a distributed file system designed to run on commodity hardware. It has many similarities with existing distributed file systems. However, the differences from other distributed file systems are significant. HDFS is highly fault-tolerant and is designed to be deployed on low-cost hardware. HDFS provides high throughput access to application data and is suitable for applications that have large data sets. HDFS relaxes a few POSIX requirements to enable streaming access to file system data. HDFS was originally built as infrastructure for the Apache Nutch web search engine project. HDFS is part of the Apache Hadoop project, which is part of the Apache Lucene project.


Killer stuff! I've lost track of some of this stuff, but had [read on the Register](http://www.theregister.co.uk/2007/10/02/ibm_gpfs_3point2/) about an update to [IBM's GPFS](http://www-03.ibm.com/systems/clusters/software/gpfs/index.html) that also sounded cool. It'll be interesting to see which is more advanced, but I'm delighted that distributed computing is once again a cool and happenin' thing.

Hmm, it looks like Hadoop is a) Java-based and b) [designed for single-computer installs](http://lucene.apache.org/hadoop/api/overview-summary.html#overview_description), so I don't need monster hardware to play with it:


> By default, Hadoop is configured to run things in a non-distributed mode, as a single Java process.

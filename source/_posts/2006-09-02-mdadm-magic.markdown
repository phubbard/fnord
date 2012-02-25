---
date: '2006-09-02 22:31:08'
layout: post
comments: true
slug: mdadm-magic
status: publish
title: mdadm magic
wordpress_id: '199'
categories:
- Debian
- Geek stuff
---


     mdadm -Cv /dev/md0 -l5 -n3 -x0 /dev/sd{b,c,d}1
    



is the magic required to create a RAID-5 array, no spares, from devices sdb, c and d, partition 1, type flag 0xFD of course.

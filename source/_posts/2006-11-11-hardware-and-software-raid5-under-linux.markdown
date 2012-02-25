---
date: '2006-11-11 23:40:49'
layout: post
comments: true
slug: hardware-and-software-raid5-under-linux
status: publish
title: Hardware and software RAID5 under linux
wordpress_id: '243'
categories:
- Debian
- Geek stuff
- Linux
---

I run phfactor.net from a server that we have at home, a basic PC running Debian Linux. It runs essentials like DNS, web, ssh, slimserver, e-mail, database, subversion and so forth. Until recently, I've been on a Dell P4 (unlike the good old days of six Sun SPARC machines!), and I needed to move off the Dell. At the same time, we've been moving more data onto the server and wanted to add space. The cheapest option was to buy 3x 250GB SATA drives from newegg.com and RAID them together.

For this, RAID5 or RAID4 would be appropriate, since it's mostly going to hold our CD collection, i.e. 5-10MB files. I wanted parity, not mirroring, since it's more efficient in its use of space. With 3x250, that'd give us 500GB of usable space with the ability to withstand a single drive failure.

Of course, any sysadmin will tell you that RAID makes for super-fast errors, too. It's not a backup, but it's better than nothing. The commodity drives of today, while incredible, don't seem to last as long as they used to and I really hate re-ripping CDs.

So, I put it all together and started hacking. I discovered that Linux software RAID5 would work, creating and formatting the volume just fine, but when I really started stressing it, the software would indicate a drive failure. It usually happened after 400GB or more were scp'd onto the new volume set, so it was a serious pain to test.

This went on for weeks. Swapped hardware, rearranged drives, reinstalled Debian, tried different kernels, etc, etc. To no avail.

This is the current solution:

![Hardware Raid](http://www.phfactor.net/wp-pics/lsi-sata-raid.jpg)


The [product page is here.](http://www.lsi.com/storage_home/products_home/internal_raid/megaraid_sata/megaraid_sata_1504/index.html)

There are numerous buyer-beware 'SATA RAID' cards out there. Most can do RAID0/RAID1/JBOD in hardware, but fall back on drivers for RAID 4/5. This one is the real deal, with 64MB of ECC memory, 4 SATA channels and Linux support.

(Oh yeah, its an LSI Logic 150-4, appx 250 on various search engines. We got it at Fry's and therefore paid a bit more.)

Because of the hardware, the RAID parity is calculated in hardware, you've got hardware cache memory, and it's even bootable. The array is still initializing (background process, it's already formatted and I'm working it hard to see how it fares.)

If this works, it's cheap at the price. This is the Nth time I've tried software RAID, and I have yet to have satisfactory results. It _could_ be me doing something stupid, but I dunno. Sometimes, its just better to solve the problem with superior hardware. ;)

---
date: '2006-03-11 11:49:48'
layout: post
slug: blackberry-syncml-and-such
status: publish
title: Blackberry, SyncML, and such
wordpress_id: '73'
categories:
- Blackberry
- Data transport
- Macintosh
- Software, add-on
---

I've been having data loss issues trying to sync my blackberry with both the laptop and the work machine. Very problematic, and hard to resolve since the utility of the handheld drops greatly if its data is stale, missing or incorrect.

Anyway, I took a look around today, and found some interesting pieces.

Item one: [SyncBerry](http://www.mobilecreek.com/products.htm), a $30 program for OTA (over the air, very desirable) sync. It says it talks to any SyncML server, which leads us to...

Item two: [MultiSync](http://www.multisync.org/news.php?page=2&PHPSESSID=85c714bdb206c2205b1687e1e223d32f), open source for SyncML. Not sure how to use this, but **it** links to...

Item three: [The project formerly known as Sync4j](http://www.funambol.com/opensource/), now called Funambol. Full syncml, explictily supports blackberry.

There's also a half-item, a [syncml plugin for multisync](http://packages.debian.org/unstable/libs/libmultisync-plugin-syncml)

Not sure how all this fits together, or if it'd work with Deban + OSX, but I sense an extended hack adventure in the near future.

UPDATED 10/24/06: Last one isn't sync4j (text corrected), although they do use the same protocol. See comments!

---
layout: post
title: "iPhoto hang fix"
date: 2013-01-02 17:12
comments: true
categories: iPhoto
---

A quick note for anyone else out there seeing this particular problem: Starting in October or so, iPhoto would hang during startup, endlessly displaying a busy cursor. I tried restoring older backups, to no avail, and finally manned up and used lsof and some patience. The fix was to remove a directory:

	mv ~/Library/Containers/com.apple.iPhoto old-iPhoto
	
and we're back in business. I'm actually ashamed to admit it took me this long; in my defense each restore-from-backup took almost 3 hours (USB2 backup drive, 130G of pictures) so it was a very tedious exercise.

I spotted the culprit with

	lsof | grep iPhoto | grep -v System | grep -v Application
	
which reduced the list down to something possible.

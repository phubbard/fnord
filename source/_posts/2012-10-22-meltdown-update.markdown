---
layout: post
title: "Meltdown update"
date: 2012-10-22 16:04
comments: true
categories: Meltdown
---

Got my first request for a binary today, so version 0.4.8 build 30 is [posted here](http://www.phfactor.net/Meltdown.apk). Give it a try!

Working

* Groups and feeds - note that feeds not in a group are collated into a hardcoded 'Orphan feeds' group
* Updates are run as an intent service, using inexact mode to save battery life, every fifteen minutes.
* Marking groups and items as read works, using a neat little AsyncTask
* Mark as saved works
* Displaying an item now has a relative timestamp at the bottom of the screen, and feed title and post name at the top.
* Sharing (via the Android system) works a treat
* Added a new feature that I've long wanted - it makes a calendar entry for a URL, e.g. 'remind me about this in a week when it ships'. I quite like this one.
* Added a menu item to zoom out when viewing a post - some image-heavy feeds mess with WebView, and as far as I can tell there's no easy way to fix it. Zooming out is a workaround, really.
* Items are cached on the local flash storage, encoded as JSON with one file per entry. Works, fast, easy to manage.
* Added an about page, with some basic info, GitHub URL and basic stats.
* Refresh now triggers a server sync

Bugs

* The background service is not yet interlocked with the activities and Application class, so there are several places where it can crash due to this. I'm refactoring now for a clean solution.
* Working on an adaptive, multi-column layout that'll use the Nexus 7 better. Fragments, ActionBar tabs and such; in progress now. 
* Items are duplicated; repeatable but not yet solved. Bug in the serverSync routine that resolves read versus unread.

It's a fun project, and already I'm using it a lot. Just so nice to be reading posts in 1-2 seconds from grabbing the phone. **Speed is a feature**.

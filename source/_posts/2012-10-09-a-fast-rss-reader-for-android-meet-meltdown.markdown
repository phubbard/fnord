---
layout: post
title: "A fast RSS reader for Android: Meet 'Meltdown'"
date: 2012-10-09 08:46
comments: true
categories: Android Meltdown coding
---
## Introduction
For some time now, I've been steadily been working on a side project to scratch a personal itch: A fast RSS reader for Android. I've got [Android hardware to use](http://fnord.phfactor.net/2012/07/18/trying-the-galaxy-nexus-and-nfc/) and am carrying a Samsung Galaxy S3 as my main phone. I had bought [Reeder for iPhone](http://reederapp.com/iphone/) and would have gladly paid for something similar.

I should back up here and explain my RSS situation. I have cycled through using [NetNewsWire](http://netnewswireapp.com), then [Google Reader](http://google.com/reader), [NewsBlur](http://newsblur.com) and finally [Fever](http://feedafever.com). Given the fact that Fever costs $30 and the others are free, I should explain that I prefer to run my own services. I learn more, control my usage data and can add hardware if it's slow.

So there you are. Fever is a magnificent piece of code, but there's no native Android client and the web app does poorly on the browser. **But Fever has an API!** A [nicely documented one](http://feedafever.com/api) with [a neat AJAX test script](https://github.com/phubbard/Meltdown/blob/master/scripts/api-widget.html) to boot.

## Goals and requirements
I want a feed reader that caters to how I read RSS feeds:
 
* **Speed is priority #1**. Fast interface, downloads and updates in the background, fast fast *fast*. I typically have a few minutes here and there where I can pull out my phone and I want the app to work well for a quick dive.
* No excessive permissions, no phoning home, no BS. Avoid stupid mistakes like saving passwords and similar.
* Handle *lots* of feeds and stories. I currently have 800+ feeds, and have seen up to 10,000 unread stories. The app must deal.
* Must be easy to mark groups or threads as read and move on quickly.
* Must be easy to share a post via email or Instapaper, Pinboard, Twitter, etc.
* I have groups sorted by priority and subject, and in each group I typically read stories newest-first with feeds mingled together.
* I also read from my desk using my laptop, so the reader needs to handle server sync, with stories, feeds and groups coming and going. I also plan on exploring tablet coding with the Nexus 7, so 3-way sync and tablet-optimized design are necessary.

My goals for the project start with

* This will be [open source on Github](https://github.com/phubbard/Meltdown) of course.
* Uploaded to [the Android app store](http://play.google.com) - I've created an account but the code's not ready to unleash yet.
* Use this as a way of learning more about writing a nice Android app. UI conventions, responsiveness, updates, integration et cetera.
* Have fun!

There's lots more I can do with the project, but I do better if I keep the scope down and start small. It can always get bigger later, but if I make sure to always have running code it's a lot easier to jump in when I have a few spare minutes.

I'll post here now and then as I learn interesting bits and want to share them. Android development info is less common on the net, so it's often difficult to find sample code and docs for what I want to do and I should do my part here.

## Meet Meltdown
Yeah well, the name is a bit of wordplay on Fever (excessive heat) and my own radiation worker background. So Meltdown it is. As of 10/9/12, the code status is alpha-grade:

* Background-running IntentService for syncing groups, feeds and stories
* Simple in-memory data structures for groups, feeds and mapping between  them. The stories are held in memory and also written to individual JSON-encoded files, and are lazy-loaded when you actually view a story. I'll do a separate post on this as it was pretty interesting.
* Background AsyncTask-based marking of stories and groups as read
* Service-to-Activity communications via the LocalBroadcastManager
* Requires only Internet and run service permissions
* Does not save username or password, only the generated API key which is the MD5 hash of them
* Only communicates with the server you specify - no special permissions required. Should run from SD or internal storage.
* Tested and running on Android v4 and 4.1. It could be backported, but frankly since this is for me I don't care. The ActionBar and NotificationBuilder and such are nice APIs and the -v4 support library is more of a pain. I'm happy to help if you want to do some coding here.
* I have at least one feature that may only be useful for me: I subscribe to a handful of RSS feeds from discussion forums, which produces tens of stories with the same title when threads run long. If you long-press one of them, Meltdown will find the entire thread and mark it as read. It's a small but gratifying feature that I use but need to make a preference, since I doubt it's of much use outside of RSS-feed forums.
* **It works for reading news** but is crashy. I need to refactor the data structures to use thread-safe arrays and rethink how I iterate over them. But you can pull it out, read some news and it works. You can open URLs in your browser of choice, share posts using the Android sharing menu, mark items to save on the server, mark entire groups as read (with confirmation) and the Downloader runs every 15 minutes via the AlarmService. Seems to use minimal battery.

There are lots of bugs. Follow along as I plug away and feel free to comment, pull the code or just email me questions or comments.
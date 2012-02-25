---
date: '2006-07-08 13:26:49'
layout: post
comments: true
slug: synergy-psp-video-encoding-and-xgrid
status: publish
title: Synergy, PSP, video encoding and Xgrid
wordpress_id: '132'
categories:
- Macintosh
- News
- PSP
- Video
---


![PSP, pic from Wikimedia](http://www.phfactor.net/wp-pics/250px-Psp1.jpg)


A while ago, while on a [12 hour flight](http://www.phfactor.net/pics/Taiwan-04-06/), I decided that I _needed_ a [Sony PSP](http://www.us.playstation.com/Content/Sites/65/Info/). My laptops' batteries last 2 hours on a good day, the iPod video playback lasts maybe 3, and I was **bored.** Really bored. Bored like 'Calvin and Hobbes waiting for the bell to ring' bored.

Combined with this is the fact that I finally admitted to myself: My PC is a game console.

There, I said it.

What's more, it's a high maintenance game console that's still in its box since we moved, because there's no place to put it in this rental house. So it's a _worthless_ game console.

What I want is something that starts up fast, requires no maintenance, patches, updates or firewall, and Just Works. I want a Game Appliance, damn it!

Other factors: 



	
  1. I want a screen good enough to use as a video playback device. The ipod video at 2", is way too small for any sort of enjoyment; you lose too much detail and have to really hold it close to your face.

	
  2. Battery life. More is better.

	
  3. Games.



The PSP scores on all these. The stock battery is good for 5+ hours (1.8Ah), and I paid [$20 for a 2.6Ah](http://www.lik-sang.com/info.php?category=218&products_id=8803&)that lasts 8+ hours. You also need [ a good case](http://www.amazon.com/gp/product/B0008G2OWS/qid=1146147022/sr=8-1/ref=pd_bbs_1/104-2912188-2944767?%5Fencoding=UTF8&v=glance&n=468642) and a big memory stick. I paid $45 for a 2GB on ebay. 

For video, the PSP uses MPEG4, with a proprietary file header; stock MP4 files won't play. It also has [some annoying limits on bitrate and resolution](http://en.wikipedia.org/wiki/PlayStation_Portable) for files played from memory vs UMD. 

**Update 5/5/07:** Version 3.30 firmware [removes the bitrate limitation](http://www.phfactor.net/wp/2007/04/15/ahh-finally-hi-res-psp-video-encoding/).

(Wow, this post is getting long. Sorry.)

You will, therefore, need some way to get video **onto** the PSP. This is where [synergy](http://en.wikipedia.org/wiki/Synergy) comes in. There are a few programs to do video ripping and encoding:



	
  1. [PSPware.](http://www.nullriver.com/index/products/pspware)

	
  2. [ipsp.](http://ipsp.kaisakura.com/)

	
  3. [Instant Handbrake.](http://handbrake.m0k.org/?page_id=26)

	
  4. Last but best, [VisuallHub.](http://www.techspansion.com/visualhub/)



So I've now paid for VisualHub, and am ready to transcode any of the DVDs I've ripped from our collection. You immediately find that video encoding burns _major_ CPU time, and heats up a laptop really fast.

Introduce the next trick to solve this: [Xgrid.](http://www.apple.com/server/macosx/features/xgrid.html) This is Apple's self-discovering easy-to-configure grid/network computing software. VisualHub can use it to distribute encoding jobs across a network. 

It's a little tricky to configure, so here's the next good bit: [This tutorial on setting it up on OSX.](http://www.macgeekery.com/gspot/2006-06/setting_up_an_xgrid_controller_in_tiger)

Workflow looks like this now:



	
  1. Rip DVDs with Handbrake, encoding to full-res at 1.6Mbps with 192kbps audio. This gives full-fidelity for laptop viewing.


	
  2. Use VisualHub and xgrid to reduce those files down for PSP. (I recommend the highest quality setting, since its maxes out at 768kbps anyway).

	
  3. Copy video files onto PSP using its USB disk mode.



The converted files are much smaller, so I can afford the disk space to keep them around. I can carry a DVD-ROM full of PSP-encoded video, so I have plenty of content if (as on the last trip) I get stuck overnight somewhere when I miss a connecting flight. 

The combo of PSP, hardcase and extended battery works pretty well; I have something with long life that I can just toss in my carryon. 

One more trick: The UMD video games (good lists are [here](http://playstation.about.com/od/toppicks/tp/PSPTopReleases.htm), [here](http://psp.ign.com/articles/619/619558p1.html) and [here](http://www.metacritic.com/games/psp/scores/).) are somewhat fragile. While looking for an improvised carrying case, I found an empty Altoids Sours can, which works _perfectly_, holding 3 UMDs and a memory stick. (Of course, [I'm not the first to notice this.](http://www.psp411.com/show/review/449)) 

The only negative so far is that the PSP does not charge over USB, so I have to carry another charger. However, with the 2 batteries I can skip it for all but the longest trips. So far 14 hours of battery life has sufficed for a 2-week trip with 7 flight legs and 3 hotel stays.

**Update 5/5/07:** See [this post for a USB charge/data cable, $7. Solves that problem.](http://www.phfactor.net/wp/2007/05/05/another-psp-essential/)

Highly recommended!

PS I still run debian on my primary server, and don't plan to change that. This gives me _some_ geek cred...

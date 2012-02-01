---
date: '2006-07-08 12:48:49'
layout: post
slug: itunes-frustrations-part-n
status: publish
title: iTunes frustrations, part N
wordpress_id: '131'
categories:
- Audio, sound and music
- Debian
- Macintosh
---

It shouldn't be this hard. We have two iPods, a Mini, and my desktop at work. The mini sees the MP3's as [an NFS drive](http://www.phfactor.net/wp/2006/01/22/nfs-and-osx-tiger-automounts/). The server is my Debian box.

Goals:



	
  1. Sync iPod's here and at work.

	
  2. Keep the MP3s sync'd, so I can rip new CDs here or there.

	
  3. Play mp3s from the fileserver using [my Squeezebox](http://www.phfactor.net/wp/?s=squeezebox&submit=GO)



Problems:

	
  1. iTunes/ipod forces you to pair the ipod with a **single** computer, so #1 is probably impossible, at least with itunes.

	
  2. The itunes database doesn't notice if the music on disk changes, and has no native way to 'add missing' or similar. I've attempted, using Unix scripts and Automator, to add any new files to itunes, but have been stymied by st00pid stuff like spaces in filenames.



Progress so far:

	
  1. I now understand and use [Unison](http://www.cis.upenn.edu/~bcpierce/unison/) to sync the laptop and desktop twice a day, and _think_ I can use it to sync the MP3s on disk.

	
  2. I just found [this Lifehacker post](http://www.lifehacker.com/software/itunes/hack-attack-automatically-sync-itunes-to-any-folders-175161.php) on syncing itunes with a directory. Hmm...


	
  3. Squeezebox now has a setting to sync every 24 hours, which is fast enough for me. If I really need faster, I have the source code.




Haven't tried the Lifehacker post yet, but it looks like it might be the missing part. Nice.


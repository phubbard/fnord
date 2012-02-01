---
date: '2006-01-26 23:00:16'
layout: post
slug: more-squeezebox-hacking
status: publish
title: More squeezebox hacking
wordpress_id: '52'
categories:
- Audio, sound and music
---

[![Pic of my mp3 player](http://www.phfactor.net/wp-pics/slim_devices_squeezebox.png)](http://slimdevices.com/)



### NPR


Y'know, what I **really** want is simple - to be able to tune in to NPR from my squeezebox now and then, and catch some programs that I like. You'd expect that to be easy, right?

Nope. I've just [installed mplayer on Debian](http://www.princessleia.com/MPlayer.php) so that [AlienBBC](http://www.x2systems.com/AlienBBC/) can work so that [PublicRadioFanBrowser](http://www.malsbury.net/~slim/) can work. 

Note that this requires several very odd steps, like downloading Windows link libraries, because many of the mplayer-supported formats are proprietary. Interesting world we live in.

Whew. AlienBBC, at least, works - I can tune into those stations, and mplayer transcodes them on the fly from Real into MP3. That's pretty cool.

PublicRadioFan, which apparently hooks into the [website of the same name](http://www.publicradiofan.com), is still borked. 

All this because the most popular programs (Marketplace, All Things Considered, Car Talk) are locked behind paywalls. If you wanna good laugh, look up the price of Marketplace on iTunes music store some time. As if!



### Server, performance, Mac v Linux


I had no end of problems running Squeezebox on the Mini. Every time the server rescanned the library, or itunes updated its podcasts and triggered a rescan, the squeezbox would either drop connection, glitch the audio, or both. I spent a **lot** of time debugging this one, and here's what I came up with.

We have (alas) version 1 of the squeezebox hardware. It seems they put too small of an audio buffer in it, so that any short server glitch causes it to lose its little brain. The v3 hardware has increased this from [2MB](http://reviews.designtechnica.com/review835_specs4174.html) to a mind-boggling [64MB](http://www.slimdevices.com/pi_specs.html), which probably fixes the problem.

For me, moving the server from the mini to my main server, a Dell 3GHz P4 running Debian, has _totally_ fixed the problem. Even rescanning the library, compiling code, etc, have no audible effect.Much better. (This with a library of about 11,000 tracks, circa 80GB).
 

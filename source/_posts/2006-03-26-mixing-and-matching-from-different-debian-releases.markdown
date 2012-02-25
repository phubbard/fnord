---
date: '2006-03-26 00:50:39'
layout: post
comments: true
slug: mixing-and-matching-from-different-debian-releases
status: publish
title: Mixing and matching from different Debian releases
wordpress_id: '80'
categories:
- Audio, sound and music
- Debian
---

![squeezebox v1](http://www.phfactor.net/wp-pics/slim_devices_squeezebox.png)

My squeezebox has been down for a while, and I had some time this weekend to hack on it.

Tarballs and RPMs from slimdevices failed in different and entertaining ways, so off to Google I went. Much RTFM'ing later, I found a slimserver package in unstable with a nest of dependencies. I run testing, since this is my sole server, and didn't want to switch to unstable.

Solution: Setup apt-get preferences to _allow_ unstable but prefer stable and testing. Genius!

Instructions [on this page.](http://jaqque.sbih.org/kplug/apt-pinning.html) The technique is called apt-pinning.

For some reason, I get no font display on the squeezebox, but at least I have music again. Wish those lusers at slimdevices had made Pandora work on v1 hardware, though.

UPDATED 3/26/06: It looks like the Perl GD library didn't work on testing due to unstated dependencies on libXft and libpng, and I couldn't make it work. Instead, I added [the Slimdevices apt source to my file and installed their version.](http://forums.slimdevices.com/showthread.php?t=20603&page=9)

I lost the nice Debian theme, but the display works.

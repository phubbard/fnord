---
date: '2010-03-29 09:08:40'
layout: post
slug: real-time-audio-manipulation
status: publish
title: Real-time audio manipulation
wordpress_id: '1236'
categories:
- Audio, sound and music
---

Way back at UNM, I worked on the problem of audio positioning via convolutions and HRTFs, using wavelets. The results weren't as hoped ([details here](http://www.phfactor.net/wdconv/), the filters didn't compress well at all), but I keep an eye out for the state of the art. I just found [SweetSpotter](http://www.ias.et.tu-dresden.de/akustik/sweetspotter/), an unfortunately-Windows-only thesis project of amazing promise.

[![Screen shot 2010-03-29 at 10.05.57 AM](http://fnord.phfactor.net/wp-content/uploads/2010/03/Screen-shot-2010-03-29-at-10.05.57-AM-450x366.png)](http://www.ias.et.tu-dresden.de/akustik/sweetspotter/)

It ups the ante of audio positioning by _using your webcam_ to see where you are, and adjusting the filtering in realtime to correct.

That is, to use the proper technical adjective, fucking **amazing**.

Sebastian Merchel did the work. I am impressed. As soon as the borked webcam on my MacBook gets fixed, I'll see if I can run this in VMWare or VirtualBox.

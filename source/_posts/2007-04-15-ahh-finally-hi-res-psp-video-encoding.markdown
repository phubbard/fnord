---
date: '2007-04-15 20:30:36'
layout: post
comments: true
slug: ahh-finally-hi-res-psp-video-encoding
status: publish
title: Ahh, finally! Hi-res PSP video encoding
wordpress_id: '314'
categories:
- Geek stuff
- PSP
- Travel
---


![PSP!](http://www.phfactor.net/wp-pics/250px-Psp1.jpg)


As noted in [my previous PSP post](http://www.phfactor.net/wp/2006/07/08/synergy-psp-video-encoding-and-xgrid/), one annoyance of the PSP was that video from Memory stick was limited to less-than-full resolution, probably to push UMD video sales. It took a while, but hackers cracked that limitation, and shortly thereafter official PSP firmware version 3.30 removed it as well. Full-res 480x272 16 by 9 glory can be yours!

I trundled off to the [Visualhub](http://www.techspansion.com/visualhub/) forums, and put in a feature request, and commended myself to patience. (After, of course, trying to hack the advanced settings in visual hub, which produced a file soundly rejected by my PSP. Sigh.)

Anyway, today [the Tao of Mac solved it for me:](http://the.taoofmac.com/space/Applications/VisualHub)



> 
Converting video to the new PSP 3.30 480x272 native resolution (16:9 ratio):

    * PSP / AVC / Go Nuts
    * In the advanced panel: set res to 480 x 272
    * In the ffmpeg options: "-bf 1 -level 21"




I'm-a encoding now... Man, I hope this works. I have some travel coming up, and a few hours of ultra-res widescreen would _really_ help.

Tip from last trip: **Avoid JFK. Period.**

---
date: '2010-09-22 15:20:24'
layout: post
slug: more-on-code-and-productivity
status: publish
title: More on code and productivity
wordpress_id: '1295'
categories:
- Code
---

A while ago, I [looked at code productivity](http://fnord.phfactor.net/2010/05/25/a-look-at-productivity-and-metrics/) on my current project. To add a bit more data, here are three snapshots from my previous work at [Argonne](http://mcs.anl.gov/). Anecdotal, and perhaps not flattering, but interesting enough to share. **Click the images for the full data set - you can explore.**

First project is C code, using POSIX threads, that moves data between a LabVIEW-based data acquisition system and a Java-based streaming server. Pretty basic stuff - command line parsing, worker thread and connection management, a bit of logging, most of the code is in the error handling.

[![Screen shot 2010-09-22 at 4.03.35 PM](http://fnord.phfactor.net/wp-content/uploads/2010/09/Screen-shot-2010-09-22-at-4.03.35-PM-450x496.png)](http://www.phfactor.net/code_stats/driver/)

Gotta start strong - pretty nice. High initial progress due to importing code (messaging library and some code I wrote at Fermilab for sockets), stabilized rapidly and refactored a bit to cleanup code. The initial 'mad coding phase' was some of my fastest work, climbing from ~1500 lines to 4500 lines 2 months! Damn.

Second project is Java based, plugin code for Globus 3-based-server that controlled stepper motors, cameras and servohydraulics. More complex to write, but depends on a container to run, and my role here was less.

[![Screen shot 2010-09-22 at 4.03.14 PM](http://fnord.phfactor.net/wp-content/uploads/2010/09/Screen-shot-2010-09-22-at-4.03.14-PM-436x600.png)](http://www.phfactor.net/code_stats/plugins)

Here the code grew fast, but I had a trivial 1303 lines total. In my defense, some of this was at the same time as the previous project, so not too shabby.

Next project is a collection of Java programs that read, write and process data from a [DataTurbine](http://dataturbine.org/) server. MJPEG drivers, data acquisition systems, etc.

[![Screen shot 2010-09-22 at 4.03.43 PM](http://fnord.phfactor.net/wp-content/uploads/2010/09/Screen-shot-2010-09-22-at-4.03.43-PM-450x501.png)](http://www.phfactor.net/code_stats/turbine/)

Lots and lots of code, mostly by the awesome Terry Weymouth. He was fantastic to work with, as you can see here - consistent progress all the time, and always able to burst more for a deadline.

Despite the well-known weaknesses of 'lines of code' as a metric, I find it fascinating to see measurements on work I know or did. It still has some value to show the progress of the project, and how the code is done. For example, only on the C code is there significant removal of code, showing cleanup and refactoring.

Cool stuff. This was all produced by [StatCVS](http://statcvs.sourceforge.net/), which automatically parses a CVS archive. Hey, it was years ago, and CVS was still a viable choice. ;)

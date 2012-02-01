---
date: '2009-12-03 13:01:36'
layout: post
slug: a-quick-nexuiz-tip
status: publish
title: A quick Nexuiz tip
wordpress_id: '1170'
categories:
- Games
---

[![nexuiz_logo](http://fnord.phfactor.net/wp-content/uploads/2009/12/nexuiz_logo.jpg)](http://www.alientrap.org/nexuiz/)Since this took me a while to figure out, I'll post it here. A few of us have been blowing off steam playing [Nexuiz](http://www.alientrap.org/nexuiz/), a free cross-platform first person shooter originally based on one of the Quake engines, called DarkPlaces.

Nexuiz is a lot of fun, doesn't require a lot of learning, and plays very well over a network. There's a single download, with binaries for Windows, Linux and OSX. (Both SDL and native versions)

After doing some googling, I figured out how to write a short macro and bind it to a key. This one does a laser-assisted jump while you hold down the q key. It looks down, switches to the laser, fires, and when you release the key it looks back up and switches back to the previous weapon. Cute, eh?


    
    
    alias +laser_jump "+lookdown; impulse 1; +attack"
    alias -laser_jump "-lookdown; -attack; impulse 11"
    bind q +laser_jump


Seems to work, though there may be a better way to do this. Note that other weapons like the rocket send you higher in the air; this is just a starting point. Save this to

    
    ~/.nexuiz/data/autoexec.cfg


and it'll persist and be loaded automatically. Enjoy!

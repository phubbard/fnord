---
date: '2006-01-22 01:34:01'
layout: post
comments: true
slug: nfs-and-osx-tiger-automounts
status: publish
title: NFS and OSX (Tiger) automounts
wordpress_id: '48'
categories:
- Macintosh
- Networking
---

Even after epic hacking, different wireless setups, subnetting, etc, etc, the [Squeezebox](http://www.slimdevices.com/) continues to glitch when playing tunes from the mini.

Damnation.

So the next thing to try is move the music to linux, NFS mount it onto the mini, and see if that works. That way, I can still use iTunes for podcasts. Wish Apple'd port it to Linux.

Anyhoo, the point of this post is to bookmark [this page explaining automount](http://naeblis.cx/rtomayko/2004/08/09/NFSAutomountOSX) in a _very_ clear manner. Avoids the NetInfo GUI altogether, and the only thing missing is the 

    
    
      sudo killall -HUP automount
    


step.

We'll see how this works, but if nothing else I can now have my music on my central server, where it gets better care than the random laptop drive I have it on now.

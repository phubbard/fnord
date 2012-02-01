---
date: '2006-05-13 22:37:29'
layout: post
slug: fourteen-thousand-one-hundred-and-eight
status: publish
title: Fourteen thousand one hundred and eight
wordpress_id: '106'
categories:
- Debian
- Networking
- News
---

...invalid login attempts on my ssh service since May eighth. That's about 2351 per day. 

Many of the attempts are from China, in particular Beijing. If this is revenge for [visiting the renegade province](http://www.phfactor.net/pics/Taiwan-04-06/) then I'm impressed. "I don't like it, but I'm impressed" to quote Natalie Imbruglia.

Anyway, I've tightened up the various bits, grepped and scanned, run backups, etc, which should shut down the bots, but its damned annoying. This is **Debian**, and I have no accounts named 'toor', 'student' or the like.

Damned script kiddies. Makes me want to reinstall OpenBSD as a packet forwarding firewall. You can do some very clever and useful tricks as pf rules that aren't possible elsewhere.

UPDATE 5/14/06: Wei suggested I add [Denyhosts](http://denyhosts.sourceforge.net/), which I have now done. We'll see how it works! I have it set to very strict, and expect quite a few host entries.

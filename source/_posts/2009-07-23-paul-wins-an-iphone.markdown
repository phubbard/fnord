---
date: '2009-07-23 00:22:28'
layout: post
slug: paul-wins-an-iphone
status: publish
title: Paul wins an iPhone!
wordpress_id: '1054'
categories:
- Code
- iPhone
---

[caption id="attachment_1055" align="aligncenter" width="450" caption="The iPhone 3GS"][![The iPhone 3GS](http://fnord.phfactor.net/wp-content/uploads/2009/07/picture-11-450x265.png)](http://www.apple.com/iphone)[/caption]

On July 14th, hosting company Engine Yard [posted a programming contest](http://www.engineyard.com/blog/2009/programming-contest-win-iphone-3gs-2k-cloud-credit/) that was (presumably) to promote their services and generally create PR. First and second prize included.... new iPhones! (Actually, Dorian pointed the contest out to me - thanks!)

Now, I've only tried one programming contest, and it was An _Epic_ Fail. **EPIC**.

Ahem. Traumatic memories.

Anyway, this time the coding problem was based around the [SHA-1 hash algorithm](http://en.wikipedia.org/wiki/SHA-1), trying to find a close match to one posted by Engine Yard. What I know about hash algorithms is pretty basic, but we have a couple of friends who do _lots_ of code & crypto, namely [Dan Bernstein](http://cr.yp.to/djb.html) and [Tanja Lange](http://www.hyperelliptic.org/tanja/). I figured that if anyone had code laying about, it'd be them and that was in fact the case. I also guessed that [CUDA](http://fnord.phfactor.net/2008/10/28/cuda-on-the-macbook-aluminum/) would be the weapon of choice for this sort of pleasingly-parallel application; that also turned out to be correct. I fired off an email and promptly forgot about it in the rush to get ready to travel.

Luckily, Dan and Tanja had time, were interested, had compute resources and (most importantly to me) didn't want an iPhone. Win!

(Insert scramble to find computers, of which I only got two and they got over 100)

Dan rolled out some [seriously awesome code](http://cr.yp.to/nearsha.html), starting with the OpenSSL SHA-1 codebase. His core2 tweaked version started at 2725 CPU cycles per hash, but by version 8 was down to 201 - a nice factor of 10+ speedup, and fast enough to do 10 million+ keys/second even on my laptop. It wasn't parallel, so we just ran one version per CPU, which worked quite well.

As if that wasn't enough, he wrote his first CUDA program and got it down to 35 cycles/hash, meaning that it really screamed. He and Tanja contacted a couple of their Taiwanese collaborators, who had GPUs to run the CUDA code, and we were off to the races. (They wanted the 2,000$ in cloud computing credits if we won, which was of no interest to me, Dan or Tanja - a perfect collaboration.) At peak, we were cranking over 3 billion keys per second, which was a tremendous advantage in a contest reliant on searching an enormous keyspace. You can see all the people, machines, rates and details on t[he page Tanja wrote for the contest](http://www.win.tue.nl/cccc/sha-1-challenge.html).

It was a blast. We used Skype to text-chat during the contest, subversion for the code and that was all we needed. "We" is a bit strong, since I mainly cheerlead as far as code. (Dan doesn't believe in comments, it would seem!) One odd thing was that the GPU version of the code gave my MacBook fits:



	
  * I had to compile it as 32 and not 64 bit, or I'd get compile errors in the C++ 'new' header file. That was a head scratcher.

	
  * You have to add -msse2 the compiler to get the cpucycles.c to compile

	
  * As before, you need [the DYLD fix](http://fnord.phfactor.net/2008/10/28/cuda-on-the-macbook-aluminum/).

	
  * With gcc-4.0 and 4.2, running the binary would freeze the laptop. 100% repeatable, required a poweroff. Mouse still worked, but that's it. The same code worked on the Linux boxes in Taiwan, so I'm stumped here. [Other people](http://forums.nvidia.com/index.php?showtopic=102349) had GPU code running on OSX, so it may be something in my configuration or the code.




[And we won](http://www.engineyard.com/blog/2009/programming-contest-and-the-winners-are/)! At the last minute we got lucky, and a [Tesla GPU](http://www.nvidia.com/page/hpc.html) in Taiwan found the winning key. We won by a single bit, but the odds of that were pretty low so it was actually a decent margin.




Of the two Macintoshes I brought in, the laptop (ebauche) found a 34, and the 8-CPU MacPro found a 33.




Technically, the main insight for speed was to pick words that totaled to 64 bytes in length, compute that hash and then feed that into a search of the 5-character keyspace. SHA-1 does blocks of 64 bytes, so this is twice as fast as computing the whole thing every time.




On the coincidence front, the GPUs exercised were quite possibly using some of my brother John's code, as he does kernel driver development for nVidia. I only thought of this afterward, but it's kinda cool. It's a small world sometimes.




I've not talked to Engine Yard yet about the phone, and dunno how I'll deal with service since we're still on T-Mobile, but I'm still thrilled and can't wait to get it. With any luck they'll be willing to pay for the unlocked version...




Friends are wonderful. Dan and Tanja - thanks for a great deal of fun, for letting me claim the prize that was yours for the taking, and for teaching me lots of fast SHA-1 tricks in a very short period of time!

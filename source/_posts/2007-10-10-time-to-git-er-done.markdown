---
date: '2007-10-10 15:05:05'
layout: post
comments: true
slug: time-to-git-er-done
status: publish
title: Time to git 'er done?
wordpress_id: '496'
categories:
- Code
- Essays - other people
- Geek stuff
---

Source Code Management, or SCM, is a topic beloved by nerds and misunderstood (or ignored) by everyone else. Since we live and breathe the stuff, that kinda makes sense.

Me, I started with [CVS](http://en.wikipedia.org/wiki/Concurrent_Versions_System) at Fermilab, used it again at Argonne, and am now on [Subversion](http://subversion.tigris.org/) at SDSC. I argued for [Perforce](http://www.perforce.com/), a commercial system that's [free for open-source](http://www.perforce.com/perforce/price.html), but the other developers hated it due mainly to a different conceptual model. (They were too used to how CVS works, I think)

Lately, I've been looking at the topic again since we may need to migrate repositories. The current best seems to be [Git](http://git.or.cz/), a project Linus started after the [BitKeeper](http://www.bitkeeper.com/) fallout. Git is fully distributed and quite fast, and (finally!) seems to have killer merge support.

Since we humans are narrative-based, a personal anecdote: When I was at Argonne, the [Globus](http://www.globus.org/) group used CVS, with developers scattered around the world. Because CVS merge is horrible, they'd plan a 'merge day' where all the developers were locked into a room with a projector, just to do a merge.

No one enjoyed this. Needless to say, I try to avoid such pain in SCM myself. One of the reasons I converged on Perforce was its killer merge support. Subversion, while much better implemented than CVS, started out with the same merge algorithms and really hasn't progressed much IMHO. If you want to do lightweight branches and allow developers to try risky (i.e. innovative) ideas, you **need** easy merging! From the [Shuttleworth post](http://www.markshuttleworth.com/archives/126):


> The “time to branch” is far less important than the “time to merge”. Why? Because merging is the act of collaboration - it’s when one developer sets down to integrate someone else’s work with their own. We must keep the cost of merging as low as possible if we want to encourage people to collaborate as much as possible. If a merge is awkward, or slow, or results in lots of conflicts, or breaks when people have renamed files and directories, then I’m likely to avoid merging early and merging often. And that just makes it even harder to merge later.

The beauty of distributed version control comes in the form of spontaneous team formation, as people with a common interest in a bug or feature start to work on it, bouncing that work between them by publishing branches and merging from one another. These teams form more easily when the cost of branching and merging is lowered, and taking this to the extreme suggests that it’s very worthwhile investing in the merge experience for developers.


Anyway, the other day I found a [nice essay](http://www.betaversion.org/~stefano/linotype/news/106/) on  Stefano's site about Git, complete with a link to a (typically incendiary) [talk by Linus](http://www.youtube.com/watch?v=4XpnKHJAok8). He's quite persuasive, and it _does_ look cool. Time to play!

Links:



	
  * Git for Subversion users: [http://git.or.cz/course/svn.html](http://git.or.cz/course/svn.html)

	
  * Linus, long email about Git to KDE project: [http://lwn.net/Articles/246381/](http://lwn.net/Articles/246381/)

	
  * Shuttleworth on 'merging is key': [http://www.markshuttleworth.com/archives/126](http://www.markshuttleworth.com/archives/126)

	
  * For amusement, Linus' flame on C++ vs C, for Git itself: [http://thread.gmane.org/gmane.comp.version-control.git/57643/focus=57918](http://www.phfactor.net/wp/wp-admin/*%20%20http://thread.gmane.org/gmane.comp.version-control.git/57643/focus=57918)


**Update** The title is for [ghort](http://ghort.livejournal.com/), who introduced me to the phrase. His context lacked SCM, but wordplay is fair game as far as I'm concerned.

**Update** 10/12: A reader suggests I consider [Accurev](http://www.accurev.com/accurev.html?link_id=1) as well, commercial. See comments.

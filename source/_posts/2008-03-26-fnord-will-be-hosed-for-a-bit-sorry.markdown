---
date: '2008-03-26 10:22:10'
layout: post
slug: fnord-will-be-hosed-for-a-bit-sorry
status: publish
title: Fnord will be hosed for a bit. Sorry.
wordpress_id: '630'
categories:
- Geek stuff
- News
---

I'm working on moving the blog from [www.phfactor.net/wp/](http://www.phfactor.net/wp/) to the more-obvious [fnord.phfactor.net](http://fnord.phfactor.net/). Not as simple as you'd think, since the wordpress install is file-shared dual-config with annalog, there's apache2 virtualhosts in there too, and of course the Debianized wordpress config auto-loader, everydns caches, 301 autoredirects, mysql, oh my...Anyway, partially complete, I have to figure out how to craft a regex redirect rule for apache so all the old links to /wp go to fnord.... expect some errors for a bit. 



Update: VHost up, redirect almost perfect, only fails for /index.html...  



Update 2: index.html fixed, too. I hope. Move should be complete! 

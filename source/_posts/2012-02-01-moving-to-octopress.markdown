---
layout: post
comments: true
title: "Moving to Octopress"
date: 2012-02-01 12:24
comments: true
categories: [news, WordPress, Octopress, Reviews and recommendations]
---

### TL;DR

Fnord is now running on [Octopress](http://octopress.org/). Should be faster and more stable. Enjoy.

### Why Octopress?

When I started Fnord back in 2005, WordPress was the hot ticket. Well supported, lots of add-ons and themes, and most importantly a Debian package. Since then, the ongoing upkeep has been a bit of a hassle, I've [gotten hacked once](http://fnord.phfactor.net/2007/08/25/fnord-updates-downtime-themes/) and also just have the itch to try something else. The PHP in WordPress has too many fiddly bits, and these days something as simple as a free WordPress theme can get you hacked. 

It's time to move on.

My first impulse was to move to [Confluence](http://www.atlassian.com/software/confluence/). I use that for [WatchOtaku](http://watchotaku.com), where the combination of blog+wiki is perfect. I [created a project](https://github.com/phubbard/wp2confluence) and did some hacking, but the HTML parsing had too many edge cases. I should have used [BeautifulSoup](http://www.crummy.com/software/BeautifulSoup/) or similar instead of trying to parse it myself; lesson learned.

Sometime later I read several posts about the advantages of a static site: they are super efficient to serve, fast under load and much harder to hack. I spent some time trying to make [Rui Carmo's](http://the.taoofmac.com/space/HomePage) code work, but that was a pain and the docs were poor.

Then I read [this post by Matt Gemmell](http://mattgemmell.com/2011/09/12/blogging-with-octopress/) and its link to the key missing piece, [exitwp](https://github.com/thomasf/exitwp). Boom!

So I went with [Octopress](http://octopress.org/). Killer support for mobile and such, designed for programmers, plugins, nice fonts, twitter and github integration, etc, etc. I'm having fun, and the results look good so far.

Most importantly, Octopress is *fun*. I blog because I want to, and having a platform that encourages that is a major plus. 

### Why Not Octopress?

There are some drawbacks. It's definitely harder to get working, oriented as it is towards software developers. Ruby, git, Markdown, rsync, Apache config; all pretty geeky. On the flip side, that niche appeal should make it less attractive towards spammers.

No nifty iOS app for blogging. That I will miss.

MarsEdit works [with a bit of effort](https://github.com/danimal/octomars).

### Comments, Categories and email subscriptions: missing features

1. One key feature I want was the dropdown list of categories. I'm trying to figure out how to replicate that here.
2. As for comments, to be honest I get about 1 real comment per month here, and several per day of varying spam. So I have no comments in place, and am not sure if I want them at all.
3. I have a few folks subscribed via email, using a wordpress plugin. I'll see what I can do there.
4. I need to decide on stats & analytics and perhaps add Mint to the header. Or getclicky; I like that too. 

### A Note For Others
As noted on [this page](https://github.com/imathis/octopress/issues/144), you need set a couple of environment variables before running rake to generate the site:
```
export LC_CTYPE=en_US.UTF-8
export LANG=en_US.UTF-8
```

Otherwise you get errors like this:
```
## Generating Site with Jekyll
unchanged sass/screen.scss
Configuration from /Users/hubbard/build/octopress/_config.yml
Building site: source -> public
/Users/hubbard/.rvm/gems/ruby-1.9.2-p290/gems/jekyll-0.11.0/lib/jekyll/convertible.rb:29:in `read_yaml': invalid byte sequence in US-ASCII (ArgumentError)
```

Overall, Octopress is a huge win. Strongly recommended, and I plan to move the other blogs here over as time permits.

As part of the move, the entire site, with configuration and posts, [is public on github](git@github.com:phubbard/fnord.git). I hesitated a long time over this, but really? The site is public, the config holds no secrets, and it might help someone else get going. Enjoy!
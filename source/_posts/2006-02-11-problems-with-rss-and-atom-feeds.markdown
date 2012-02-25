---
date: '2006-02-11 18:48:38'
layout: post
comments: true
slug: problems-with-rss-and-atom-feeds
status: publish
title: Problems with RSS and Atom feeds
wordpress_id: '58'
categories:
- News
---

Oops. I switched to a better URL layout and it borked all the feeds. I didn't notice because my subscription was using the old feed URL, which still worked...

[This is a known bug](http://wordpress.org/support/topic/54340) with a fix. I've downloaded the patch and will try to get it applied.

Oops. Turns out that you also have to let .htaccess do its thing by putting something like

    
    
      AllowOverride all
    


in httpd.conf.

Hopefully all better!

Kudos to [my friend Tom Stidham](http://www.thestidhams.com/tom/wp/) for finding this and letting me know.

---
date: '2011-02-21 17:20:49'
layout: post
comments: true
slug: man-i-love-python-sometimes
status: publish
title: Man, I love Python sometimes
wordpress_id: '1388'
categories:
- Code
---

Open a file, handle any errors, read it in by lines, strip any leading or trailing whitespace, put the result into an array:

	with open(price_filename) as f:
   		 prices_strs = [x.strip() for x in f.readlines()]

That's it. Damned concise, runs fast, easy to read once you learn the idioms. (List comprehensions, [with statement](http://effbot.org/zone/python-with-statement.htm).)

[I'm a fan](http://python.org/).

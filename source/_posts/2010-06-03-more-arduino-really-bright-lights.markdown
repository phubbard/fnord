---
date: '2010-06-03 13:38:34'
layout: post
slug: more-arduino-really-bright-lights
status: publish
title: More Arduino - really bright lights
wordpress_id: '1264'
categories:
- Arduino
---

After reading about using an [Arduino and a traffic light](http://www.urbanhonking.com/ideasfordozens/2010/05/the_github_stoplight.html), I was inspired to do a smaller-and-cheaper version at work for [our Buildbot setup](http://ooici.net:8010/).

**Lights**: 10,000 mcd LEDs from Sparkfun in [blue](http://www.sparkfun.com/commerce/product_info.php?products_id=8860), [green](http://www.sparkfun.com/commerce/product_info.php?products_id=8861) and [red](http://www.sparkfun.com/commerce/product_info.php?products_id=8862). $1.50 each, get two of each in case I toast a few. (I also bought a [BlinkM RGB light](http://www.sparkfun.com/commerce/product_info.php?products_id=8579), which at 8,000 mcd is almost as bright and easier to drive.)

**Driver circuit**: The LEDs are 80mA, 3.0V drop so I needed a current amplifier. It's been a while, and my EE was nearly gone, but [this excellent post](http://sqlskills.com/blogs/paulselec/post/Arduino-figuring-out-transistors-and-associated-resistors.aspx) walked me through the design. Simple emitter-follower circuit based on the PN2222 transistor does the job nicely:

[![Screen shot 2010-06-03 at 2.31.11 PM](http://fnord.phfactor.net/wp-content/uploads/2010/06/Screen-shot-2010-06-03-at-2.31.11-PM.png)](http://fnord.phfactor.net/wp-content/uploads/2010/06/Screen-shot-2010-06-03-at-2.31.11-PM.png)

Assuming a beta of 100, the base resistor works out to 4.7k, and the current limiter to 25 ohms. (I used 33 as being the closest).

Three circuits in a row on the breadboard, driven by digital I/O pins 6-8:

[![IMG_0076](http://fnord.phfactor.net/wp-content/uploads/2010/06/IMG_0076-450x600.jpg)](http://fnord.phfactor.net/wp-content/uploads/2010/06/IMG_0076.jpg)

Yep, it works! The LEDs, slightly current-limited by the USB power, are still too bright to look at directly. Quite noticeable.

Next up, the [ethernet shield](http://www.sparkfun.com/commerce/product_info.php?products_id=9026) is on order, and I have [Python code to poll the buildbot](http://pythonwise.blogspot.com/2010/02/publish-buildbot-builds-to-twitter.html) for last-build-status. Fun stuff!

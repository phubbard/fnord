---
layout: post
title: "Ham radio and the Baofeng UV5RA"
date: 2013-03-02 18:29
comments: true
categories: hamradio reviews
---

The [ham radio category here](http://fnord.phfactor.net/category/ham-radio/) has been pretty bleak, mostly because I got my Technician license in a weekend and haven't had a need that'd get me to buy a radio. [This post on Hack A Day](http://hackaday.com/2013/02/28/hacking-a-ham-radio/) changed that. Let's talk.

The [Baofeng UV 5RA](http://www.amazon.com/gp/product/B009MAKWC0/ref=oh_details_o00_s00_i00?ie=UTF8&psc=1) (Amazon link, non-affiliate) is between 40 and 50 bucks online. That gets you a handheld with plenty of functions and extras like desk charger, earpiece, belt clip, strap and such. It's dual band, 136-174Mhz and 400-480, *plus* FM receiver (e.g. bog-standard FM radio, receive-only). And it has a 0.5W LED flashlight. And you can hack it.

In other words, its the perfect and cheap way to try ham radio if you, like me, have that shiny new license in your pocket and a wife intolerant of expensive new hobbies.

Some notes and links to help others:

* [Amazon is a good place](http://www.amazon.com/Two-Way-Professional-Transceiver-Frequency-Protable/dp/B008IYCQSO/ref=cm_cr_pr_product_top) to buy it, but there are plenty of others.
* You want and need [the USB cable](http://www.amazon.com/gp/product/B008RZJHJU/ref=oh_details_o00_s00_i01?ie=UTF8&psc=1), which is an extra nine bucks.
* The USB cable is actually a USB-to-serial cable with a Kenwood-style end. The USB chip is my least favorite, the Prolific PL-2303. For OSX, [go here for the driver you'll need to install before it'll work.](http://changux.co/osx-installer-to-pl2303-serial-usb-on-osx-lio)
* The open-source software you should *immediately* get and install is called [Chirp](http://chirp.danplanet.com/projects/chirp/wiki/Home). More on this below.
* Start reading on [the Baofeng UV5R FAQ](http://miklor-uv5r.99k.org/UV5R-FAQ.html)
* The FM radio is accessed by pressing the 'call' button briefly. 
* The flashlight, via the 'Moni' button.
* Tons of information at [http://miklor-uv5r.99k.org](http://miklor-uv5r.99k.org)
* ARRL has a nice one-page color PDF of [ham radio bands](http://www.arrl.org/files/file/Hambands_color.pdf). The radio can do the 2 meter and 70cm bands.
* I've not tried this yet, but it can recieve NOAA weather broadcasts as well. 
* Haven't tried this either, but the Chirp radio unlocks additional functionality. Out of the box, the radio does 420-480Mhz; with Chirp it now goes to 520Mhz.
* The radio can handle [FRS/GMRS](https://en.wikipedia.org/wiki/General_Mobile_Radio_Service) but *is not legal* on those bands. Design and power limits. Update: Stuart Bain corrects me to note that GMRS is legal once you get the additional FCC permit for it. FRS is not, as it requires non-removable antennas.
* It gets [pretty good reviews](http://www.eham.net/reviews/detail/10349) and [the Amazon reviews](http://www.amazon.com/Two-Way-Professional-Transceiver-Frequency-Protable/product-reviews/B008IYCQSO/ref=cm_cr_dp_see_all_btm?ie=UTF8&showViewpoints=1&sortBy=bySubmissionDateDescending) are very positive.
*  The in-box manual is just a brochure. Head to [http://radiodoc.github.com](http://radiodoc.github.com) for a vastly better one.
* It has a basic scanner, and from an hour of listening 447.64Mhz seems to be a repeater with lots of folks talking. Coincidentally, I heard a conversation about this very radio; a negative review from a long-term ham.
* One strong plus of Chirp - you can go the menus, tell it where you are and it'll pre-program the channel memories with all of the local repeaters automatically. HUGE WIN.

Overall? Strong recommend. Cheap and capable.
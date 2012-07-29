---
layout: post
title: "Trying the Galaxy Nexus and NFC"
date: 2012-07-18 10:50
comments: true
categories: Google GalaxyNexus NFC Reviews
---

So I got to go to [Google's I/O conference](https://developers.google.com/events/io/) and the hardware haul was ludicrous:

* [Galaxy Nexus GSM phone](https://play.google.com/store/devices/details?id=galaxy_nexus_hspa&feature=device-featured#?t=W251bGwsMSwyLDIwMiwibnVsbC1mZWF0dXJlZF9kZXZpY2VzX1VTX18xX3Byb21vXzEzNDA1MTg5NjUwMzYiXQ..)
* [Nexus 7 tablet](https://play.google.com/store/devices/details?id=nexus_7_8gb&feature=device-featured#?t=W251bGwsMSwyLDIwMiwibnVsbC1mZWF0dXJlZF9kZXZpY2VzX1VTX18yX3Byb21vXzEzNDA1MTg5NjUwMzYiXQ..)
* [Nexus Q media streamer](https://play.google.com/store/devices/details?id=nexus_q&feature=device-featured#?t=W251bGwsMSwyLDIwMiwibnVsbC1mZWF0dXJlZF9kZXZpY2VzX1VTX18zX3Byb21vXzEzNDA1MTg5NjUwMzYiXQ..)
* [i5 Chromebox](http://www.google.com/intl/en/chrome/devices/chromebox.html)

I'm aware of the [irony of this](http://fnord.phfactor.net/2012/02/24/migrating-away-from-google/), but given that stack of Cool! New! Hardware! it was time to give it all a try, and donate some more of my usage data to Google to monetize.

## Google I/O
A quick take on the conference: huge (six thousand nerds, more than a few of which were just there to get and resell the hardware, from various conversations I had), very well run, amazing zeppelin/parachute demos, and packed every day with content. Worth going even if they weren't giving away stuff; the tech content is excellent. 

## The Galaxy Nexus phone
I've had an older Samsung 'Droid Charge' (running 2.2 and then 2.3) for some time now, and while it's a decent smartphone it was no competition for my iPhone 4 (CDMA). Good but not great.

The Galaxy Nexus (GN in brief) is the *first Android device I think is better than the iPhone 4.* Hardware and maybe even software. Google spent the time to even out the performance and laggyness that plagued the system, and the result is a delight to hold and use.

Note that I can't compare it to the current-model iPhone 4S, since I don't have one, so [caveat lector](http://www.merriam-webster.com/dictionary/caveat%20lector) on that score.

To try it out, I went with a [T-Mobile pay-as-you-go plan](http://prepaid-phones.t-mobile.com/pay-as-you-go-plans) that has $30 for a month, with 5GB of data, unlimited SMS and 100 voice minutes. Since the Nexus line is unlocked, there's no activation to deal with, just drop in the SIM and activate on T-Mobile's site. Service and speeds have been excellent here in San Diego so far.

### SIP service
I should note that the GN supports SIP service, meaning that if you run Asterisk or similar you can use it as a fully-enabled VoIP phone. I've done some testing and it works great, and this is a good solution for data-heavy plans like the T-Mobile one.
Very cool.

### NFC / RFID
One of the features I quite wanted to play with is the hardware support for [NFC](http://en.wikipedia.org/wiki/Near_field_communication). I went to a talk or two at the conference, and had some ideas for 'micro-location' uses:

* A tag on your desk to set a long display timeout, louder volume, auto screen brightness.
* A tag on the bedstand to mute the ringer, dim the screen and reduce display timeout
* Tags in the kitchen to set cooking timers
* Other work-related ideas I can't discuss here

A starter pack of 15 tags is about $15 [from Tagstand.com](http://www.tagstand.com/collections/nfc-kits/products/nfc-hobbyist-starter-kit-15-stickers) and is seriously cool. The NFC is distance-limited to 5cm by design; as they explained **this is a feature.** It lets you do stuff where you have greatly reduced fears of attacks, snooping replay and such. To keep the owner happy, tags are only active when the screen is on and unlocked, so you don't have to worry about taking random actions based on hidden or malicious tags.

To setup a tag, the free [NFC Task Launcher](https://play.google.com/store/apps/details?id=com.jwsoft.nfcactionlauncher&feature=search_result#?t=W251bGwsMSwxLDEsImNvbS5qd3NvZnQubmZjYWN0aW9ubGF1bmNoZXIiXQ..) is a simple app that lets you write, erase and keep track of your tags. Lots of possibilities here; I feel I've barely scratched the surface of what it can do. 

I should also note that the OS has significant support for NFC as of, I think, version 4.1. You can bring two NFC-equipped devices together and push/share content from one to the other - pictures, web pages, anything supported by the Android sharing APIs. Slick! Watching the demos, I had flashbacks to the Palm infra-red LED, which for a while was supercool for exchanging business cards. I wonder if adoption here will do better? Google claims they're activating a million NFC-equipped devices per week, so the hardware is disseminating rapidly at least.

Although I bitterly resent the price, I went ahead and bought [the desktop dock](https://play.google.com/store/devices/details/Desktop_Dock_with_Pogo_Pins?id=galaxy_nexus_hspa_pogo_desk_dock&feature=accessories#?t=W251bGwsMSwyLDExMSwiZGV2aWNlLWdhbGF4eV9uZXh1c19oc3BhX3BvZ29fZGVza19kb2NrIl0.). It uses 'pogo pins' instead of micro-USB, so it's easier to dock and remove the phone at least. This morning, I had an idea and stuck an NFC tag onto the dock itself:
![Dock with tag](http://fnord.phfactor.net/wp-content/uploads/2012/07/18/dock.jpg)

This I like. Drop it in and boom, actions triggered based on location. 

### Overall review
After a couple of weeks of use, I'm still happy with it. I've found native apps for most of my daily use (Twitter, Instapaper, iTunes Remote, 1Password, news, email) as well as the specialized ones like TripIt, Realtor.com and such. The new Chrome browser is good, and it's sync-between-devices is brilliant. 

Side note - I have been increasingly giving out my Google Voice number to co-workers and businesses, and one of the plusses of doing so is that it's easy to add a new called device. A nice abstraction layer for 'which phone am I using today?' I've also forwared the number from my iPhone to the GN, since we have more minutes than we ever use on our plan anyway.

Battery life is good enough, if a bit less than the iPhone. More likely to get warm in use, and less likely to go the entire day without a charge. Since it has a removable battery, less of an issue. **Side note on batteries** - the NFC chip is *in the battery*, and I wonder about how that'll affect operation, or if the software can handle changes in chip ID and such. I don't have a second one, so leave a comment if you know. The cynical side of me guesses they did this to make it hard to create third-party batteries.

The screen is fantastic - 1280x800, sharp and bright and delightful. Good for ebooks in Instapaper, Kindle app, etc.
### Google Play
To get music onto the phone, I am using the [Google Music Manager](http://support.google.com/googleplay/bin/answer.py?hl=en&answer=1229970) . It's syncing my iTunes collection into Google's cloud, all eleven thousand tracks. That saturated my DSL uplink for almost three days! About 150 tracks didn't upload, format and metadata errors that iTunes smooths over. Playback from the cloud works but it sometimes glitched. 

### Missing functions
I miss iMessage. Those don't forward, so you have to airplane-mode the iPhone to keep from accumulating unread messages.

I also greatly miss [Reeder](http://reederapp.com/). I'm running [Fever](http://feedafever.com/) on my Debian server, and there's currently no native Android client. The web interface sorta-mostly-kinda works, but has a few resizing quirks that are a pain in the ass on mobile. I keep having the urge to write my own, as the Fever API is public, but here time is a limiting factor.

### Bottom line on the Galaxy Nexus
It's a great device. Apple has competition, finally. Even if I switch back, I'll keep this one for the next time I travel.

## Nexus Q
WTF? It's flaky. I already have an amp, so it's hard to even try it. The control app usually refuses to control the device it just added. This one was released too soon; I'll wait for software updates.

## Nexus 7
The real deal. Just fantastic, smooth and fast and the right size for carrying, holding and travel. I hate the sleep/wake buttons' location, and miss the iPad home button, but other than that it's a home run, especially for the price. Buy one.

## Chromebox
I tried this out, but really I have no need for a 2012-era X terminal. It'd be perfect for tech-phobic elders, since it's secure as hell and zero-maintenance. So I did some RTFM, flipped the developer switch and [installed Ubuntu](http://www.extremetech.com/computing/132300-unleash-your-chromebox-how-to-dual-boot-ubuntu-linux-on-your-chrome-os-device/2). Slick! A nice fast compute server for now, and I like that I can be back to dead-stock with the flip of the switch. Right now I'm using to try out [PiCloud](https://www.picloud.com/) and the new [iPython notebook](http://ipython.org/ipython-doc/dev/interactive/htmlnotebook.html). Super fast little machine (16GB SSD, leaves about 5GB with a full Ubuntu install), quiet, small and low power too.


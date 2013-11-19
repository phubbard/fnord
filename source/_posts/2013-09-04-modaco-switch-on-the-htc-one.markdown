---
layout: post
title: "Modaco Switch on the HTC One"
date: 2013-09-04 11:31
comments: true
categories: android roms smartphones hacking modaco htc twrp
---

![HTC One product image](https://www.phfactor.net/fnord-images/2013/09/htc-one-unlocked_xl.jpg)

So I bought the [developer edition HTC One](http://shopamerica.htc.com/cell-phones/productdetail.htm?prId=41599) Android phone a while ago, thought I should share some of what I've learned. The [AnandTech review](http://www.anandtech.com/show/6747/htc-one-review/3) was the tipping point; nice review of an amazing phone.

Before you buy one, though, [read this first](http://www.pcmag.com/article2/0,2817,2416536,00.asp):
	Here's the problem: the Developer Edition has HSPA/WCDMA 850/1900/2100 and LTE  700/850/AWS/1900. If you don't know what that means but you're still cheering for unlocked phones, you need to get educated fast, because this is the problem with unlocked phones in the U.S.
	This phone will only work properly on AT&T.
	On T-Mobile, it will get 3G in some cities, but not in others; it'll be stuck on 2G in many places. It might get LTE in the future, but we're not sure. Ditto for Simple Mobile, Ready SIM, Straight Talk, and any other carrier that uses T-Mobile's network.

## Super Short Review
Great phone. Good battery, excellent camera, excellent display, no regrets after three months. I tried T-Mobile prepaid, Solavei, now using [net10](http://www.net10wireless.com/#/plans/pay-as-you-go) prepaid plan at appx $50/month. Net10 is an AT&T MVNO, so coverage is decent, not as good as Verizon. I **do not have LTE**, just HSPA and HSPA+; that suffices for me. 

Unlike my Samsung Galaxy S3, audio quality on the HTC is excellent; as good as my iPhones and/or iPods. This has been a big annoyance for me, the S3 is a decent device but music sounds much worse, so even with Beats disabled the HTC sounds excellent on speakers or line-out. WIN.

Overall: Recommended.

The AT&T version is an alternative; they also have the 64G version and *do* have LTE. It's locked, though.
	
## Unlocked bootloader
One of the big appeals for me was the combination of great hardware with no-hacks-required reprogramming. I've less time, so a phone ready to hack was worth extra. (64GB was also a big selling point, as I like to carry lots of music with me when I travel.)

So what can you *do* with said bootloader? Replace the entire operating system!

I've taken my time in doing so. HTC has some custom apps I'd hate to lose - the improved audio ('Beats', as far as I can tell a custom DSP filter) and the camera app. The camera on this thing is excellent, especially for the indoor uses that predominate for me. So I was, and am, in no hurry.

There are multiple ROMs that will work on this - see [this page](http://forum.xda-developers.com/forumdisplay.php?f=2115) for a listing, and be prepared to spend a few hours reading. The tradeoffs are complex, and the ROMs updated frequently. [HTC has a nice page](http://www.readability.com/read?url=http%3A//www.htcdev.com/bootloader/rom_flashing_guide) with a dictionary of terms and procedures that's also well worth reading.

The stock Android version of the hardware, ["Google Experience"](https://play.google.com/store/devices/details?id=htc_one), came out after I'd bought, or I might have bought that instead. Ahh well. If you just want stock Android, that's where I'd start.

### Ground rules and choices - root and S-OFF
I decided on [MoDaCo Switch](http://www.modaco.com/topic/363797-beta-12-modacoswitch-htc-one-support-topic/), an insanely clever ROM that allows the best of both worlds: You can toggle between stock Android and the HTC version. It self-updates over the air ("OTA updates") as well.

As a long-time Unix geek, I was very cautious of anything requiring root or disabling device security. Mobile security is bad enough already, I don't want to add more risk than necessary. I'm also looking for reliability, since this is my primary phone.

Installing MoDaCo Switch requires another app, a ROM assistant. The best options seem to be [ClockworkMod](http://www.clockworkmod.com) and [TWRP](http://www.teamw.in/project/twrp2/164). I chose TWRP based on [the MoDaCo instructions](http://forum.xda-developers.com/forumdisplay.php?f=2115).

I've already got the [ADK](http://developer.android.com/sdk/index.html) installed for [Meltdown](https://play.google.com/store/apps/details?id=net.phfactor.meltdown), so I've got the various tools ready to go. ADB, fastboot and the like.

I did **not** mess with S-ON/S-OFF. This unlocks lower levels of the device/radio firmware, and since it's not required I see no reason to mess with it. Nor did I root the phone; same reasoning.

## The steps

1. Download SWITCH.Beta1.zip, SWITCH.Beta10.zip and SWITCH.S-ON.zip [from here](http://www.modaco.com/topic/363797-beta-12-modacoswitch-htc-one-support-topic/)
2. Download TWRP [from here](http://www.teamw.in/project/twrp2/164)
3. On the phone, install the TWRP manager [from google play](https://play.google.com/store/apps/details?id=com.jmz.soft.twrpmanager)
2. On the computer, run

	adb push SWITCH.Beta1.zip /sdcard/
	
	adb push SWITCH.Beta10.zip /sdcard/
	
	adb push SWITCH.S-ON.zip /sdcard/
	
3. Unplug the phone and power down
4. Hold volume-down and boot
5. Select Fastboot and press power to enable
6. Connect USB - display should change to 'FASTBOOT USB'
7. On the computer, run
	fastboot flash recovery openrecovery-twrp-2.6.1.0-m7.img
8. Unplug the phone, select Recovery and press power to boot into recovery	
9. The phone should boot into TWRP!
10. From TWRP, select and install the zipfiles, all menu driven.
11. Once the phone boots, you should have a new app, 'MoDaCo Switch' that will switch modes.
12. Profit!

## Current status
I just got this installed today, and the browser tab collection was large, so this is just a dump of tabs and some notes. Complex process, more than one way to do it, and maybe of use to someone else as well. I just did my first switch from HTC mode to Google mode, and hey! It worked. App data preserved, too, and MoDaCo did a self-update to beta 12, all working as I had hoped. I'll post again if needed.

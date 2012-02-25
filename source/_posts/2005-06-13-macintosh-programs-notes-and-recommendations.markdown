---
date: '2005-06-13 13:37:29'
layout: post
comments: true
slug: macintosh-programs-notes-and-recommendations
status: publish
title: Macintosh stuff - notes and recommendations
wordpress_id: '3'
categories:
- Macintosh
- Reviews and recommendations
---

#### Change history


	
* Written 10/2003

	
* Updated 11/2003 for Panther (10.3)

	
* Added SSH keychain 4/5/04, minor edits

	
* Added gCount, MailUnreadStatusBar, Snapz Pro, 7/15/04

	
* Added bag section 9/9/04

	
* Added OSX Planet, MenuCalendarClock 10/22/04

	
* Added Quicksilver 12/19/04

	
* Typos fixed, added Meteo 2/14/05

	
* Removed 10.2 stuff, some Tiger mentions 6/5/05

	
* Porting to wordpress, 6/13/05

	
* Added Aquamacs 11/8/05

	
* Added Broadband tuner 11/30/05

	
* Cleanup, split sections, removed dead links, etc 2/25/06

	
* Added Jumpcut and Delibar 2/27/06

	
* Added GPG tools, Parallels 8/7/06

	
* More on Bags, 8/15/06

	
* More on bags, 12/1/06

	
* Updated image urls - no more direct linking, my bad. 5/21/07.

	
* Updates for 10.5 - spaces, etc. 5/20/08

	
* Updates after discovering the page still gets read, 6/18/09. Removing all PowerPC and 10.3 references.

	
* Update 4/9/10: Adding GlimerBlocker, ClickToFlash, IRC/IM, a few other edits, trimmed some 10.4 stuff.

	
* Update 8/19/10: Add iFixit, Disk Inventory X

	
* Update 10/25/10: Add SmartSleep

![](http://www.phfactor.net/wp-pics/powerbookg4-al-15.gif)


## Introduction


As a Unix weenie, I've become quite enamored with [my Macintosh laptop.](http://sfgate.com/cgi-bin/article.cgi?f=/g/a/2003/10/01/notes100103.DTL&nl=fix) To the point of advocating them to friends and co-workers. This page is an unstructured attempt to list software I've found, and a few tips and tricks to make your life easier.

Enjoy, and please leave comments for myself and others. I try to keep the page updated, and if you leave a comment I'll get an email so do chime in!


## PC emulators for x86 Macs (Macbook, Pro)


[Parallels Workstation ($80)](http://www.parallels.com/en/products/workstation/mac/) is presently the first out of the gate. Seems to deliver around 80% of native performance with the exception of OpenGL. Still not as polished as VMWare or VirtualPC, but damned fast and workable. 2 week evaluation licenses available for the asking. [VMWare Fusion](http://www.vmware.com/mac) is also $80, and I prefer it to Parallels for superior USB support and the ability to use all of those free VMWare images available online. Handy, those.

A new entrant is the Sun-funded [VirtualBox](http://www.virtualbox.org/). You can't beat **free**! I use it as well; not as polished and a trifle slower, but pretty darn good for zero cost.

Any of the above work; I default to VMware for compatibility with the existing stock of downloadable premade machine images.


## Development tools




### You have to install Xcode off of the install DVD. It's the 'Optional installs' folder.




### For all OSX users


The [Fink project](http://fink.sourceforge.net/) is a **must-have**. Its a complete port of the GNU suite + Debian's package management tools. From their page:


> We modify Unix software so that it compiles and runs on Mac OS X("port" it) and make it available for download as a coherent distribution.


Marvelous. This gets you two key tools - apt and fink. With fink, you install from source and compile, a la the BSD ports method. With apt, you install precompiled binaries, like Debian.

For CVS assistance, check out [this page](http://www.macdevcenter.com/lpt/a/4143), which has links to several good GUI CVS tools. There are Fink packages for Subversion as well. Git is best downloaded from [here](http://git-scm.com/) as a binary installer; it installs into /usr/local/git for some reason.

There's also [Darwin Ports](http://darwinports.com/), which is the BSD porting system (Open, Free and NetBSD, I think). I've not used it, but many are fans.


## Web browsers


The defaults as of 10.4 is [Apple's Safari browser](http://www.apple.com/safari/), which is pretty decent. [Camino](http://www.caminobrowser.org/), which is mac-native but built around the [Firefox](http://www.mozilla.org/) engine, is also good. You can, of course, go get Firefox itself, particularly if you want Greasemonkey script support.

There's also the [Shiira](http://hmdt-web.net/shiira/en) project, which is based on the same WebKit engine as Safari, but has better cookie management and other tweaks. I like it a lot.

Another solid choice is the now-free [Opera.](http://opera.com/) It does an excellent emulation of IE, and is sometimes the only thing that will load a page for me.

As of Safari V4, I use it as my default and Firefox when I need specific tools like [Elasticfox](http://developer.amazonwebservices.com/connect/entry.jspa?externalID=609).

Newest is [Google Chrome](http://www.google.com/chrome), which is pretty darn cool.


## Ad and Flash blockers


The best ad blockers in my opinion are the ones implemented as HTTP proxies, as that works with any browser. These days, I strongly recommend [GlimmerBlocker](http://glimmerblocker.org/) (free, GPL, runs as a control panel.)

You also want [ClickToFlash](http://clicktoflash.com/). Yes, you do. Option-click to whitelist a site.

Now that Safari has plugins/extensions, I love the '[A cleaner YouTube](http://extensions.apple.com/#entertainment)' plugin; strips all the crap off of youtube pages.


## Bookmarking


Ever since the advent of [del.icio.us](http://del.icio.us/), people have been changing how and where they manage bookmarks. Local, del.icio.us, .mac, etc.

I encourage you to experiment. Try [Safarilicious](http://www.tuaw.com/2005/12/14/safarilicious/) to upload bookmarks from Safari to del.icio.us, then [Delibar](http://www.tuaw.com/2006/02/25/delibar-the-missing-link-of-social-bookmarking/) to make them convenient on the menubar. I have to admit that the [Firefox Delicious plugin](https://addons.mozilla.org/en-US/firefox/addon/3615), which maps them to a normal menu, is seven kinds of awesome.


## Mail, ftp, sftp, scp, rss


Outlook fans should look at [Microsoft Entourage](http://www.microsoft.com/mac/products/entouragex/entouragex.aspx?pid=entouragex) - it's free.

Personally, I quite like the Mail application; it works well for me with IMAPS and ASMTP.

For FTP, try [Cyberduck](http://icu.unizh.ch/~dkocher/cyberduck/),which is GPL and also handles sftp.

For scp/sftp only, [Fugu](http://rsug.itd.umich.edu/software/fugu/) is marvelous and also free. This is my preferred program, and highly recommended. By the way, the name 'fugu', comes from an elaborate joke based on sushi and cryptography, that is: Fugu is the part of the blowfish you can lick.

Yeah, there's at least 3 nerd jokes buried in there.

If you have heavier-duty sftp/ftp duties, [Transmit](http://www.panic.com/transmit/) is worth the 30 bucks. Nice queueing system, iMac support, dashboard widget, etc.

A recent entrant that won my money is [ExpanDrive](http://www.expandrive.com/mac), which uses the MacFUSE layer to provide transparent access to _any_ filesystem over SSH and S3. I use it daily and paid for it out of pocket. There's a free trial, too.

For RSS, I used to use the now-free [NetNewsWire](http://ranchero.com/netnewswire/). These days, since I have the [iPhone](http://fnord.phfactor.net/category/iphone/), I've switched over to [Google Reader](http://google.com/reader/), which has the advantage of being always-synced between desktop and phone. There's a brand new app called [Fever](http://feedafever.com/) that self-hosts and looks interesting, but for now I'll stick with Google.


## IRC and instant messaging


For IRC, the [Colloquy](http://colloquy.info/) client is most excellent. [Psi](http://psi-im.org/) is excellent for XMPP/Jabber.

For instant messenger, [Adium](http://adium.im/) is a good cross-system app, though it can't do audio or video chat. For that, the included [iChat](http://www.apple.com/macosx/what-is-macosx/ichat.html) is good, as are [Google Talk](http://www.google.com/talk/) and [Skype](http://www.skype.com/welcomeback/). [FaceTime](http://www.apple.com/mac/facetime/) is still beta but an interesting idea.


## Office Software


[Microsoft Office for Mac](http://www.microsoft.com/mac/) works quite well; make sure and get the patches. There's a free (time bombed) [test drive available](http://www.microsoft.com/mac/downloads.aspx?pid=testdrive).

There's also [OpenOffice as well](http://porting.openoffice.org/mac/ooo-osx_downloads.html), which is free and evolving rapidly.

These days I mostly use [iLife](http://www.apple.com/ilife/) and [iWork](http://www.apple.com/iwork/) for when I need a DOC file or spreadsheet. For documentation and simple formatting, I actually prefer writing HTML files - they have a lot of advantages and for most documents their formatting suffices. Try [Mozilla SeaMonkey](http://www.seamonkey-project.org/) for a good free WYSIWYG editor.

For Visio-type functionality, [OmniGraffle Pro](http://www.omnigroup.com/applications/omnigraffle/) is great. If you have a laptop, you may have a copy bundled with the machine in /Applications.

For presentation software, Apple's [Keynote](http://www.apple.com/keynote/) is both megaspiffy and reads and writes Powerpoint. I like it. O'Reilly has [ a flattering review of Keynote](http://www.macdevcenter.com/lpt/a/4185) as a total replacement for Powerpoint. Keynote is now part of [the iWork suite](http://www.apple.com/iwork/).

For screen captures, which I use quite a bit for generating documentation, OSX includes a program called 'Grab' that does a decent job. It outputs TIFFs, but you can use Folder Actions to auto-convert to JPG/PNG. Or you can do what I've done, and pay the money for [Snapz Pro](http://www.ambrosiasw.com/utilities/snapzprox/). It has a bunch of additional capabilites, like capturing movies of the desktop, audio, etc. Free trial available.


## Scheduling, Entourage integration, iCal(endar)


One common requirement when working with Windows machines is Outlook integration. This is partially possible with a bit of work. Outlook can export iCalendar-format .ics files, which are compatible with iCal and Mail. This is my solution right now, and seems to work OK.

If you're using iCal, check out [MenuCalendarClock.](http://www.objectpark.net/mcc.html) It replaces the time in the upper right, but you can have it display a calendar and (if you pay) your iCal schedule for the day! Wonderful, unobtrusive, works great.

For calendar sharing, I've spent many hours on this to very poor results, so I have to recommend MobileMe or Google Calendars. If you have Exchange server, that works too. No great solutions here, at least not for free.

**Analysis, Graphing, Math**

For time-series data, I am a long-time fan of the cross-platform [Kaleidagraph](http://www.synergy.com/). Excellent plots and analysis tools.

If you need it, [MATLAB](http://www.mathworks.com/products/matlab/) is available. Not cheap, but that's always been true.

The same applies to [Mathematica](http://www.wolfram.com/products/mathematica/), of course.

For freeware, [Octave](http://www.octave.org/) is a GNU workalike for MATLAB; there are others depending on your needs. The [R Project](http://www.r-project.org/) is another alternative is you need lots of statistics.


## Editors


A perennial favorite is called [BBEdit](http://www.barebones.com/products/bbedit/index.shtml)- very nice support for code (compilation, code highlighting, CVS), HTML, etc. They also have a simpler, free version called [TextWrangler.](http://www.barebones.com/products/textwrangler/index.shtml)

[ ](http://www.barebones.com/products/textwrangler/index.shtml)

I've paid for and like [TextMate](http://macromates.com/), it's quite code-friendly and expandable.

Emacs works in Terminal; if you

    
     setenv TERM dtterm


then syntax highlighting works as well.

There's also [Aquamacs](http://aquamacs.org/), which looks even better. I use it and quite like it.

More recent editors also include [Smultron (GPL!)](http://smultron.sourceforge.net/), [TextMate (commercial)](http://macromates.com/) and [JEdit (GPL, Java, cross-platform)](http://www.jedit.org/)

JEdit in particular seems to have quite the following, as of 2/06 there were over 80 plugins for it. Seems a bit easier to use than the full-bore-IDE of Eclipse.

For Python, IPython and [Komodo](http://www.activestate.com/komodo/) make a good combo, as does TextMate for simpler code.


### TeX and LaTeX


Once you've got Fink installed, you can install TeX and LaTex. A nice GUI shell for working with them is [TeXShop](http://www.uoregon.edu/%7Ekoch/texshop), which works a treat. Note that, for strange reasons, it uses pdftex, which is not quite the same as vanilla TeX as far as, say, EPS support.


## Menu bar applets


These live on the menu bar, always running and doing useful stuff.

Start off by getting [iStat Menus](http://www.islayer.com/apps/istatmenus/). It shows CPU, network, disk activity and more. Free, polished, donation-ware. (Version 2 is nag-ware, so I'm no longer using it.)

[MenuMeters](http://www.ragingmenace.com/software/menumeters/) is a GPL'd program to monitor memory, disk activity, network, swap and such. Also gives fast access to things like the Activity Monitor, network settings, net util, etc. Almost as good as iStat.

[SSH Keychain](http://www.sshkeychain.org/) is another GPL'd utility that I **highly** recommend. It handles your SSH key for you, can optionally revoke it on sleep/screensaver, integrates with Fugu, SSH tunnel manager, ssh, scp, sftp, CVS, etc. Wonderful stuff.

See above under 'Scheduling' for MenubarCalendarClock - recommended.

[Meteo](http://heat-meteo.sourceforge.net/) is a free, open-source applet that displays weather on the menubar. Simple, flexible, reliable. Quite nice, especially if you have a windowless office, or travel a lot.

One of the annoying things about the mac clipboard is that it only stores one entry. When I'm writing something up, its often useful to have several URLs available. Until now, I had experimented with the commercial [iPaste](http://www.iggsoftware.com/ipaste/index.html), but didn't like it enough to keep past the trial.

I just found a free replacement called [Jumpcut](http://www.snarkout.org/projects/jumpcut/) that is a must-download. It puts a small icon on the menubar, with a dropdown list of entries. Clicking moves that entry into the clipboard for use. That way, I can keep the last 20 or so things I copied or cut around... really handy. Another way to get this functionality is to run [LaunchBar](http://www.obdev.at/products/launchbar/), which has it as a side feature.


## Cool Random Stuff


When I had a Linux desktop at work, I used to have xplanet running as a backdrop, with hand-scripted alpha-blended cloud data from the UWisc Near-IR satellite. I was the nerd equivalent of a hipster. Now, of course, you can get the same effect, only more so and free, on OSX. Head on over to [this page and get OSXPlanet](http://otte.ucsc.edu/~gabriel/osxplanet.html), which is one of the coolest programs you'll see in a long time. Free, too.

Prepare to waste many hours if you've not tried [Google Earth](http://earth.google.com/). Be sure to try the flight simulator part!

There's an awesome Mac-only app called [StreamRipperX](http://streamripperx.sourceforge.net/) that takes an Internet radio station and writes MP3 files to disk from the content. Set it running, leave it overnight, and come back in the
morning to a bunch of nicely named and saved files. Mondo cool.

For wireless networks, [KisMAC](http://freshmeat.net/projects/kismac/?topic_id=861%2C43%2C152) does a great job and has the side benefit of not sending anything, ensuing that innocent searching does not bring down the wrath of the network BOFH.

[ProFont](http://www.tobias-jung.de/seekingprofont/) is a monospaced font for Mac, Windows and Unix designed for code. Wonderful stuff. It has a lot of little touches, such as distinguishable l/1, slashed zeros, clear punctuation, and others. Also excellent for terminal windows. There's also [AnonymousPro](http://www.ms-studio.com/FontSales/anonymouspro.html).

**Quicksilver**

One hard-to-classify app is a piece of freeware called [Quicksilver.](http://quicksilver.blacktree.com/) It's sort of a search program, that can do many other things. Launch programs, search your bookmarks, file management, all sorts of stuff. I used to be a hardcore fan, but the developer abandoned it and it's gotten less reliable as the OS evolved. These days I run [LaunchBar](http://www.obdev.at/products/launchbar/) instead; ahh well. Very similar in function and definitely more polished than QS was.

Battery and sleep - OSX is a bit annoying about sleep and hibernate, but [SmartSleep](http://www.jinx.de/SmartSleep.html) will solve the problem for you. Recommended.

Screensavers and eye candy

If you've got 3D onboard, the [ATI OpenGL demos and screensavers](http://www.ati.com/developer/demos/macss2/index.html) are awesome. And free.

The essential Matrix screensaver is called [Red Pill](http://meta.ath0.com/articles/2005/05/10/redpill-1-4-2). Free, very well done, open source.


## PGP/GPG, Mail plugins and utilities


[This page has plugins for Mail](http://www.tikouka.net/mailapp/), including stuff like Entourage imports, spamcop, mail count in the menubar,all sorts of amazing and useful stuff.

For GPG, I use the [MacGPG](http://macgpg.sourceforge.net/) distribution plus the [GPGMail plugin.](http://www.sente.ch/software/GPGMail/English.lproj/GPGMail.html) Works fabulously, though you need to set the 'By default, use OpenPGP/MIME' option for some clients to recognize and parse the emails. (Mutt + gpg, in particular.)

For figuring out where your disk space went, try the visual [Disk Inventory X](http://www.derlien.com/). Works great.


## Backups


Of course, as of 10.5 [Time Machine](http://www.apple.com/macosx/features/timemachine.html) is the hot ticket. Buy an external drive or [TimeCapsule](http://www.apple.com/timecapsule/) and be done with it. Highly recommended.

Another alternative is the free-but-must-register [Silverkeeper](http://www.silverkeeper.com/) from LaCie. Scheduled backups, free, GUI, OS9 and OSX support, looks pretty good, works well.

Many people swear by [Dantz Retrospect](http://www.dantz.com/en/products/index.dtml); I've not tried it.

Apple also has a [free graphical backup program](http://www.apple.com/downloads/macosx/apple/backup.html) that can write to firewire, CD/DVD, iDisk, and also has scheduling capability. However, if you don't have a .Mac membership, it's crippled to only writing to .Mac. Which kind of sucks.

If you have the Serious Mojo, you can [create your own dot-mac replacement](http://www.tnpi.biz/computing/mac/tips/idisk/idisk-v2.shtml) and use Apple Backup with it. I've not yet tried this, but its a nice hack.

For partial backups and true bidirectional sync, [Unison](http://www.cis.upenn.edu/~bcpierce/unison/) is pretty amazing. Cross-platform, free, fast, and hard as hell to configure. I spent the time, based on the recommendation of [a friend of mine](http://cr.yp.to/), and it's excellent. I sync my desktop, bookmarks, calendars, addressbook and some reference data folders twice a day with my desktop, and its enabled me to leave the laptop at home. Well worth the effort.


### Hardware


Sooner or later you'll want to replace/upgrade a hard drive, battery or such. Head to [iFixit](http://ifixit.com/) for a comprehensive set of visual do-it-yourself tutorials.

Books

O'Reilly has [many excellent books ](http://mac.oreilly.com/)you'll want; I am particularly fond of [Mac OS X for Unix Geeks.](http://www.oreilly.com/catalog/mosxgeeks/) [Mac OSX: The Missing Manual](http://www.oreilly.com/catalog/macosxmm/) is an excellent overall intro, with pointers to in-depth resources. A good place to start.


## Carrying cases


I've hesitated to add this section, as bags tend to be a religous topic for people. On the other hand, I'd like to advocate what I like.

I've had several bags over the past few years, starting with a basic attache-style laptop bag from Lands' End. It worked fine for my Thinkpad, but is a little too small to carry the 15" powerbook. Also, the padding is minimal. Other than that, a decent bag, nicely unobtrusive.

Next I went to a [Targus sport deluxe backpack.](http://www.targus.com/us/product_details.asp?sku=TSB315) It works pretty well for carrying lots of stuff, and excels at heavy loads. Things that annoyed me enough to switch:



	
  1. Dangling straps. Lots of them.

	
  2. Main fastener broke in short order, so the flap was held only by gravity.

	
  3. Main pack is split in two, so you can't carry large items.

	
  4. A bit large. Doesn't travel well, especially under airline seats.


After that, I got a nice leather briefcase in Brazil. Super-classy, good fit, decent padding. However, it just doesn't hold enough to be useful; I save it for occasions when I need to look good.


### Timbuktu!


![](http://www.phfactor.net/wp-pics/obssob.jpg)

I then bought a [Timbuk2 Commute bag](http://www.timbuk2.com/tb2/catalog/categories.t2?categoryId=7) at the Apple store downtown. I actually saw it one day, went home and researched it, and went back the next day to buy it. It rocks. It's by far the nicest and best-made bag I've ever had. Just enough volume, lots of pockets and niches, most excellent padding, waterproof to boot, and super comfortable. Highly recommended.

Update August 2006: According to the [Ars Technica review](http://arstechnica.com/reviews/hardware/macbookpro.ars/2), the MBP 15" won't _quite_ fit in the Commute bag. Damn.

Update Dec 2006: The Macbookpro fits quite well in the Timbuktu. I've now traveled twice with it, no problem, recommended.

Update Dec 2006:

[
![](http://www.phfactor.net/wp-pics/bbp1sm.jpg)
](http://www.kk.org/cooltools/archives/001494.php)

The [Bum Backpack Messenger bag](http://www.kk.org/cooltools/archives/001494.php) gets a strong recommend from Cool Tools. Haven't tried it personally, but looks good.


### ...and back to REI again


As of October 2004, my commute has changed - I now have a 30-minute walk to the bus stop, and the reverse coming home. Also, I'm now using [Unison](http://www.cis.upenn.edu/~bcpierce/unison/) to sync the powerbook with the desktop, so I don't need to pack the powerbook along. In this situation, the Timbuktu doesn't work very well, and I've gotten a nice [REI backpack](http://www.rei.com/online/store/ProductDisplay?storeId=8000&catalogId=40000008000&productId=47928395&parent_category_rn=4501697). No computer sleeve, but good for carrying everything else. Might try it on my next trip to SD West.

Update Aug 2006: The REI bag continues to work pretty well for the daily walking commute, but its a bit suboptimal for airlines. The Timbuktu is still preferred for that.

For a complete list of bags that will fit the powerbooks, please see [this page on MacNN.](http://forums.macnn.com/showthread.php?t=178702) This list has 'em all!


### ... and back to Timbuktu Yet Again!


Wow, soap opera, eh? What can I say, I'm picky. Current choice for the past year or so is[ this Timbuktu backpack](http://www.amazon.com/Timbuk2-Track-Laptop-Backpack-strap/dp/B000JZ4VZG/ref=sr_1_10?ie=UTF8&s=apparel&qid=1211321686&sr=1-10):

[![](http://fnord.phfactor.net/wp-content/uploads/2008/05/ttrack.jpg)](http://fnord.phfactor.net/wp-content/uploads/2008/05/ttrack.jpg)It's better for the long walks I have to and from the bus now, and has been excellent. Doesn't hold a lot, but that's just fine.


## External keyboards and mice


I love the [old-school IBM keyboards](http://www.dansdata.com/clickykeyboards.htm), despite the noise. You can now get the same thing for Mac with the [Matias TactilePro.](http://matias.ca/tactilepro/index.php) I've had one for several months and love it. Noisy, but who cares?

For mice, get whatever multibutton type suits. I like Logitech and MS more or less equally. At least two buttons, and scroll wheel is nice too.


## Other Notes for Unix people


A neat trick at the command line - use the

    
    open


command to simulate a double-click in the Finder. So you can 'open .' to get a new finder window of the current directory, or 'open *.doc' and so forth. Very useful.

Use

    
     alias ssh ssh -AXY


That forwards agent connections and X11, and fixes a broken-ness with X and SSH that otherwise shows up in programs like xdvi.


### **Other References**


[This page on Faisal](http://www.faisal.com/docs/osxforgeeks.html) is an excellent introduction to the Mac for Unix geeks. Worth a read.

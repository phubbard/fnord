---
date: '2008-02-17 20:48:01'
layout: post
comments: true
slug: with-fear-and-trembling-the-iphone-update-hack
status: publish
title: With fear and trembling... the iPhone update & hack
wordpress_id: '599'
categories:
- Cell phones
- iPhone
- Reviews and recommendations
---




![Adding NextSim to T-Mobile](http://www.phfactor.net/wp-pics/DSCF1987.jpg)



Roughly following the vendor-linked instructions [here](http://jailbreakme.com/1.1.2/)...



	
  1. Backup via iTunes

	
  2. Download various ipsw firmware fils from [here](http://iphone.unlock.no/#restore-firmware-files).

	
  3. Looks like I need to 'revirginize', or undo the unlock that I did before. Hmm.

	
    1. Tool [here ](http://code.google.com/p/iphone-elite/wiki/RevirginizingTool) from ipone dev elite, their [FAQ re-virginize link](http://code.google.com/p/iphone-elite/wiki/FAQ) is borked.

	
    2. Looks like [the latest iNdependance](http://code.google.com/p/independence/) can do some of this too... Let's try that first, it's the simplest. Trying the 'prepare for upgrade' option...




	
  4. Using iTunes, 'check for upgrade', upgrade to 1.1.3, seems to work.

	
  5. Using iNdependance, activate and jailbreak - OK, done.

	
  6. Install trick SIM chip, using scissors to cut SIM card and tape to attach it. No work, no network shown, no error message. Hmm.

	
  7. Try installing SSH/SCP/SFTP using iNdependance. Nope.

	
  8. Try iNdependance's SIM(software) unlock in desparation... Unlock succeeded, but with the 'next sim' in place the phone shows no network.

	
  9. Re-flash 1.1.3 using iTunes, try with and without SIM present, before and after restoring data...nope.

	
  10. Remove next sim, try old SIM card... same thing. Symptoms: IMEI 00 499901 064000 0, no signal on cell meter.


Time to RTFM, and[ according to this](http://code.google.com/p/independence/wiki/Beta14KnownIssues) TurboSim doesn't work with 1.1.3. Which means that my $20 'next sim' probably doesn't either. Damnation. The instructions claim 1.1.3 works, but a re-read of [the poorly written paragraph](http://www.pdacable.com/servlet/the-56/iphone-unlock-1.1.2-next/Detail) seems to imply only that 'works' means 'downgrade to 1.1.1 and unlock' that works:


> Safe unlock for OTB iphone 1.1.2 and 1.1.3. Just tested with 1.1.3 works great. Buy now and I will include free tech support, just call us. We will walk you through installation! Won't void apple warranty. Works with boatloader 4.6 and 3.9. Guaranteed or 100 percent refund! No programming knowledge required. 3Easy steps to unlock the iphone 1.Downgrade your firmware from 1.1.2 to 1.1.1, follow the link for the Tutorial 2.Jailbreak and activate, install ok to prep and iworld if needed. 3.Cut your sim as shown in picture. Stick sim and next sim together and put back in sim tray and into iphone. Now your ready to use your unlocked iphone!


Hmm. From reading[ this page](http://www.iphoneatlas.com/2008/02/13/an-even-easier-iphone-113-jailbreak-for-iphone-users/), maybe I should try [iJailbreak](http://code.google.com/p/ijailbreak/) instead. It WORKS!


![Unlocking the iPhone](http://www.phfactor.net/wp-pics/DSCF1989.jpg)



What's more, it installs the AppTapp installer for you; nice touch.

OK, verdict is this:



	
  1. Use iNdependance to 'prepare for upgrade', not sure if this is necessary

	
  2. Use iTunes to sync for a backup.

	
  3. Use iTunes to update to 1.1.3

	
  4. Use [iJailbreak](http://code.google.com/p/ijailbreak/) to activate and unlock.

	
  5. There is no step five.


That's it! And, what's more, the GPS-lite WORKS!

It took all damn day, but I'm a delighted nerd. Off to donate to iJailbreak!

(And yes, the 20 bucks for the 'next sim' hardware was a waste. Save your money.)

---
date: '2006-01-06 23:32:47'
layout: post
slug: hitachi-wifi-voip-up-and-running
status: publish
title: Hitachi WiFi VoIP up and running!
wordpress_id: '40'
categories:
- News
- Voice over IP
---




![](http://www.phfactor.net/wp-pics/hitachi-5000.jpg)



Finally got my cheap-from-ebay [Hitachi WirelessIP 5000](http://www.voip-info.org/wiki/index.php?page=Hitachi) phone working. Took a lot of doing:


	
* Hadda configure the wireless to B-only, which suxx.

	
* Asterisk config

	
* Much poking through a very odd set of phone menus, figured it out only after I googled the phone user and admin manuals.

	
* Had to [change broadvoice proxies](http://www.broadvoice.com/support_install_asterisk.html%22) to get the lag down from 165msec to 18.

Seems to have semi-poor wireless reception, worse than my not-great aluminum powerbook. Audio quality is still in progress, not sure I have it setup right. I'm getting a lot of these from Asterisk:

    
    
        -- Got SIP response 606 "Not Acceptable" back from 204.128.136.100


No help from google, surprisingly.

Since the manuals were hard to find, I'm mirroring them locally for anyone else who needs them:
[WIP-5000_WebInterface.pdf](http://www.phfactor.net/hitachi-voip/WIP-5000_WebInterface.pdf)

[WirelessIP5000_SE_Manual_jul.pdf](http://www.phfactor.net/hitachi-voip/WirelessIP5000_SE_Manual_jul.pdf)

[WirelessIP5000_Users_manual_jul.pdf
](http://www.phfactor.net/hitachi-voip/WirelessIP5000_Users_manual_jul.pdf)

We'll see how this goes. I really, really love the idea of unlimited phone calls for twenty bucks a month. In other words, email me if you want to talk and I'll send you the new VoIP number.

Update 11/23/06:

I still get 606 errors, but I have new firmware I need to try. The [wiki page on this phone](http://www.voip-info.org/wiki/view/Hitachi+WirelessIP5000) has some ideas, so maybe when I get home I'll try a firmware update. I'm also considering just selling it and switching to a Nokia N80, which has SIP/Asterisk support.

Update 12/20/06:

Sold it on Ebay and bought a Sipura 3012 FXS/FXO adapter. Too much hassle with the Hitachi.

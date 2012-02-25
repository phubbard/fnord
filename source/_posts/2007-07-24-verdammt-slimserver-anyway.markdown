---
date: '2007-07-24 12:10:07'
layout: post
comments: true
slug: verdammt-slimserver-anyway
status: publish
title: Verdammt slimserver anyway
wordpress_id: '402'
categories:
- Audio, sound and music
- Debian
- Networking
---

I've had a lot of people trying to use my wireless network of late 


> 
Sidebar: The Airport Extreme can send log messages to your Unix box via the syslog mechanism. Check out 'Base station options'/ 'Logging/NTP' and 'Send base station logging to'

I also set the LED light to blink for traffic, as I find that more useful than always-on.

See [this page](http://www.phfactor.net/wp/2006/01/15/syslog-net-wide-finally/) for syslog setup on Debian.



and I've been trying to close down the hatches. I've always used MAC filtering, so they couldn't get on, but someone keeps trying. Given the rapid repeat, its certainly automated or just OS stupidity, but it annoys me.

Plan of attack:


* Switch from B/G WiFi to G only.


* Enable encryption, WPA2 preferred.


* Disable SSID broadcast.


So. First problem is my version 1 [Squeezebox.](http://slimdevices.com/) 

![](http://www.phfactor.net/wp-pics/slim_devices_squeezebox.png)

It's [been trouble before](http://www.phfactor.net/wp/2006/01/26/more-squeezebox-hacking/), but I don't have the dosh to upgrade to the much-nicer v2 or v3. It's WiFi is B-only. Fortunately, I had a Linksys WRT54GS spare, and had [previously setup one as a bridge.](http://www.phfactor.net/wp/2005/12/11/client-mode-on-linksys-wrt54gs/) 

Since I wanted to put images in this post, here's a pic of one borrowed from [the Wikipedia page](http://en.wikipedia.org/wiki/WRT54G) on it:

![](http://www.phfactor.net/wp-pics/800px-linksys_wrt54g-wp.jpg)

I found a [slightly better set of instructions](http://forums.anandtech.com/messageview.aspx?catid=36&threadid=1513386&frmKeyword=&STARTPAGE=1&FTVAR_FORUMVIEWTMP=Linear) for bridge mode on AnandTech, and managed to get it working. I found that the newer Talisman firmware worked better than the Alchemy release.


> 
Sidenote on firmware and Sveasoft: I am a former subscriber to Sveasoft, and have paid for a year of access. This time, subscription having expired, I downloaded the 'Freeman' version from [this page instead](http://wrt54g.thermoman.de/), which lacks the ultra-stupid MAC-based copy protection. I am fairly certain that Sveasoft has bent or broken GPL on this, and FWIW the Freeman version is working well. Rant over.




After you do all the setup (subnet, DHCP, client-mode wireless) there's just one real gotcha - to get it to work, you have to enable ARP proxying on the Linksys. There's no way to do this from the web interface, and **the setting is erased if you reboot the router.** So you have to


* Enable SSH on the router.


* Upload your SSH key via the web interface.


* SSH in as root, and run

    
    
    echo 1 > /proc/sys/net/ipv4/conf/`route | grep default | awk '{print $NF}'`/proxy_arp 
    





Messy, eh?

Once I had that figured out, I wanted to enable encryption. [WEP](http://en.wikipedia.org/wiki/Wired_Equivalent_Privacy) is no good, so I wanted [WPA](http://en.wikipedia.org/wiki/Wi-Fi_Protected_Access) or [WPA2.](http://en.wikipedia.org/wiki/IEEE_802.11i) I'm using an [Airport Express](http://www.apple.com/airportexpress/) which supports all of the above as my base station. Gratuitous picture:


![](http://www.phfactor.net/wp-pics/airport-express.jpg)


However, the Freeman firmware pages use different terminology than the Apple admin program, so I had to google a bit. [This page](http://www.punknix.com/?q=node/62) and [this one](http://www.networkworld.com/net.worker/columnists/2005/0110shaw.html) got me going. You have to


* Select 'Wireless security'


* Select WPA2 personal.


* Select Encryption type as 'WPA only'


* Only now will 'WPA personal' show up as an option; choose it.


* Select 'Pre-shared key' above, and enter your 64 hex secret.


Now, while it reboots, go to the Freeman firmware and select 'WPA-TKIP'. Enter same key, reboot, do the SSH ARP voodoo above, and you're good to go.

(You also have to go around to all your laptops and enter the key into their setups, but that's much easier.)

Once I did this I hit the next problem: Slimserver is not working. I spent hours thinking it was the bridge setup, which was reasonable given the number of places you can make mistakes, but it isn't. For some reason, the current release in debian unstable is borked, and the symptom is that the web interface never loads. You can connect to the port ok but you get no content. I erased the contents of /var/cache/slimserver/MySQL and restarted it, but got the same result.

Oddly, the web interface was working while it rebuilt the database, but somewhere in that process it Just Stopped. No error log that I can find, no errors in /var/cache/slimserver/mysql-error-log.txt either. I'm at a loss.

The other problem that I have is probably my error - I can't load the Linksys web interface unless I'm cabled into it. I enabled the remote admin, but it may be subnet-related or such.

I **really** wish that the ARP proxy setup was a) permanent and b) web-interface-settable. Yeesh.

I also am a bit peeved at Slimserver. It's the program single most likely to break on a Debian dist-upgrade.

Ahh well, maybe with G-only and WPA it'll cut down on the neighbors trying to associate with my base station...

**Update 8/19/07:** Squeezebox got updated and appears to stay up now, so I'm reopening this one. Fixed the missing anandtech URL, sorry. I should also note that the WPA+G change **did** remove the slowdowns and associations -- hooray! Now tackling the ARP proxy and such. Post to follow!

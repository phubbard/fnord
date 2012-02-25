---
date: '2007-05-31 22:13:04'
layout: post
comments: true
slug: vpn-between-osx-and-linksys-rv042048
status: publish
title: VPN between OSX and Linksys RV042/048
wordpress_id: '337'
categories:
- Macintosh
- Networking
---

 
![](http://www.phfactor.net/wp-pics/linksysrv042.jpg)
 

I've been considering a different firewall router for the home network, and am looking at the [Linksys/Cisco RV042.](http://www.amazon.com/Linksys-RV042-100-4-Port-Router/dp/B0002I7288<br ></a>)

The unit ships with decent Windows software, but they're silent on the issue of Mac support. From [this excellent article](http://slowcruisin.wordpress.com/2007/01/17/vpn-using-mac-os-x-and-linksys-rv042/) come the instructions and three key tidbits:



	
  1. It won't work if your Mac is behind a NAT router.

	
  2. You configure the router under 'PPTP server' and **not **VPN server.

	
  3. Enter the username/password into 'Internet Connect' and you're good to go.


If you're lucky enough to have [OSX server](http://www.maclive.net/sid/132), a VPN server is built in. I'm not.

Hmm, looks like the RV042 is ~$170 as of 6/07. Not bad. It can do 5 PPTP connections at once, which'd be fine for me. It'd be nice to be able to print from offsite sometimes, and SSH tunnels are a PITA.

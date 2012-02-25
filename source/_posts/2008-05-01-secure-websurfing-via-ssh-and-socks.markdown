---
date: '2008-05-01 12:27:32'
layout: post
comments: true
slug: secure-websurfing-via-ssh-and-socks
status: publish
title: Secure websurfing via SSH and SOCKS
wordpress_id: '675'
categories:
- Geek stuff
- Macintosh
- Networking
- Politics
---

It's often handy to be able to surf from a monitored network. Perhaps you want to job-search Monster from work, view (cough) inappropriate comment on your lunch break, check your bank balance in a open-wifi coffeeshop, whatever. For it to really be secure, all parts of the channel must be encrypted, including the DNS lookups. Here's a free way to do it. (If you have the money, you can also run a VPN; this is a simpler way of building a private HTTP-only VPN.)




You need an SSH account on a server that you trust, and a copy of Firefox. That's it! An SSH agent such as SSHKeychain is nice for not having to re-enter passwords every time, but not required.




For this example, I'm going to use my server, usul.phfactor.net, so change accordingly for your setup.




There are two parts of this: The first part is to setup an encrypted connection, which has what's called [a SOCKS proxy.](http://en.wikipedia.org/wiki/SOCKS) This forwards your HTTP requests over the SSH connection to the remote server, which does the DNS query, HTTP fetch and returns the results to you via SSH. It turns out that SSH **itself** has a SOCKS proxy in it, you just have to enable it.





The second part is to tell your web browser to use the proxy, and how to find it.






Here's the first part:



    
    
     ssh -C -D 8119 pfh@usul.phfactor.net
    




That connects me to my account (pfh@phfactor.net). The -C asks for gzip compression, which speeds things up a bit over slow connections. The -D 8119 sets up the SOCKS proxy, and establishes port 8119 on the local machine as the proxy connection. You'll see a prompt after this, as the SOCKS part is invisible:  

![screenshot](http://www.phfactor.net/wp-pics/ssh-socks-login.png)  

Next, you have to tell your browser about it. I'll use Firefox, as its common and easy to use. Open up preferences, and go to Advanced/Network:  

![screenshot](http://www.phfactor.net/wp-pics/firefox-prefs.png)  

Then go to Settings:  

![screenshot](http://www.phfactor.net/wp-pics/firefox-proxy.png)  

Put in localhost/8119 for the SOCKS proxy, and use SOCKS4 and not the SOCKS5.






That's it! Now, every web page you surf travels over SSH to the remote host and is encrypted from you to there. (In my case, until it hits usul.phfactor.net) You still have to trust the server and sysadmin who runs it, but that's easier sometimes.






Enjoy!






Sources: [This page](http://www.mikeash.com/?page=ssh_socks.html) had the key bits, before I found it I had tried twice and failed. Thanks, interweb!  






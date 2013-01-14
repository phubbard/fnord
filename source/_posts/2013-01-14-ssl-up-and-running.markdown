---
layout: post
title: "SSL up and running"
date: 2013-01-14 10:25
comments: true
categories: ssl godaddy Meltdown
---

I've been meaning to set this up, and finally got it done. [https://fnord.phfactor.net/](https://fnord.phfactor.net) should work with no CA errors or hassles. I ended up buying a 1-year cert from GoDaddy for $7, which is quite reasonable and should be trusted by most browsers.

Install pretty straightforward, gotta love Apache2. Right now both HTTP and SSL work, might put in an auto-redirect just on principle.

Now that I've done it once, I think I'll buy another cert for www.phfactor.net; that'll also allow me to test SSL support in Meltdown.
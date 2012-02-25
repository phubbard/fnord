---
date: '2006-02-16 13:55:41'
layout: post
comments: true
slug: new-ca-and-service-certificates
status: publish
title: New CA and service certificates
wordpress_id: '60'
categories:
- News
---

Yep, finally found [a better walkthrough](http://hublog.hubmed.org/archives/001075.html) for Debian + CA + openssl + various services.

Whew.

So, new root CA, new certs on IMAPS, ASMTP. Grab the new CA cert [from here](http://www.phfactor.net/cacrt.txt) and import it. 

On a mac, the import is just

    
    
     sudo certtool i cacrt.txt v k=/System/Library/Keychains/X509Anchors
    




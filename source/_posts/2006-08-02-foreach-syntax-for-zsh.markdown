---
date: '2006-08-02 21:34:42'
layout: post
comments: true
slug: foreach-syntax-for-zsh
status: publish
title: Foreach syntax for zsh
wordpress_id: '156'
categories:
- Geek stuff
- Macintosh
---


I got my Shiny! New! Macbookpro! and am setting it up. I have a bunch of root CA certs to add, and finally tracked down the zsh syntax for it:

    
    
     foreach i (*.pem) sudo certtool i $i v k=/System/Library/Keychains/X509Anchors; end 
    


Sweet.

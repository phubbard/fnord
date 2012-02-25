---
date: '2007-06-28 20:12:59'
layout: post
comments: true
slug: better-image-sizes-in-bins-albums
status: publish
title: Better image sizes in Bins albums
wordpress_id: '357'
categories:
- Debian
- Photography
---

I use and like [Bins](http://bins.sautret.org/) for generating photo albums like [this one.](http://www.phfactor.net/pics/misc-anna/) When we upgraded our camera from 2 to 7 megapixels, the small/medium/large image sizing that bins does became a problem: at 7MP, even 'small' was over 1024x768.

Solution:

Edit the bins config file to reduce the sizes. It uses percentages, so given a target of VGA (640x480) I ended up with 20/40/100%.

For Debian, you first have to copy the default file into your own directory:

    
    
       cp /etc/bins/binsrc ~/.bins
    



Then edit it like so:


    
    
      <sizes>
        <size name="Small" shortname="Sm" height="20%" width="20%"/>
        <size name="Medium" shortname="Med" height="40%" width="40%"/>
        <size name="Large" shortname="Lg" height="100%" width="100%"/>
      </sizes>
    



It works, my family is happier, you have to remove the generated albums and re-run bins on each. Tedious, but only have to do it once.

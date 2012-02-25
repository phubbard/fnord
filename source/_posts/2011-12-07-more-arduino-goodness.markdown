---
date: '2011-12-07 14:48:26'
layout: post
comments: true
slug: more-arduino-goodness
status: publish
title: More Arduino goodness
wordpress_id: '1490'
categories:
- Arduino
---

Part work, part just-for-fun. [Arduino v1 software](http://arduino.cc/) was just released, and I'd wanted an excuse, so we now have the [Home Weather Statio](https://github.com/phubbard/hws)n, a ballad in two parts:





  1. Update old design with better and more sensors


  2. Add a second, outdoor node, connected with Zigbee.



I also wanted to try and remove the Python server component (simplify!) and have it push directly to Pachube from the Arduino. 

(Note that the code, sensor listing and such are [all on github](https://github.com/phubbard/hws))

I had crap data from the old temp sensor, which is the dead-simple, analog-out LM35CAZ. Roger advised me to try the Dallas Semi DS1820, which comes in two versions. The DS18S20 is 8-bit precision, and the DS18B20 10 or 12 bits. Since they're all of five bucks, I got the better B version.

On a whim, I added the [cheap light sensor](http://www.sparkfun.com/products/8688). Another five dollars, nice and small, why not.

I kept the same humidity sensor. Still happy with it. (Ohmic SC-600)

Here's a first pass, minus the ethernet:

![IMG 0381](http://fnord.phfactor.net/wp-content/uploads/2011/12/IMG_0381.jpg)

Not too bad to get that working, though I really need to solder the light sensor. Note that the light sensor maxes out at only 1,000 lux; full daylight around here is over 120,000.

Second pass: move to mini breadboard, clean up the wiring, add ethernet:

![IMG 0383](http://fnord.phfactor.net/wp-content/uploads/2011/12/IMG_0383.jpg)

Notes for others out there:




  1. Although the pins are exposed, digital pins 10-12 are used by the ethernet. So I had to move the DS1820 to pin 2.


  2. The updated Ethernet library has DNS and DHCP support, so my code can just connect to 'api.pachube.com'. However, you have to have DNS and DHCP working. Seems obvious, eh?


  3. Pachube has a very nice 'API debugger' that uses javascript; highly recommended. You can find it at https://pachube.com/users/phubbard/debug (swap in your username).


  4. Before I got things working, I needed to check locally that I was forming the HTTP request correctly. Here's a good trick:

    
    
     nc -l 8000
    


will start up a TCP listener on port 8000 that prints anything it gets. Then tell the Arduino to connect to that, and voila. Nice debug tool. (This is part of [netcat](http://netcat.sourceforge.net/)).


  5. I started this running yesterday, and this morning by 10 the data feed was frozen. [There's a known bug](http://code.google.com/p/arduino/issues/detail?id=605&start=200) or two in the Ethernet library, so I'm not sure yet where the fault is.


  6. I am using the wired Ethernet module, in a rental home where I can't pull cat5, so I'm using my Airport Extreme in bridge mode, and plugging the Arduino into the Airport. Works great, may get another one on Ebay.



Current configuration:

![IMG 0384](http://fnord.phfactor.net/wp-content/uploads/2011/12/IMG_0384.jpg)



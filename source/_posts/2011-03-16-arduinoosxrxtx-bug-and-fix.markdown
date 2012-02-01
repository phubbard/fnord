---
date: '2011-03-16 11:12:59'
layout: post
slug: arduinoosxrxtx-bug-and-fix
status: publish
title: Arduino+OSX+RXTX bug and fix
wordpress_id: '1395'
categories:
- Arduino
---

For those that might also hit this one - I was having problems with the Arduino IDE, it would refuse to connect to the Arduino claiming that the serial port was in use by another application.

(This is OSX 10.6, Arduino Duemilanove, Arduino software v22)

I fired up Console and saw this:

    
    3/16/11 11:01:51 AM	[0x0-0x3a03a].cc.arduino.Arduino[934]	check_group_uucp(): error testing lock file creation Error details:Permission deniedcheck_lock_status: No permission to create lock file.
    3/16/11 11:01:51 AM	[0x0-0x3a03a].cc.arduino.Arduino[934]	please see: How can I use Lock Files with rxtx? in INSTALL
    3/16/11 11:01:51 AM	[0x0-0x3a03a].cc.arduino.Arduino[934]	processing.app.SerialException: Serial port '/dev/tty.usbserial-A6008hB0' already in use.  Try quiting any programs that may be using it.


Which led to [this thread](http://www.arduino.cc/cgi-bin/yabb2/YaBB.pl?num=1211165807/6).

The fix:

    
    cd /Library/Java/Extensions
    rm rm RXTXcomm.jar librxtxSerial.jnilib



The problem was an outdated version of RXTX that was loaded before the one bundled with the Arduino. Removing it solves the problem. I had RXTX from a previous project, oops.

---
date: '2009-06-10 15:19:26'
layout: post
comments: true
slug: progress-on-the-arduino
status: publish
title: Progress on the Arduino
wordpress_id: '980'
categories:
- Arduino
- Code
---

I was having a bad karma day (OSX install failing, RabbitMQ borked, Debian server freezing, apt failures, etc, etc.) and worked a bit on the Arduino project as a break. Here's the LM35 wired up and working:

[![img_0189](http://fnord.phfactor.net/wp-content/uploads/2009/06/img_0189-450x600.jpg)](http://fnord.phfactor.net/wp-content/uploads/2009/06/img_0189.jpg)

(That's my ancient self-designed linear power supply with 5/6/12 and LM7805)

Temp out goes to ADC0. Arduino runs

    
    void setup() {
    // initialize the serial communication:
      Serial.begin(9600);
    }
    
    void loop() {
      // send the value of analog input 0:
      int val = analogRead(0);
      float fVal = map(val, 0, 1023, 0, 500);
      Serial.println(fVal);
      // wait a bit for the analog-to-digital converter
      // to stabilize after the last reading:
      delay(100);
    }


and, on the mac, Processing runs

    
    // Graphing sketch
    
    // This program takes ASCII-encoded strings
    // from the serial port at 9600 baud and graphs them. It expects values in the
    // range 0 to 1023, followed by a newline, or newline and carriage return
    
    // Created 20 Apr 2005
    // Updated 18 Jan 2008
    // by Tom Igoe
    
    import processing.serial.*;
    
    Serial myPort;        // The serial port
    int xPos = 1;         // horizontal position of the graph
    
    void setup () {
      // List all the available serial ports
      println(Serial.list());
      // I know that the first port in the serial list on my mac
      // is always my  Arduino, so I open Serial.list()[0].
      // Open whatever port is the one you're using.
      myPort = new Serial(this, Serial.list()[0], 9600);
      // don't generate a serialEvent() unless you get a newline character:
      myPort.bufferUntil('\n');
    }
    void draw () {
      // everything happens in the serialEvent()
    }
    
    void serialEvent (Serial myPort) {
      // get the ASCII string:
      String inString = myPort.readStringUntil('\n');
    
      println(trim(inString));
    }


Notes so far:



	
  1. On OSX 10.5, Processing fails with RXTX errors. The solution, found [here](http://iharder.sourceforge.net/current/java/), was a new version of librxtxSerial.jnilib, which I copied into /Library/Java/Extensions along with the RXTXcomm.jar

	
  2. Code has a truncation bug - no fractional degrees.

	
  3. Arduino is pretty easy to code and use; I'm impressed.




Up next is the more complex SC600 humidity sensor, for which I need capacitors and a bit of wirewrap. Wondering how to plot the captured data on a web page...

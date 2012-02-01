---
date: '2009-06-23 09:13:21'
layout: post
slug: arduino-datalogger-is-up
status: publish
title: Arduino datalogger is up!
wordpress_id: '1015'
categories:
- Arduino
---

As previously noted, I decided to make a super-simple office temperature and humidity datalogger based on the Arduino, LM35CAZ and SC600. Today I finally added the resistor and cap for the lowpass filter on the SC600 and the data looks good:

[![picture-22](http://fnord.phfactor.net/wp-content/uploads/2009/06/picture-22.png)](http://fnord.phfactor.net/wp-content/uploads/2009/06/picture-22.png)

Yep, that web page is public. [You too can see ](http://137.110.111.142:2000/)the ambient conditions in Calit2 room 6402! Temperature is Celsius, humidity is relative percent.

For some reason the temperature data is noisier than I'd expect, but the humidity data looks clean. I'll have to see if I can pull the data into a graphing page - I'm experimenting with adding it to Cacti (thus the format of the web page, designed for machine consumption) but have not gotten it working yet.(see below)

Here's an iPhone snap of the completed circuit - really quite minimal. The LM35 needs no external parts at all, and the SC600 just needs the 47uF cap and 100k resistor. Good sensors for this, and cheap too.

[![img_0005](http://fnord.phfactor.net/wp-content/uploads/2009/06/img_0005-450x600.jpg)](http://fnord.phfactor.net/wp-content/uploads/2009/06/img_0005.jpg)

(Yeah, I really covet the macro photo ability of the new iPhone.)

It turns out that the Arduino outputs 5VDC, so I don't even need the power supply to run it - all via USB. Elegant, that.

**Update 6/26/09**: Data in Cacti! I had to prefix the HTML output with a space to get the data ingester to work, and fiddled with the graph settings to get it to display. Check out [the page here](http://www.phfactor.net/cacti/graph_view.php?action=preview) (login is guest/guest) and admire the data.

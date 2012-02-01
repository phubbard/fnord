---
date: '2009-06-15 13:33:17'
layout: post
slug: arduino-and-twisted
status: publish
title: Arduino and Twisted
wordpress_id: '986'
categories:
- Arduino
---

The datalogger progresses - now with carefully-soldered SC600 sensor online:
[![img_0191](http://fnord.phfactor.net/wp-content/uploads/2009/06/img_0191-450x600.jpg)](http://fnord.phfactor.net/wp-content/uploads/2009/06/img_0191.jpg)Still need to add the 47uF cap and 100k RC filter, though, so the humidity data is crap.

I cleaned up the code a bit. The Arduino now simply sends raw ADC counts, and lets the other side do the linearization and conversion. Much more sensible. To make it easy, I have the Arduino send

    
    ADC ADC\n


In other words, value space value newline, which is the easiest possible thing to parse on the other end. Code is now simply:

    
    
    void setup() {
    // initialize the serial communication:
      Serial.begin(9600);
    }
    
    void loop() {
      Serial.print(analogRead(0));
      Serial.print(" ");
      Serial.print(analogRead(1));
      Serial.println();
    }
    



Using the magnificent [Twisted](http://twistedmatrix.com/trac/) framework, this is a '[LineReceiver](http://twistedmatrix.com/documents/8.2.0/api/twisted.protocols.basic.LineReceiver.html)' protocol on top of a serial port, so the code to read it is quite compact. I won't paste it here, as its 85 lines with all the comments, command line parsing, error handling and such, but here are the key bits:

    
    class Echo(LineReceiver):
        def processData(self, data):
            """Convert raw ADC counts into SI units as per datasheets"""
            if len(data) != 2:
                return
    
            tempCts = int(data[0])
            rhCts = int(data[1])
    
            rhVolts = rhCts * 0.0048828125
            # 10mV/degree, 1024 count/5V
            temp = tempCts * 0.48828125
            # TODO need to rewrite this to include thermal compensation as per SC600 datasheet!
            humidity = (rhVolts * 45.25) - 42.76
            logging.info('Temp: %f C Relative humidity: %f %%' % (temp, humidity))
    
        def lineReceived(self, line):
            try:
                data = line.split()
                logging.debug(data)
                self.processData(data)
            except ValueError:
                logging.error('Unable to parse data %s' % line)
                return
    if __name__ == '__main__':
        logging.basicConfig(level=logging.INFO, \
                    format='%(asctime)s %(levelname)s [%(funcName)s] %(message)s')
    
        o = THOptions()
        try:
            o.parseOptions()
        except usage.UsageError, errortext:
            logging.error('%s %s' % (sys.argv[0], errortext))
            logging.info('Try %s --help for usage details' % sys.argv[0])
            raise SystemExit, 1
    
        if o.opts['baudrate']:
            baudrate = int(o.opts['baudrate'])
    
        port = o.opts['port']
    
        logging.debug('About to open port %s' % port)
        s = SerialPort(Echo(), port, reactor, baudrate=baudrate)
        reactor.run()


Gotta love Python! (And Arduino.) Next up is trying to get the data into [Cacti](http://fnord.phfactor.net/2008/11/14/cacti-snmp-airport-express-and-mib-a-quiet-leap-forward/) or RRDtool...

**Update 6/17:** Adding a web interface took just a few more lines of code:

    
    
    class indexPage(resource.Resource):
        isLeaf = True
    
        def render_GET(self, request):
            ccStr = 'Temp:%f Humidity:%f\n' % (lastTemp, lastRH)
            return ccStr
    
        root = indexPage()
        site = server.Site(root)
        reactor.listenTCP(2000, site)
    
    Now trying to get Cacti to parse the data it returns.

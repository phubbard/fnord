---
date: '2011-11-24 08:40:42'
layout: post
slug: debian-update-broke-dailystrips
status: publish
title: Debian update broke dailystrips
wordpress_id: '1478'
categories:
- Debian
---

One of the downsides of Debian is that (rarely) a package update breaks something. Today it's dailystrips, which when run yields the obtuse:


> 
/usr/bin/perl: symbol lookup error: /usr/lib/perl5/auto/List/Util/Util.so: undefined symbol: Perl_Gthr_key_ptr




No fix yet. 

Update 11/25:

The fix required:

    
    
    apt-get install libperl-dev
    rm -rf  /usr/lib/perl5/auto/List/Util
    apt-get install libio-compress-perl
    rm -rf /usr/lib/perl5/auto/Crypt/SSLeay
    apt-get install libnet-ssleay-perl 
    
    


Yeesh. Looks like I really, really need to do a clean install the next time I migrate servers. Leftover cruft from old Perl.

Hope this helps someone else!

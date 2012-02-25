---
date: '2009-02-12 11:15:45'
layout: post
comments: true
slug: python-continues-to-impress
status: publish
title: Python continues to impress
wordpress_id: '894'
categories:
- Code
- Python
---

I was browsing the Python 2.6 docs and saw the 'datetime' library. On a lark, I rewrote my old C-coded '[days' app](http://www.phfactor.net/code/days/) as Python:

    
{% codeblock lang:python %}    
    #!/usr/bin/env python
    # Rewrite of days-old calculator using Python. Gotta love this language!
    # pfh 2/12/09
    
    import datetime
    
    bd = datetime.date(year=1968,month=2,day=2)
    today = datetime.date.today()
    
    tdiff = today - bd
    
    print("\nToday is %s and you are %s days old.\n" \
    % (today.strftime("%A, %B %d %Y"), tdiff.days))
{% endcodeblock %}

Took me all of ten minutes, and the code is shorter, easy to tweak and such. Damn, I'm liking Python.

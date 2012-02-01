---
date: '2010-05-25 13:52:47'
layout: post
slug: a-look-at-productivity-and-metrics
status: publish
title: A look at productivity and metrics
wordpress_id: '1255'
categories:
- Code
---

I'm always curious about how, why and wherefore when it comes to getting code written. We had a software engineering undergrad course, I've read some of the classic books ([Brooks](http://www.amazon.com/Mythical-Man-Month-Software-Engineering-Anniversary/dp/0201835959/ref=sr_1_1?ie=UTF8&s=books&qid=1274823275&sr=1-1), [DeMarco/Lister](http://www.amazon.com/Peopleware-Productive-Projects-Teams-Second/dp/0932633439/ref=sr_1_1?ie=UTF8&s=books&qid=1274823296&sr=1-1), etc) with various metrics, and I've always kept an eye out for [ways to measure my own productivity](http://code.google.com/p/line-counting/). For your and my amusement, here's [a work project](http://ooici.net/doxygen/data_exchange/), in [Python](http://python.org/) / [Twisted](http://twistedmatrix.com/), with Git repository metrics from a commercial product called [FishEye](http://www.atlassian.com/software/fisheye/):

[caption id="attachment_1259" align="alignnone" width="282" caption="Code was from October 2009 through April 2010"][![Code was from October 2009 through April 2010](http://fnord.phfactor.net/wp-content/uploads/2010/05/Screen-shot-2010-05-25-at-2.31.40-PM.png)](http://fnord.phfactor.net/wp-content/uploads/2010/05/Screen-shot-2010-05-25-at-2.31.40-PM.png)[/caption]

[caption id="attachment_1257" align="alignnone" width="281" caption="Bursts of productivity on the week view"][![Bursts of productivity on the week view](http://fnord.phfactor.net/wp-content/uploads/2010/05/Screen-shot-2010-05-25-at-2.31.20-PM.png)](http://fnord.phfactor.net/wp-content/uploads/2010/05/Screen-shot-2010-05-25-at-2.31.20-PM.png)[/caption]

The weekly view makes sense - we run an agile process here, so those correspond to 'iterations' of development.

Here you can see the code accumulate:

[caption id="attachment_1256" align="alignnone" width="284" caption="Top graph is total lines of code."][![Top graph is total lines of code.](http://fnord.phfactor.net/wp-content/uploads/2010/05/Screen-shot-2010-05-25-at-2.31.07-PM.png)](http://fnord.phfactor.net/wp-content/uploads/2010/05/Screen-shot-2010-05-25-at-2.31.07-PM.png)[/caption]

Last, and most interesting in my opinion, is the commits by day:

[caption id="attachment_1258" align="alignnone" width="276" caption="Thursday is my best day??"][![Thursday is my best day??](http://fnord.phfactor.net/wp-content/uploads/2010/05/Screen-shot-2010-05-25-at-2.31.31-PM.png)](http://fnord.phfactor.net/wp-content/uploads/2010/05/Screen-shot-2010-05-25-at-2.31.31-PM.png)[/caption]

I would _never_ have guessed that Thurs was my best day in terms of commits.

(Note the time graph is broken, as FishEye is converting timezones incorrectly. I'm not really pushing code at midnight.)

This is a small-to-medium-sized project, less than 5[KLOC](http://en.wikipedia.org/wiki/Source_lines_of_code), with basically one developer, so the usual caveats about anecdotes apply. Still interesting to me. I'll repost here in a few months, we're now collaborating on a larger, shared project and it'll be interesting to see what that does to the stats.

**Update 5/26: ** The code is fairly complex, a set of a dozen or so modules communicating over AMQP to implement an OpenDAP cache accessed via HTTP proxy and/or web interface, and also includes a decent set of unit and integration tests.

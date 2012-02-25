---
layout: post
comments: true
title: "Added email subscriptions to the site"
date: 2012-02-24 09:13
comments: true
categories: [octopress, email, news]
---

If you look in the upper right next to the search area, there's a new icon that looks like this:

![email icon](/images/email.png)

[Click it](http://feedburner.google.com/fb/a/mailverify?uri=phfactor/rzbg&amp;loc=en_US) and you can subscribe to daily updates via email, implemented via Feedburner. I know that some
folks used to read the site that way, so I'm pleased to have it working on Octopress. 

If you want to set it up on your Octopress site, there's two steps. You have to setup Feedburner
with your RSS or Atom feed, then go to the 'Publicize' tab and activate email. Then take the HTTP URL
they give you and enter it into the _config.yml:
```
subscribe_email: http://feedburner.google.com/fb/a/mailverify?uri=phfactor/rzbg&amp;loc=en_US
```

Leave a comment if you have any problems, or email me - the feed now includes my email address.


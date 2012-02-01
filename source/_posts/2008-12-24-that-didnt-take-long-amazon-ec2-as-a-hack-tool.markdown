---
date: '2008-12-24 09:38:46'
layout: post
slug: that-didnt-take-long-amazon-ec2-as-a-hack-tool
status: publish
title: That didn't take long... Amazon EC2 as a hack tool
wordpress_id: '869'
categories:
- Networking
- Spam/UCE
---

I run [denyhosts](http://www.google.com/url?sa=U&start=1&q=http://denyhosts.sourceforge.net/&ei=OnNSSfOBFtLjtged2YmdDg&usg=AFQjCNGrbFn6Zcgh0axbN49-Bp_jTyOJqA) locally, which bars access to any computer trying to login over ssh after a few failed password attempts. Even as a net nobody, you see a **lot** of these attacks; I have several tens of thousands of blocked hosts now. They seem to be mostly home-connected Windows machines, but this morning a new wrinkle showed up:

    
    Added the following hosts to /etc/hosts.deny:
    
    174.129.151.164 (ec2-174-129-151-164.compute-1.amazonaws.com)


Someone had the fairly obvious idea of using Amazon's[ EC2 elastic compute cloud](http://www.google.com/url?sa=U&start=1&q=http://aws.amazon.com/ec2/&ei=ZXNSSf2YCOHAtgeKstDmBg&usg=AFQjCNEYw8DpyWQwP8htAHZQc9rvv0GqHg) to run hack attacks, since there's no reason for EC2 to be trying to login to my network. Now I gotta figure out how to report this to Amazon; at least with them there's an audit trail. Which probably leads back to a stolen credit card, but still.

**Update 12/25/08**: Jeff Barr from Amazon left a couple of comments with instructions, so I've reported it. Thanks, Jeff!

**Update 12/26**: Email back from Amazon, instance shut down, very professional and fast.

**Update 12/27**: Two more attempts today from different IPs. Seems to be a problem.

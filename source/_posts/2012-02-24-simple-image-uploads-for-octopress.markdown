---
layout: post
title: "Simple image uploads for Octopress"
date: 2012-02-24 11:47
comments: true
categories: octopress, python, code
---

One of the features from Wordpress I've been missing is easy support for uploading and including
images. WP has a fancy GUI for this, and handles the uploads well. 

So today did a hack while inspired. Shared as a gist on Github, this code:

* Makes the path YYYY/MM/DD, e.g. '2012/02/24'
* Verifies that the directory created is writeable
* Does an upload via the filesystem
* Fetches the uploaded file via HTTP for an end-to-end check
* Computes MD5 hashes of both to make sure it made it intact
* Print out the full URL of the image, for easy use in your editor
* Copies said URL into the copy & paste buffer via pbcopy
 
Usage is pretty basic:
```
code/Image_uploader/upload.py Desktop/sorry.png
http://fnord.phfactor.net/wp-content/uploads/2012/02/24/sorry.png
```
In one step, you've uploaded the file and can go paste the URL into the editor!

I wanted to use scp, but was unable to find a way to create directories easily. It's do-able, but
since I paid for ExpanDrive I'm not averse to using it. Here's the code in case you want it:
{% gist 1903244 %}

Gotta love Python. And Github. And Octopress.


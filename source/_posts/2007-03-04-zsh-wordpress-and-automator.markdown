---
date: '2007-03-04 13:23:12'
layout: post
comments: true
slug: zsh-wordpress-and-automator
status: publish
title: zsh, wordpress and automator
wordpress_id: '300'
categories:
- Code
- Reviews and recommendations
---

The problem:

Given a random JPEG, scale it to 400 pixels wide (this is what seems to fit on this blog), append an extension, upload it to the website, and put the complete URL into the clipboard for subsequent posting.

The solution:

[Automator](http://www.apple.com/macosx/features/automator/) for doing the image operations and filename appending, followed by two zsh scripts for iteration, upload, file movement and such.

wp-iterator.zsh:

    
    
    #!/bin/zsh
    # Loop over image files, upload each.
    # pfh 3/4/07
    
    cd /Users/hubbard/Desktop/Wordpress
    
    foreach f in *-wp.jpg
     #echo $f
     $HOME/bin/wp-upload.zsh $f
     if [[  $? == 0 ]]; then  
       mv $f Posted
     else
       echo $? : Error uploading $f: leaving it in place!
     fi
    end
    



...which invokes wp-upload.zsh:

    
    
    #!/bin/zsh
    # Script to upload a blog pic and paste its url into the clipboard
    # pfh 3/4/07
    
    scp -q $1 USERNAME@WEBHOST:/export/website/wp-pics
    echo http://www.phfactor.net/wp-pics/$1 | pbcopy
    pbpaste
    



(URL and username removed for spam reasons)

I then have a wrapper Automator scrip that just invokes the 'copy-scale-rename' script and then the wp-iterator.zsh script. URLs are pasted into the clipboard, which works for more than one file because I run [Jumpcut.](http://jumpcut.sourceforge.net/)

A successful run looks like this:

    
    
    ./wp-iterator.zsh 
    http://www.phfactor.net/wp-pics/img_1961-bb-wp.jpg
    



Also required: An ssh agent, I use [sshkeychain.](http://www.sshkeychain.org/) Otherwise, it'll ask for your password each time.

When done, I dragged the wrapper Automator program to the toolbar, where I can just drop images. Seems to work!

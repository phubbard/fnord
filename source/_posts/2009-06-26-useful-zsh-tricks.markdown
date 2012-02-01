---
date: '2009-06-26 10:43:08'
layout: post
slug: useful-zsh-tricks
status: publish
title: Useful zsh tricks
wordpress_id: '1020'
categories:
- Code
- Geek stuff
---

I'm using [zsh](http://www.zsh.org/) on my mac, mostly for its better completion system. A coworker asked me for a couple of tweaks, the answers took a bit to find so here's a FYI for the command line nerds out there.

**Q1: The cd command tab-completes files, which is totally broken.**

**Fix**:

    
     compctl -/ cd




**Q2: Tab-completion for git commands, please**




**Ans**:

    
     compctl -k "(add bisect branch checkout co clone commit diff fetch grep init log merge mv pull push rebase reset rm show status tag)" git







The second just says that that 'these words in the array are the arguments for the git command.'




There's also the vastly [more elaborate code here](http://wunjo.org/zsh-git/), which modifies the prompt to show git status when in a git-controlled repository. I'm trying that now.










**Q3: Fix the prompt when using **[**virtualenv**](http://pypi.python.org/pypi/virtualenv)




**Ans**: See [this post](http://blog.doughellmann.com/2008/12/virtualenvwrapper-161-even-more-zsh.html) (especially read the comments). Looks like 1.6.1 of [virtualenvwrapper](http://www.doughellmann.com/projects/virtualenvwrapper/) and newer should 'just work.'

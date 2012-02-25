---
date: '2007-01-15 14:14:40'
layout: post
comments: true
slug: one-less-microsoft-office-annoyance
status: publish
title: One less Microsoft Office annoyance
wordpress_id: '279'
categories:
- Macintosh
---

The culprit:

![](http://www.phfactor.net/wp-pics/20060712-acrotoolbar.png)

Based on [this page](http://www.kassblog.com/index.php?itemid=297), a quick command-line method for permanently removing the Acrobat toolbar from Microsoft Office 2004 on Mac:

    
    
    cd /Applications/Microsoft\ Office\ 2004/Office/Startup/Excel
    rm PDFMaker.xla; touch PDFMaker.xla; chmod 444 PDFMaker.xla
    cd ../Word
    rm PDFMaker.dot; touch PDFMaker.dot; chmod 444 PDFMaker.dot 
    



God, I hate that sort of unwanted visual crud. 


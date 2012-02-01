---
date: '2007-11-10 11:55:40'
layout: post
slug: macbook-pro-hard-drive-upgrade
status: publish
title: Macbook pro hard drive upgrade
wordpress_id: '541'
categories:
- Macintosh
- Reviews and recommendations
---

Not too bad. I'm now sporting [a 250GB drive](http://eshop.macsales.com/item/Hitachi/0A53329/) (!!), quite easy to do. Lots of Torx and Phillips screws, but not bad with patience and help from a co-worker.

Data transfer was via rsync:

    
    
      sudo rsync -axvE --progress / /Volumes/New


(Actually, the volume name is Rex Tremendae, a hat tip to [Berlioz's Requiem.](http://www.amazon.com/Berlioz-Requiem-Boito-Prologue-Mefistofele/dp/B000003CTJ/ref=pd_sim_m_img_3/103-4858399-7534239) Good stuff, that.)

After that, just go into Prefs and select the new drive as the boot volume. Almost too easy.


![Big dang disk](http://www.phfactor.net/wp-pics/rex-tremendae.jpg)


What amazing times we live in. 250 (marketing) gigabytes for two hundred and nine dollars!

BTW, the Hitachi appears to be quieter than the stock 120G it replaced. Speed seems about the same in casual use so far.

---
date: '2007-08-25 10:37:14'
layout: post
slug: fnord-updates-downtime-themes
status: publish
title: Fnord updates - downtime, themes
wordpress_id: '426'
categories:
- News
- Spam/UCE
---

We were down last night from about 11:30PM until today around 11AM. Somehow, some [censored] managed to add a link to my sidebar by inserting into the wp_links table for wordpress.

After thinking about it for a bit, I'm updating this post: The link was to www.snjpc.com. It's an online casino site, and while I dislike giving them hits it seems worthwhile to say that they, or their hires, are doing this sort of blog cracking.

How they managed this, I am still trying to determine. The mysql logfiles
`
cd /var/log/mysql
mysqlbinlog *.0* | grep wp_links
`
show no inserts, the mysql instance is only available from localhost (firewalled to boot), and system logs look good. Checks for rootkits and similar are negative, firewall logs are clean, and I am puzzled. Props to [this page](http://souptonuts.sourceforge.net/readme_mysql.htm) for mysql tips.

One piece of evidence - they seem to have borked wordpress, probably on purpose - if you invoke the theme editor (or plugin editor) you get

    
    
    Sorry, that file cannot be edited.


which is patently false. My working hypothesis is, for now, that someone managed to either inject an exploit into Debian's wordpress package, or found a generic Wordpress exploit. I am continuing to investigate and take various measures to prevent a reoccurence. This sucks.

Oh yeah, swapped themes for a while as part of the cleanup and diagnostics. Let me know what you think.

Update: Added paragraph naming snjpc.com

Update: A fresh download of Wordpress 2.2.2 from Debian or wordpress.org produces the same result... interesting. So either the default WP is broken, or its a config file/database problem. Debugging continues...

Update: Looks like the problem is related to the list of files passed to the `validate_file_to_edit` function. It looks like the first file passed is the wp-config.php, which on Debian is a link to the system file in /etc/wordpress. Hmm, maybe that's how they got the MySQL access information... You can hack around this by adding the following to theme-editor.php. Change this:

    
    
    if (empty($file)) {
    $file = $allowed_files[0];
    }
    $file = validate_file_to_edit($file, $allowed_files);


to the following. This overrides the file list that was passed in, so you have to change the index to match the file you want. Other than that, it totally fixes the problem. Hmm...

    
    
    if (empty($file)) {
    $file = $allowed_files[0];
    }
    
    $file = $allowed_files[3];
    
    $file = validate_file_to_edit($file, $allowed_files);

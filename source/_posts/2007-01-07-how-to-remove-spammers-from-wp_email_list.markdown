---
date: '2007-01-07 18:35:41'
layout: post
slug: how-to-remove-spammers-from-wp_email_list
status: publish
title: How to remove spammers from wp_email_list
wordpress_id: '273'
categories:
- Geek stuff
- Spam/UCE
---


Sigh. They try to spam the site via the email signup. So I can remember, the magic is:


    
    
    mysql -u root -p
    use wordpress;
    delete from wp_email_list where gets_mail is NULL;
    



2031 records. Ye gods.

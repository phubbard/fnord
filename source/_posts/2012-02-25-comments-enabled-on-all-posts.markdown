---
layout: post
title: "Comments enabled on all posts"
date: 2012-02-25 07:43
comments: true
categories: octopress
---

Another item off the to-do list - all posts here should now have comments enabled. A
bit of Perl:
```
perl -pi -e 's/layout: post/layout: post\ncomments: true/g' *.markdown
```

I think the [exitwp](https://github.com/thomasf/exitwp) script that I used didn't add the comments: true field. 

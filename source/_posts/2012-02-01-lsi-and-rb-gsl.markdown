---
layout: post
title: "LSI and rb-gsl"
date: 2012-02-01 16:19
comments: true
categories: Octopress, Ruby, lazyweb
---

So I'm spelunking through [the Octopress docs](https://github.com/mojombo/jekyll/wiki/Configuration) and 
find a flag for 'related posts'. 

In _config.yml, set
```
lsi: true
```

...and watch your laptop turn into a smoldering heap of rubble. My
```
rake generate
```
is still cranking, fans roaring, as it tries to generate related posts. It does helpfully say
> Notice: for 10x faster LSI support, please install http://rb-gsl.rubyforge.org/

But [rb-gsl](http://rb-gsl.rubyforge.org/) is Ruby on top of [GSL](http://www.gnu.org/software/gsl), hmm. GSL compiles and installs no prob, but rb-gsl dies:
```
gem install gsl
```
yields lots of compiles then
```
gcc -I. -I/Users/hubbard/.rvm/rubies/ruby-1.9.2-p290/include/ruby-1.9.1/x86_64-darwin11.2.0 -I/Users/hubbard/.rvm/rubies/ruby-1.9.2-p290/include/ruby-1.9.1/ruby/backward -I/Users/hubbard/.rvm/rubies/ruby-1.9.2-p290/include/ruby-1.9.1 -I. -DHAVE_NARRAY_H  -I/Users/hubbard/.rvm/gems/ruby-1.9.2-p290/gems/narray-0.6.0.1/. -I/Users/hubbard/.rvm/rubies/ruby-1.9.2-p290/lib/ruby/site_ruby/1.9.1/x86_64-darwin11.2.0 -I/Users/hubbard/.rvm/usr/include -D_XOPEN_SOURCE -D_DARWIN_C_SOURCE   -fno-common  -Wall -I../include  -I/usr/local/include  -o matrix_complex.o -c matrix_complex.c
matrix_complex.c:1525: error: conflicting types for âgsl_matrix_complex_equalâ
/usr/local/include/gsl/gsl_matrix_complex_double.h:227: error: previous declaration of âgsl_matrix_complex_equalâ was here
make: *** [matrix_complex.o] Error 1


Gem files will remain installed in /Users/hubbard/.rvm/gems/ruby-1.9.2-p290/gems/gsl-1.14.7 for inspection.
Results logged to /Users/hubbard/.rvm/gems/ruby-1.9.2-p290/gems/gsl-1.14.7/ext/gem_make.out.
```

Drat. No fix yet.
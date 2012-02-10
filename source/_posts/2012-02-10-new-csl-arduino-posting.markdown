---
layout: post
title: "New CSL Arduino posting"
date: 2012-02-10 10:29
comments: true
categories: Arduino, CSL, Octopress
---

A couple of quick notes - at the suggestion of a friend, I've written some posts for [the Citizen Scientists League](http://citizenscientistsleague.com/2012/02/09/getting-the-arduino-software-and-hardware-working-first-in-a-series/) on 
the Arduino weather station. Code, setup, circuitry, Pachube interface and such. I'm curious to see how the response is there, as they probably get more readers than I do here.

Secondly, a quick tweak to Octopress - when you create a new post using rake, I added calls to add the post to git and fire up the editor, as those are what I'd do next anyway. Here's the snippet from the Rakefile:
```
# usage rake new_post[my-new-post] or rake new_post['my new post'] or rake new_post (defaults to "new-post")
desc "Begin a new post in #{source_dir}/#{posts_dir}"
task :new_post, :title do |t, args|
  raise "### You haven't set anything up yet. First run `rake install` to set up an Octopress theme." unless File.directory?(source_dir)
  mkdir_p "#{source_dir}/#{posts_dir}"
  args.with_defaults(:title => 'new-post')
  title = args.title
  filename = "#{source_dir}/#{posts_dir}/#{Time.now.strftime('%Y-%m-%d')}-#{title.to_url}.#{new_post_ext}"
  if File.exist?(filename)
    abort("rake aborted!") if ask("#{filename} already exists. Do you want to overwrite?", ['y', 'n']) == 'n'
  end
  puts "Creating new post: #{filename}"
  open(filename, 'w') do |post|
    post.puts "---"
    post.puts "layout: post"
    post.puts "title: \"#{title.gsub(/&/,'&amp;')}\""
    post.puts "date: #{Time.now.strftime('%Y-%m-%d %H:%M')}"
    post.puts "comments: true"
    post.puts "categories: "
    post.puts "---"
  end
  # pfh 2/10/12
  system "git add #{filename}"
  system "edit #{filename}"
end
```

One more note - if you use zsh, you have to escape the square brackets. Here's the syntax when I created this post:
```
rake new_post\["New CSL Arduino posting"\]
```
Mildly annoying.



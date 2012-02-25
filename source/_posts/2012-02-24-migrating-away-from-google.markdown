---
layout: post
comments: true
title: "Migrating away from Google"
date: 2012-02-24 13:30
comments: true
categories: [google, newsblur, duckduckgo]
---

There's an inherent tension when a company provides a free service: How do they
make money? Are *you* the product? Is it a [Freemium](https://en.wikipedia.org/wiki/Freemium) model? Do they even have a plan?

If it's free, they can always go out of business, change the terms, or generally do anything they want. 
Those are your risks. 

There has been, in the last couple of years, a recurring spate of news about Google that gives me
pause. [Censorship in China](https://en.wikipedia.org/wiki/Censorship_by_Google), the [blending of Plus into search](http://googleblog.blogspot.com/2012/01/search-plus-your-world.html), etc, etc.

The thing that tipped me into action is their awful new ['privacy' policy](http://googleblog.blogspot.com/2012/01/updating-our-privacy-policies-and-terms.html)
(By the way, you should really [clear your Google history](https://www.eff.org/deeplinks/2012/02/how-remove-your-google-search-history-googles-new-privacy-policy-takes-effect) 
before that takes effect on March 1st!). Me no like.

It's their company. They have to make a profit, and it's their choice how they do so. From the 
point of view of a random nerd, I strongly dislike the level of fine-grained data they will be
gathering and selling. I am choosing to look for alternatives, and I'm happy to pay for them.

Let me share what I've found so far. For the most part, I'll just mention the ones I chose and not
try to enumerate all the alternatives.

## Search

Still far and away the best product from Google, I must say. I've been using
the oddly named [DuckDuckGo](http://duckduckgo.com) which I found via [John Gruber](http://daringfireball.net/linked/2012/01/16/winer-bing). It takes some
getting used to, but has some new features I like too. Using '!so' to search StackOverflow is handy, 
as are the Python and Android shortcuts. I'm warming up to it.

#### Search in Safari or other browsers

If, as I recommend strongly, you are running [GlimmerBlocker](http://glimmerblocker.org/), then adding DDG to Safari
is pretty easy - see [this page](http://help.duckduckgo.com/customer/portal/articles/216447-safari) for instructions. 

Chrome or Firefox are also tweakable; see [the same page](http://help.duckduckgo.com/customer/portal/articles/216447-safari)
#### Search on iPhone / iPad

No easy way to replace Google with DDG here. DDG does have [mobile search apps](http://help.duckduckgo.com/customer/portal/articles/216419-apps) for iOS and Android, but 
it's not integrated into Safari.

#### Search on your blog

If you use the search bar here on Fnord, as of today it'll go via DDG. Kudos to them for having [Octopress instructions](http://help.duckduckgo.com/customer/portal/articles/361829-octopress) - major nerd plus!
They also support other platforms, of course.

## RSS/Atom (Google Reader)

There are several alternatives here. I found and recommend [NewsBlur](http://www.newsblur.com/), which
is Freemium, [open source](http://github.com/samuelclay) and has an iPhone app. I simply exported my OPML from Google Reader, imported
it into NewsBlur and have never looked back. I paid for the Premium account, which is as I recall ~20/year; you set the donation amount. 

Minuses:

* iPhone app is a bit crashy
* No iPad app yet

Overall - strongly recommended. I use the main site on the desktop and the iPhone app. Works great.

## Email

I run an Exim-based mailserver here, though a few years ago I conceded the spam battle. My personal email 
is now forwarded to [SpamCop](http://www.spamcop.net/) for filtering. $30/year, fantastic. Never a single outage
or problem in three years now. I have a hybrid setup, where I archive messages to my IMAP server, but the inbox is on SpamCop. 

## Blogs

Depending on your level of techie interest, you can self-host as I do, use Github and Octopress, or one of the other
free platforms such as Tumblr, Posterous, WordPress.com and so on. I prefer to self-host, as that way I have my 
data locally and complete control. Plus, it's fun to do this stuff yourself!

If you do run WordPress, there are commercial services that'll handle all the sysadmin work for you. It's a pain
if your site gets popular. 

## Analytics

I paid for and like [Mint](http://www.haveamint.com/). You can see my stats [on this page](http://www.phfactor.net/mint/). The price is reasonable,
the install painless and the results decent. For my WatchOtaku site, I've been using [Clicky](http://getclicky.com/), as it's a bit nicer but really 
Mint would work there too. There are others; for my level of traffic and casual observation these both suffice.

## Code and project hosting

Go [Github](http://github.com). Don't even consider anything else. It's *that* good.

Also works for [static pages like this one](http://phubbard.github.com)

## Maps and directions

I've not tackled this one yet. Any suggestions? Mapquest perhaps? Even harder on the iPhone/iPad.

## Google Docs

I used to use this more at UCSD, these days it's a combination of IM, Email and the rare DOCX file. No suggestions, 
other than to suggest using HTML for doc formatting; makes posting it easier anyway.

## Google apps for your domain

I use this a bit; Google is still doing the mail for WatchOtaku. I can live with this for now and will 
migrate off if the account starts getting a lot of email; right now its about 1 per month and I can accept that. Since 
that's a domain-specific hobby/account/site, the analytics from it are gonna be bizarre.

## Conclusions

Google has some excellent products and replacing them takes time and money. It's worth it to me. I'd rather
spend a few bucks then be monetized, but of course YMMV.

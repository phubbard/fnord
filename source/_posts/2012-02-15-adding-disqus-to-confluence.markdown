---
layout: post
title: "Adding Disqus to Confluence"
date: 2012-02-15 13:28
comments: true
categories: disqus, confluence, code
---

I'm trying to get non-spammy commenting working on [my Confluence site](http://watchotaku.com) and
it's a pain in the ass. The native solution is CAPTCHA-based, and that's been 
defeated by spammers.

I have a semi-solution using (as with Fnord) Disqus. Some notes for other folks attempting this:

 1. You have to use the [raw Javascript functions of Disqus](http://docs.disqus.com/developers/universal/)
 2. On Confluence, go into Site admin / Theme / Layout editor / Page footnotes
 3. Change Options to 'Velocity then raw HTML'
 4. Change the shortname to that of your site
 
Here's mine so far, with the short name munged:
```
<div id="disqus_thread"></div>
<script type="text/javascript">
    var disqus_shortname = 'CHANGEME'; // required: replace example with your forum short name

    (function() {
        var dsq = document.createElement('script'); dsq.type = 'text/javascript'; dsq.async = true;
        dsq.src = 'http://' + disqus_shortname + '.disqus.com/embed.js';
        (document.getElementsByTagName('head')[0] || document.getElementsByTagName('body')[0]).appendChild(dsq);
    })();
</script>
<noscript>Please enable JavaScript to view the <a href="http://disqus.com/?ref_noscript">comments powered by Disqus.</a></noscript>
<a href="http://disqus.com" class="dsq-brlink">blog comments powered by <span class="logo-disqus">Disqus</span></a>
```

This seems to almost work, but the variables that tell Disqus what page it is seem to be unreachable.
Normally, you set
```
disqus_url
disqus_identifier
```
but I can't tell how to read those. I've tried (from [these docs](https://developer.atlassian.com/display/CONFDEV/Confluence+Objects+Accessible+From+Velocity))
```
$req
$req.contextPath
```
but those are not found. 

Syntax was
```
var disqus_identifier = $req.contextPath;
```
which produces an error visible in the Safari error console about req not being found.

I also tried (from [these docs](http://confluence.atlassian.com/display/DOC/Guide+to+User+Macro+Templates))
```
$content
$content.getEntity().getRequestUrl()
```
but even content is not found. Perhaps some syntax error with the Velocity engine stuff, but the mixture
of Velocity and Javascript is very poorly documented. I was unable to find anyone else using Disqus with Confluence,
so if you have any tips do say so here!

At present, it's almost working. The page portion loads, the Disqus portal seems happy, but due to
the lack of URL is causing comments to not load on the page they should be attached to.

Drat.
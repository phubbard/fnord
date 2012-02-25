---
date: '2011-02-04 16:39:12'
layout: post
comments: true
slug: a-tasty-programming-morsel
status: publish
title: A tasty programming morsel
wordpress_id: '1374'
categories:
- Code
- Geek stuff
---

I, along with a co-worker or two, was a big fan of the impromptu programming challenges posted to [The Reinvigorated Programmer](ttp://reprog.wordpress.com/). There's a real art to finding just the right puzzle - not too hard, not to quick to solve, easily solved in different languages and operating systems and yet, most indefinably, _interesting_.

To my increasing sadness, the author Mike Taylor hasn't posted another [since May 2010](ttp://reprog.wordpress.com/2010/05/19/another-challenge-can-you-write-a-correct-selection-sort/). There are more in [Jon Bently](http://www.amazon.com/Programming-Pearls-2nd-Jon-Bentley/dp/0201657880/ref=sr_1_1?ie=UTF8&qid=1296863348&sr=8-1) and I've solved a few, but I'm a lot more likely to be interested when it's online. Laziness, impatience and hubris, yep.

With that as background, you will better understand why I was so pleased to [find this one](http://careers.joelonsoftware.com/jobs/9924/most-world-changing-web-engineer-position-causes).  (I keep an eye on the job boards, it's a good way to see what skills are in demand.) Here's the problem description:


> Two words are friends if they have a Levenshtein distance of 1. That is, you can add, remove, or substitute exactly one letter in word X to create word Y. A word’s social network consists of all of its friends, plus all of their friends, and all of their friends’ friends, and so on. Write a program to tell us how big the social network for the word “causes” is, using this word list:
github.com/causes/puzzles/raw/master/word_friends/word.list


The job posting is [here](http://careers.joelonsoftware.com/jobs/9924/most-world-changing-web-engineer-position-causes), BTW.

So. My weapon of choice these days is Python, and I start noodling around. First thing, I [created a gist on github](https://gist.github.com/799075); I _love_ those. Once I'd read the problem a bit, I arbitrarily decided that 'Levenshtein distance computation is boring' and [found one on PyPi](http://pypi.python.org/pypi/python-Levenshtein/0.10.2) instead of writing it myself.

The wordlist, downloaded, is about 250,000 words. A good chunk, but easily read in milliseconds. Like I said, the problem has to be the right size, and this one is.

**Stop reading now if you want to solve it yourself! **

If you read the description closely, it's not clear if they want the height of the tree or the number of nodes in it; I think the number but either is easy once you're done.

I initially [created a Vertex class](https://gist.github.com/799075/f1b307e59394c4413244027ac130c03ad6d07c14#file_causes.py), but that turned out to be needless - all you need is a 2-D array, where each row is a layer in the tree. Row 0 is the seed word, 'causes', and every word in row 1 is distance 1 from 'causes'. Repeat, iterating over rows, until you run out of data. Here's pseudocode, simplified a bit:

    
        tree = [[]]
        seen_list = [seed_word]
        # Seed it with the root
        tree[0].append(seed_word)
        cur_depth = 0
        # Add the next layer for build_layer to populate
        tree.append([])
    
        # Run the first pass
        friends_added = build_layer(tree, cur_depth, wordlist, seen_list)
        total_nodes = friends_added
    
        # Now we repeat until no more friends are found
        while friends_added > 0:
            cur_depth = cur_depth + 1
            tree.append([])
            log.info('Starting depth %d' % cur_depth)
            friends_added = build_layer(tree, cur_depth, wordlist, seen_list)
            total_nodes = total_nodes + friends_added


Brute force indeed. If you think about it, you have to compute the distance from each word to each other word... O(n^2) or worse. To verify it, I finally learned the Python profiler:

    
    import cProfile
    ...
    cProfile.run('main()')


which spits out some very nice stats and also confirms O(n^2) it is indeed. So the code works, there are **78482 friends** in the list. (The code is O(n) on memory, interestingly, and could be made more efficient by discarding old rows after they pass.)

But it takes hours even on [my new laptop](http://fnord.phfactor.net/2010/12/16/more-amazing-times/). Larger graphs would rapidly become impossible.

I showed [Chris](http://www.phfactor.net/hurlburt/) the problem, and that was the end of spare time for a week or so. Evenings, we worked on it together on my laptop, and she ended up totally kicking my ass. On the same machine, my code takes **14,456 CPU seconds**. [Hers](https://gist.github.com/799075/#file_causes.py)? **3958**. Probably close to O(nlogn). Damn!

Clever bits:



	
  * Build the entire tree, which is well under half a second

	
  * Notice that, if a word is distance-3 away, there's no point looking for it before the third layer.

	
  * Also track connected but not used words.


Here's the code:

    
    def create_distance_dict(seed, wordlist):
        """
        Returns a dictionary whose keys are the levenstein distance from
        seed and whose values are a list of things from wordlist whose
        levenstein distance is 1
        """
        word_dict = {}
        for word in wordlist:
            d = distance(seed,word)
            if d in word_dict.keys():
                word_dict[d].append(word)
            else:
                word_dict[d]=[word]
        return word_dict
    
    def tree_checker(seed,wordlist):
        """
        This takes a wordlist and returns an array of arrays
        where the ith array consists of all things on wordlist
        of levenstein distance i from the seed and levenstein
        distance 1 from something in the i-1 array.
    
        Note:  The one requires that the seed be in the list.
        """
        lev = create_distance_dict(seed,wordlist)
        log.debug('Distance dictionary created')
        tree = [[seed]]
        connected_not_used = []
        connected_not_used_skip = []
        key = 0
        while len(tree[key])>0:
            key = key + 1
            log.debug('Working on level %d' % key)
            next_level = []
            next_connected = []
            next_skip = []
            if key in lev:
                connected_not_used.extend(lev[key])
            for word in connected_not_used:
                min_dist = 100  #Bigger than max tree depth
                for prior in tree[key - 1]:
                    dist = distance(word,prior)
                    if dist < min_dist:
                         min_dist = dist
                    if dist == 1:
                         next_level.append(word)
                         break
                 if min_dist == 2:
                     next_connected.append(word)
                 elif min_dist > 2:
                    next_skip.append(word)
            next_connected.extend(connected_not_used_skip)
    
            connected_not_used = [x for x in next_connected]
            connected_not_used_skip = [x for x in next_skip]
            tree.append(next_level)
    
        return tree


While it's humbling to have your mathematician better half pwn me like this, I'm pleased to have a partner with whom I can hack Python tree puzzles. Life is good, and so is this puzzle.

My thanks to [Causes](http://www.causes.com/) for a really interesting problem! Our code is [here on github](https://gist.github.com/799075/).

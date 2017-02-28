---
layout: post
title: "Why I Unfollowed Everyone on Twitter"
summary: "I unfollowed everyone (~4,500 people) on Twitter. Here's why I'd do such an insane thing."
comments: true
---

Back in January, I unfollowed everyone on Twitter. At the time, I was following 4,500 or so people. After slowly attempting to unfollow people from whom I didn't get much value (spammers, people only pimping their shit, etc), I got frustrated at the pace at which I was clearing things up, and nuked the whole batch. All the way to zero, including my wife, family and close friends. 

What on earth would possess me to do something so rash?

## My Love Affair With Twitter

I love Twitter. I've been a user for just about a decade now (typing that sounds crazy), and through my years, I've always been pretty active. I credit Twitter for helping me [start my user experience][madera] [design practice][fcp] and connecting me with people who've turned out to be some of my closest friends (there was that time six years ago that [Josh][joshtronic] immediately DM'd me when I followed him to ask why in the hell I was following him. We still chat daily.)

As much as I love Twitter, over the years, things had gotten out of hand. I followed people promisciously, offering up a follow to anyone who had any degree of interest or connection to me, thinking that Twitter would be a great way to stay closer in touch with them and stay attuned to their thinking.

That worked. For awhile. 

## Death By A Thousand Follows

As I began to follow more and more people, the timeline got crowded. Ironically, the people providing the least value (hammering the timeline with irrelevant blog posts, new stories and promos) began to dominate the feed, drowning out the people who I actually wanted to hear from. While I could selectively unfollow those folks as I saw them, I wasn't making any headway. My timeline had become useless. 

The very reason I started to use Twitter - to follow people and connect with them - became the very thing that Twitter no longer was able to deliver on for me. After a few weeks of trying to cull things down by hand, I got fed up, Googled how to unfollow everybody, and got ready to hit the nuke button. 

## How To Unfollow Everyone

As it turns out, Twitter doesn't make unfollowing everyone easy. Makes sense. You need to resort to some more creative tactics, in order to get the job done. I [found an article][techygeeks] that showed me how to get this done. The long and short of it is that you need to go to the page on Twitter that [shows everyone you're following][twitterfollowing], and use a snippet of code in the Developer Tools console to programmatically work through the list and click the "unfollow" button for you. The code that [TechyGeeks][techygeeks] published looks like this:

~~~
i=0;   
 setInterval(function(){t=$(".js-follow-btn").eq(i);  
 if(!t[0])window.scrollTo(0,$(document).height());  
 else t.trigger("click")  
 i++;},1000)
~~~

Basically, paste that into your console while on [your following page][twitterfollowing] and voila', behold the destruction. (Note that I tried to speed this process up by changing the timeout interval - the "1000" in the last bit of that code that represents how many milliseconds the script will wait between tries - and I got hit with throttling errors by the Twitter api. Stick with 1000, keep your browser window open, and make a drink. You'll be here awhile.)

![unfollowing all my peeps][unfollowgif]

## Building The List Back Up

As of today, [I follow just 7 people][jwd2a], including one person who I don't want to follow, but in some strange turn of events, could never _unfollow_ in the first place. I'm starting to slowly build the list back up now, but keeping a very keen eye on assuring that I'm following the right people, and putting together a mix that allows me to better connect with folks. I'm not sure what the ideal number of followers is. 100? 200? 500? Either way, I'm starting to build that list back up, and I'm hopeful it'll allow me to get back to the valuable connections and conversations that got me to use Twitter in the first place. 

Hope this inspires you to do the same!

[jwd2a]: https://twitter.com/jwd2a
[joshtronic]: https://twitter.com/joshtronic
[madera]: http://maderalabs.com
[fcp]: http://firstchairpartners.com
[techygeeks]: http://blog.techygeekshome.info/2016/07/how-to-mass-unfollow-everyone-on-twitter/
[twitterfollowing]: https://twitter.com/following
[unfollowgif]: https://dl.dropbox.com/s/w7u41libn0aa6z2/unfollow.gif

---
layout: post
title: "If You Don't Have a Feedback System, It's Not Agile"
summary: "Everyone loves to throw around the 'agile' word, when talking about how they approach development. But, who's actually doing it, and who's just pretending?"
comments: true
---

I work with a lot of different software development teams, and when I ask about how they work, "agile" is often the first response. The same goes for the tech startups that I work with. "Yeah, we're definitely agile!" is the refrain I hear all the time. The problem is, the word "agile" is bandied about far more often that it should be, with teams really not understanding what it means to "be agile", and do Agile software development. 

A lot has been written about agile methodologies, and what the process looks like, from [Scrum][scrum] to [XP][xp]. I'm not terribly concerned with rehashing that process. What I'm concerned about is how lacking a core piece of the agile philosophy is among most teams. That piece is feedback.

Backing up, let's think about what the point of agile is. As opposed to a waterfall approach, agile promises to get things out in the world more quickly, so you can adjust and deliver a more appropriate product to users. It's about tight iteration loops and speed-to-market, and it works extraordinarily well when done correctly. The key, however, to this working well is *learning from the market and adjusting*. Without learning and responding to it, you're merely pushing shit out the window at a faster rate. I'm all about faster shipping, but without knowing what's working, you're basically shooting with a blindfold on. 

So, what kind of feedback are we talking about? In my mind, there are two types of feedback mechanisms you should be thinking about with every single ship: quantitative (reading the data), and qualitative (talking to people). Let's take a fictional scenario to see how these work out in the course of shipping something:

Let's say you're Acme, Inc., and you have a SaaS product that allows people to submit timesheets (the canonacal boring example of web tech, for whatever reason). You release you product, that allows people to submit their timesheets, albeit, a bit manually. A few weeks later, in a product meeting (read: conversation with someone over coffee), you think it'd be nice to let people either manually enter the name of the task their tracking, or select from some items they've previously tracked, to make things a bit easy. You're agile, so you get it into development, and kick it out the door to users.

So, did it work? Is it helping?

This is where most people stop. They kick the feature out the door, think "Oh, man, people will SURELY love this!", and move on. But, what if it's not quite right? What if your users are now getting confused: do they have to select from the list, or can they also enter new ones? Can they manage this list somewhere? Do they expect to see items in this list from other team members? What about that thing they tracked once, a year ago - why isn't it showing up in the list?

Here's where the feedback loop helps. First, we can measure quantitatively: how many people are selecting from the list vs. manual entry? Is the time it takes someone to log a task decreasing, or increasing? Is total engagement with the product decreasing, or increasing? This is data that can be identified and tracked easily, with some fairly rudamentary behavioral analytics. Those numbers, then, can start to tell a story: "Interesting, after we released this, it seems like people are tracking more, but it's taking them longer to complete each entry" That, then, forms the basis of your qualitative approach. 

Next up, is to talk to users and *find out what the hell they actually think*. So few people do this, it borders on irresponsible. Now that we've seen what the data says about this change, let's come up with a few questions to ask them to add color to the story. Email your list, offer them $25 for 20 minutes of their time (or whatever's appropriate for your vertical), and start to dig in. Did they notice the new completion options? Are they using them, or not? What about it is confusing? Does this feel helpful, or not? There are about a million things you can ask here, in order to add some color to what you're seeing in the data, and it doesn't need to be an elaborate setup to do it. You can set this kind of thing up inside of a couple hours, if you've got a fairly engaged user base who's willing to jump on the phone with you.

Now that you have this information, you're ready to use it for the next iteration. Turns out that people didn't see things quite as they expected? Make a modification, ship it, and watch the data again. Did things change? Did users incidate that it's better or worse? Take the information, feed it back into the next iteration, and so on, until you've got it right.

That's being agile. Agile isn't about just being fast. Fast is great, and is one of the more enviable traits of a software team, but it's not the end of the story. Being fast and ineffective isn't helpful. Make sure you're building these feedback loops in, and intentionally paying attention to them, so you'll know what's working, and what isn't. 

It constantly blows my mind how basic peoples' understanding of this is. If you redesign a page on your site, how did affect your basic metrics - time on page, bounce, etc? If you redesign your signup page, how did it affect conversion rates? If you add a new feature, what percentage of your users are using it? As someone running any kind of product, this kind of baseline data is absolutely required to say you're doing your job well. Otherwise, you're just shipping blindfolded, and at best, flipping a coin. 

If you don't have this feedback loop in place today, stop and go get it in there. Use [Google Analytics][ga] and set up conversion funnels and event tracking. Start querying your own database for usage information and kicking out some basic reports on the regular. Start calling and emailing users and asking them how things are going (NOT SELLING NEW SHIT TO THEM). I can promise you, once you've got this loop closed, you'll never go back. And, you'll finally be doing real Agile development. 

[scrum]: https://en.wikipedia.org/wiki/Scrum_(software_development)
[xp]: https://en.wikipedia.org/wiki/Extreme_programming
[ga]: http://google.com/analytics

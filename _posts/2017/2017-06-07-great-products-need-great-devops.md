---
layout: post
title: "Great Products Need Great DevOps"
summary: "In the quest for shipping great products, DevOps is often overlooked, and that's a mistake"
comment: true
---

The two most important factors that lead to better products are [shipping][shippost] and incorporating customer feedback. While you're waxing poetic about which backend framework you should use, or trying to figure out which sexy design pattern you're going to use, you're missing out on one of the most important factors of product development. Fact is, the faster you're able to get product to market, gather feedback, iterate, and get it back out, the better chance you have at success. If you think you've got your product right on the first go, and this doesn't apply to you, you're sorely mistaken. 

This ability to ship is directly affected by the strength of your DevOps game, and if you're struggling in that department, it's probably worth stopping everything and getting up to snuff. 

For those new to the concept, DevOps is the merger of _development_ and _operations_, essentially, where development meets IT and infrastructure. DevOps covers a lot, including scaling (which almost all of you don't need to worry about), but one of the most important aspects of the DevOps picture is the deployment pipeline - e.g., how you ship.

How you get code from a developer's laptop (whether that's you or someone else) to the waiting public is something that you need to examine constantly, and do whatever you can to make it better. At the end of the day, you have two goals: make it faster, and make it more stable. 

## Why This Matters

So what? You're happy with dragging your code into your FTP client, or rsync'ing it to your server every few weeks or so. What's the problem? The problem is, the rest of the world is kicking your ass when it comes to shipping code. In [their latest report on the state of DevOps][report], [Puppet][puppet] noted that the best-in-class companies are shipping code to production _multiple times a day_. The medium and low performers are shipping once a week, or worse, once a month. 

Here inlines the problem. When you ship code daily, your iteration cycles are _tight_. Ship code, get feedback that day, ship modifications tomorrow. When you ship once a week, or once a month, you're delaying that loop. Every completion of the ship-iterate-ship cycle is an incremental step toward better product/market fit, which means more customers. When you slow down the loop, _everything else in the business slows down_: sales, product development, marketing....everything.

## How We Do It

So, what do faster shipping cycles look like, and how are they supported by DevOps? The most backstage look I can give you is a [product I'm working on][cs] with my buddy [Josh][josh] and a couple other talented dudes. Josh (aka, DevOps Jesus) has set up an amazing framework to make getting code deployed as easy as possible. Here's a few things we do to get code out the door faster:

- *Work in Master*: We rarely work in branches. Occasionally we do, but for no longer than a few hours. Almost everything is merged into master and shipped to the repo on a daily basis. No long-lived branches. This means that code is ready for production all the time, not hung up in branches for weeks.
- *Ship from Slack*: DevOps Jesus built a Slackbot for us that allows us to deploy any part of the application to product, right from slack:

![shipping from slack][bender]

Not only can we ship any part of the application from Slack, but we can also ask for the `shipstats`, which keeps a friendly competition amongst who's shipping to production more often. Ingrained in the culture is a drive to get things out the door, and we use the bot to help cultivate that.
- *Smaller, independent components*: Our codebase is broken into 5 discreet services: `www` (the website), `api` (the API that serves as the backend entry point), `app` (the Angular frontend), `admin` (the admin side of the api) and `assets` (CSS, images, etc). This allows us to ship from smaller components, instead of needing to test and ship the entire thing every time. 

Putting this framework and architecture together took maybe a week and a half or so, very part-time. It's not about being overly sophisticated, it's about architecting and engineering things to make sure you can get code off your laptop and into the world as quickly as possible.

## Don't Overlook DevOps

When we build products, we often focus on two sides of the product development coin: development and design. However, if that's all you're thinking about, you're missing a critical component. DevOps is incredibly important, and is often the key to ensuring you can get product out the door and iterate faster, which ultimate leads to better product. If you don't have that competency today, go find it or learn it, trust me. 

If you want to read a phenomenal book on this, check out [The Phoenix Project][phoenix] - it's written as a novel about real-life DevOps situations, and is a fantastic "case study" of a large organization that radically changes how they get product out the door. 

[shippost]: http://justindavis.co/2014/11/24/just-ship/
[report]: https://puppet.com/resources/whitepaper/state-of-devops-report
[puppet]: https://puppet.com
[cs]: http://www.crowdsync.io
[josh]: http://joshtronic.com
[bender]: https://dl.dropbox.com/s/h0kaqgn688cmoze/shippingbender.gif
[phoenix]: http://amzn.to/2r5TIjL

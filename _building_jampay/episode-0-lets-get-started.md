---
title: "Let's Get Started"
comments: true
episode: 0
---

I'm launching something new, and I want you to follow along.

The new thing is called [JamPay][jampay], a site that helps live musicians get paid more by allowing the crowd to tip them via credit card instantly. This is an idea that hit me in October of 2015 as I was walking around Boston, seeing great musicians playing on the street, trying to eek out a living doing so. Since then, I've been slowly putting things together, and we're getting close to launch.

The vision is straightforward: I want to change the way musicians get paid, allow them to make more from each live performance, and create a more sustainable career out of being a live performer.

Now that things are close to launch, I thought it'd be interesting - and enlightening - to chronicle the start of JamPay week-by-week, and that's what you're reading now.

Starting this week, I'll be breaking down what I'm working on, what steps I'm taking to make JamPay work, and the failures and - hopefully - successes along the way.

## Why Do This?

Starting something is hard. It's lonely at times, and you can definitely get into a situation where you're into dangerous echo chamber territory. I want to break out of that cycle by giving a weekly play-by-play on how JamPay works, what I'm doing to bring it into the world, what challenges I'm up against, and how I'm trying to solve them. For me, it's about accountability and helping to generate ideas on different approaches for making this work. Hopefully for you, it'll be fun to read.

## What You Can Expect

This isn't going to be overly formal, it's probably going to be poorly written, and it'll most definitely be a pretty seat-of-the-pants account of things. That said, here's what you can expect to read from this every week:

- What I did this week to move progress along
- What challenges I'm looking at
- What I want to get done this week
- All the other bullshit that comes from starting and lauching something

One thing I can **absolutely promise** is this: I'll be completely - sometimes dangerously - transparent. I'll be sharing numbers (including revenue), marketing strategies, everything. We learn better when we see what others are doing to tune the engine on something, and if JamPay does nothing else, at least it can serve to help other learn about the mechanics of what goes into launching these things.

## Where We Are Today

Alright, let's get into the more interesting stuff. Where is JamPay today, and what's the makeup of this thing look like?

I've been working on the site, roughly, since early November 2015. I went hard for a few weeks, then ran into an issue where I thought I couldn't do this, because I'd be classified as a [money transmitter][money] (based on the fact I'm taking money from audience members and moving it over to artists). Fast forward a few months, and I found out that [Stripe][stripe] actually lets me do this really easily, while taking out a commission for JamPay automatically.

I found that out sometime around January/February of this year, and it reignited my interest and passion for solving the problem. So, I kicked the dust off the repo, and went about the business of getting things finished up.

Today, I'm dangerously close. The basic site [is up][jampay], but I still need to do polish on signup/login, as well as some error handling and general stability/QA stuff. My goal is to have this stuff mostly done by the first week of May 2016, and I'll start pulling some users on the platform to actually use it for real.

## How This Is Being Built

Let's chat for a second about how I'm putting this together. I'm fortunate, in that I have a fairly good set of skills that lets me put this together. I'm [a user experience designer][firstchair], which means I know how to design a product experience that's easy-to-use and pleasurable. Big hurdle passed. Additionally, I'm a developer, which means I have the technical skills to get things built. Awesome.

What I'm _not_, however, is a visual designer. I suck at it. So, I've hired some folks in Serbia (via Upwork) to take my wireframes and create designs from them. They've done a great job. I'm currently having them get the logo nailed down as well.

Between those pieces, I've got what I need to get this thing out into the world.

From a tech perspective, here's how things line up. The app is built on AngularJS, running a Node/Mongo backend. The front uses Bootstrap (of course), and it's all hosted in a Docker container sitting on a Digital Ocean box.

(BTW, I love Digital Ocean, you [should try them out][do]. Sign up with that link and get a $10 credit - two free months!)

## What's next

In the next installment, we'll get caught up with what's happened over the past week, including what I consider the most important part of launching a product: getting product/market fit dialed in. Look for that coming soon!

[jampay]: http://jampay.com?utm_source=building-jampay
[money]: https://en.wikipedia.org/wiki/Money_transmitter
[stripe]: http://stripe.com
[firstchair]: http://firstchairpartners.com
[do]: https://m.do.co/c/c0c980996086

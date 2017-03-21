---
layout: post
title: "Everyone In a Startup Should Have This Skill"
summary: "You know you need technical skills to build the product, and sales skills to sell it, but does your team have this critical skill?"
comments: true
---

This is going to come as a shock. Everyone in a startup - especially in the early days, and definitely in leadership positions - needs to be able to openly query the database at any time, for anything. 

(I'll wait for the gnashing of teeth to stop.)

Here's the deal. At any given time in a startup, you're going to have about a million questions:

- "Are users using that feature?"
- "For that last campaign we ran, did it affect engagement on that particular page?"
- "How many items are users uploading on average?"
- "Is that upsell path working? For what kinds of users?"

And so on. Every day, you're coming up with a new question that's almost always borne out of business requirements, marketing requirements, or product questions. Questions that you _do_ have the ability to answer...with the right data. 

## SaaS Startups Have Data DNA

In the past few months, I've been appalled at how many startups I've worked with where they couldn't answer basic questions. Not only did they not understand the basics - like conversion rates, churn and LTV - but we were unable to get access to answers to basic questions about feature usage, frequency of use and nature of use. In an environment where speed is absolutely key, and access to information for making better decisions is one of the best assets you have, this is unacceptable.  

If you're running a dry cleaners, the story might be different. You might not know how many men's shirts come in the door, unless you have a system for tracking that inventory. But, with a SaaS or other techincal product, there's no excuse. _Every single action a user takes, everything they do that's important, is in a database somewhere_. You just need to get access to it. 

## Shut up and SQL

In the breakneck world of technical startups, speed and agility is keep. The faster you can get information, the faster you can win, period. That's why everyone in the organization should have access to, and the ability to query, all your databases that contain any user information (ensuring you're respecting your local privacy and HIIPA laws where necessary). This means that everyone should be able to write basic queries to be able to answer their questions, instead of waiting on some IT donk gatekeeper to reluctantly agree to the request.

Don't let your important business decision making power be locked up behind a guy with a database power complex. Democratize access to important business data as much as possible. 

## Can't IT Just Do This?

Sure, if you want everything to take forever. Just kidding, not a knock on IT, but it's still true. IT's busy doing a lot - keeping things humming along, developing new features, fixing bugs. When you leave a meeting with a key question, do you want to wait a few days to get in their queue, or just head back to your office, fire off a quick query, get your information and move on? Thought so.

## How To Start

So, how do you start to do this? Chances are, for most people reading this who aren't the devs in charge of the databases, you don't know thing one about where the database is and how to use it. Totally natural, totally normal. 

First up, figure out what you're dealing with. A friendly talk with your database guy or gal should answer basic questions, like what kind of database (MySQL, Oracle, Postgres, MongoDB?) you're dealing with, and how you connect to it (just ask about how to access it, they'll mutter things about connection strings. Take them to your desk and have them help you get set up).

Next, learn what you're doing. Take a glance at [some presentations about SQL for marketers][slideshare] (SQL is just an acronym for "Structured Query Language", and fancy phrase for "how to get what you want out of the database"), or hit up some [courses to really dig in][treehouse]. You might even get your IT folks to do a workshop for the rest of the company, to help you get up to speed. However you get the knowledge, just make sure you get hip to how it works. 

## WHOA. ACCESS TO THE DATABASE?!

Alright, at this point, someone is flipping out about the fact that the VP of Marketing is going to have access to a live database. I get it. For those in charge of maintaining the security of things, get what you need in place before you allow access. Using GRANTS in MySQL and similar methods elsewhere can help lock things down a bit, to ensure folks don't go dropping whole databates of user records, or messing with foriegn keys. 

An even better (if heavier) solution is to simply do a copy of your key databases nightly (which you're already doing...right?) and allow access to those, instead of the live data. Data delayed by a day is better than nothing, and you eliminate the risk of someone monkeying around with your production boxes. 

However you're comfortable, get it set up. This will vary depending on your culture, environment, and thickness of the tin foil you've got on your head. 

## These Are the New Skills

Underlying all this is a key thing that everyone in a tech company needs to understand: the skills you need to succeed in tech are different than they are for other places. You're running a data-driven business. Understanding how to access that data to help make better business decisions is absolutely a core skill that you need. Is it work? Yup. Is it a bit overwhelming when you start? Yup. Welcome to the challenges of actually running a high-performing business. It's not all pizza parties and hammocks. 

## Do Dashboards Solve This?

In short, no. Dashboards are fine, and you should have dashboards for _key metrics_ that drive the high-level strategy of the business. That said, there are way too many times when nuanced understanding of data is required to make decisions, on a case-by-case basis. You'll never identify those when you build your dashboards, and this data isn't something that should be persisted at such a high level anyway. The ability to query databases ad-hoc, alongside dashboards for high-level, persistent metrics, is the key to a healthy, data-driven startup.

If there's any one deficiency I've noticed recently in many of the startups I've worked with, it's that they don't have access to the information they need to make critical business decisions. Don't fall into that trap. Give everyone in the organization the power of that data at their fingertips, and watch the quality of decision-making go up very quickly. 

[slideshare]: https://www.slideshare.net/jwmares/sql-for-marketers-slideshare-v1
[treehouse]: https://teamtreehouse.com/library/sql-basics


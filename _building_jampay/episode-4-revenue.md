---
title: "Revenue!"
category: buildingJampay
comments: true
episode: 4
---

(Did you miss the first episodes of this series - Check out [episode 0][ep0],  [episode 1][ep1], [episode 2][ep2] and [episode 3][ep3]. Much better way to explore all these coming soon, I promise.)

This week saw a milestone I wasn't expecting: revenue! That's right - the first tips were processed through [JamPay][jampay], just a few days after our first users. Needless to say, I was pretty stoked.

In this episode, we'll talk about that revenue, the challenges with it, some much needed cleanup on the app, a mostly failed pitch and marketing for the next week. Let's go!

## Making Money

Late last Wednesday night, I got an email from Stripe saying $20 had been deposited into my account. To be honest, I was initially pretty confused. I have an account on [JamPay][jampay] myself, for testing, but certainly no one was tipping on that account. Turns out - the email was notifying me that one of my connected accounts (accounts I set up on behalf of users) had received money - our first actual revenue!

I was shocked. If you remember from the [last episode][ep3], we had just gotten our first real users. One of them was noticeably persistent - working around all the bugs to get their account set up. Not hours after I'd sent this user an email saying we'd fixed up a bug where other users couldn't view their profile (ouch), a payment came through. Wow.

## Breaking Down the Revenue

Let's chat about how money is actually made on JamPay for a second.  For each transaction, we charge a flat 15%, which seems a bit high, until you break down the math. Here's how that looks.

For a $5 tip, we take $.75, leaving the artist with $4.25. Out of that $.75, we have to pay Stripe, which is $.30 + 2.9%, or $.45 total, leaving us with a grand total of $.30 that we make. Not huge margins.

As tips get larger, our take gets larger, based on the fact a big chunk of the Stripe fee is a fixed cost, not a percentage.

So, for the $20 tip that was processed (the maximum that JamPay allows), the math breaks down like this:

> $20 * .15 == $3 fee from JamPay, $17 back to the artist
>
> $3 - ($.30 + $.58) = $2.12 net to JamPay

As you can see, we make much more money the larger the tip. That said, my expectation is that most tips are going to be down in the $5 range, leaving us a pretty small take on each transaction.

Regardless of our take, we're helping the musicians make a lot more money than they'd otherwise make, a real win-win.

## Break Even Analysis

If you're paying attention, you'd notice that because of the flat fee that Stripe charges, there is a possibility that we could _lose_ money on a transaction. This would suck. So, instead of inviting that possibility, we've set the minimum tip at $5, to avoid any possibility of loss.

Why $5? Because of the break even analysis per tip.

Math time again! Our break even is $2.47. With a tip of that amount, we take $.37, and the stripe fee is $.30 + $.07, leaving us with exactly $0.

We could do a $3 minimum in the app, but that's only leave us with $.07 per transaction, which is quite low. By setting the minimum at $5, the hope is that we hit the sweet spot between low enough to drive volume, but high enough to keep sane margins per transaction. We'll see. If feedback overwhelmingly suggests that $5 is too high a minimum, we'll look at dropping close to $3.

## Declines and Error Handling, Ick

When I set JamPay live a few weeks ago, I honestly didn't expect anything to happen. I didn't expect users to sign up, and I sure didn't expect to have tips processed so quickly. Turns out, I was wrong. Awesome.

The problem with these assumptions is that I strategically didn't build out some parts of the app completely, just to get the thing out the door. Specifically, I didn't think about, or design for, a case where credit cards are declined.

Then it happened.

Just a few days after that first tip came through, the same user had two more charges. Both for $20, and both were declined by Stripe. I'm unsure why that's the case, but regardless, they were declined (Stripe doesn't always give reasons for a decline, which was the case for these transactions).

Declined credit cards are a way of life, I just didn't expect them to rear their head so early in the lifecycle. The problem with declines is that they require logic to handle and communicate them - logic I hadn't yet built into the app.

Long story short, I spent a chunk of the week building in that error handling and messaging, to ensure future declines are handled more gracefully. I also instituted a weekly account status email to help provide more clarity on an artist's tips each week (more on that in a second).

Here's the lesson: you're going to have errors, and you'll have to handle them gracefully. You won't hit them all in your first pass, but keep a keen eye out for what's happening in the app so you can design to support those cases quickly after they come up.

## Weekly Account Email == Engagement (I hope)

As mentioned, I put together a weekly account status email to help keep users up to date with their activity over the past week. I took inspiration from a weekly email I get from [SumoMe][sumo] that looks like this:

![sumome email](https://dl.dropbox.com/s/i31l7z216m5sl7v/Screenshot%202016-06-01%2012.58.20.png?dl=0)

What I love about this email is the comparison to the week before. It keeps me engaged, and wanting to keep performing every week. So, I put together an uglier version of this to keep users apprised of their weekly performance:

![jampay email](https://dl.dropbox.com/s/jagndtzjhqedwa8/Screenshot%202016-06-01%2011.45.58.png?dl=0)

This gives users a quick rundown of their tips for the week, with a comparison to last week, in addition to providing them with a glance at the payments, so they'll know if some have been declined.

There's another reason for doing this as well: engagement. My hope is that a weekly email like this provides motivation to continue using JamPay, and is a weekly reminder that they need to be using the service to make more money when they play live.

The first round of these emails goes out next week, we'll see how it plays out.

## Sales Pitches (Suck)

I'm not a great salesperson, I'm just not. I _want_ to be, but have never had the natural knack for it that someone like [Gary Vee][garyv] might have.

So, what do you do when you're bad at something? You practice.

Last Friday, I was out having drinks with some family who were in for Memorial Day weekend. We were hanging out [at a local waterfront bar][jackwillies], and there was a band that was setting up as we were having drinks. Seeing the opportunity to practice the pitch, I went up to them and pitched JamPay.

It was...terrible.

Pretty shitty pitch. I stumbled through it, feeling a bit desperate and out of sorts. As I pitched it to them, there was mild interest, which quickly turned into active ignoring of me. Chalk that one up as a failure.

That said, there was a bright side. Some of their questions helped me to understand where things might not be as clear as they need to be. One question was "So, how do people know where to go to tip you?". My answer was something along the lines of "Oh, it's like your Twitter account [blank stares], er...Facebook account. You tell people how to find you." Clearly, I need to get better at helping folks understand this part of the experience, as I've had the same question a few times.

I'll keep doing this, just to get better at it. The good news is, there are musicians playing at nearly every bar here in Tampa, which provides ample opportunities for practice. Always be selling!

## Marketing Continues

This week, more marketing continues. Now that I've patched up a bunch of bugs and generally cleaned up the platform more, I feel better about throwing people on it. A few things I'll be trying this week include:

- Twitter follow, retweet and liking campaign: following, liking and retweeting key targets, in hope that I'll get some interest.
- Direct outreach to bands with email or message: finding folks that look like they're a good fit, and directly reaching out to them personally.
- Email my signup list: remember that list of folks I got from [BetaList][betalist]? I'll be hitting that list up to get them on the platform as well.

One other thing I'll be doing is a handbill campaign. Because my targets are musicians taking tips, it means they each have a tip jar when they're playing live. That tip jar is like an inbox for my marketing material, and I plan on using it as such. I've had 500 handbills printed (2.5" x 2.5" square cardstock pieces), that look like this:

Front side:

![jampay handbill front](https://dl.dropbox.com/s/lkoz8dmyhwingdk/Screenshot%202016-06-01%2013.10.59.png?dl=0)

Back side:

![jampay handbill back](https://dl.dropbox.com/s/r89csbmckuojs5a/Screenshot%202016-06-01%2013.11.39.png?dl=0)

The plan is to take these, stick a post it note on it with a handwritten (albeit canned) message, saying something like "Loved the set! You should check this out!", and paperclip a dollar to it. I'll drop those in the tip jar, so they're processed at the end of the night with the rest of the money. Because they're small, they're easily shoved in a pocket or wallet for later reference, unlike a 4x6 postcard which would most likely be immediately thrown away.

That's the plan! I was able to print 500 of these for just $30 at [Club Flyers][clubflyers], one of my favorite printers. If I can get a user to convert from this, my Customer Acquisition Cost is just $1.06 - not bad at all. When these come in next week, I'll snap a photo of the final product and include it in the next installment.

That's a wrap for this week. A lot going on, and a lot to do as I move into the first month of really ramping up the first users on the platform.

Don't miss next week! Make sure to sign up for the weekly email of this post at the top of the screen, so you don't miss an episode!



[jampay]: http://jampay.com?utm_source=building-jampay
[ep0]: http://justindavis.co/building-jampay/episode-0-lets-get-started.html
[ep1]: http://justindavis.co/building-jampay/episode-1-names-logos-and-other-branding-bullshit
[ep2]: http://justindavis.co/building-jampay/episode-2-validation-ssl-and-shipping
[ep3]: http://justindavis.co/building-jampay/episode-3-first-real-users
[clubflyers]: http://clubflyers.com
[garyv]: https://twitter.com/garyvee
[jackwillies]: http://www.jackwilliesbarandgrill.com/
[sumo]: http://sumome.com
[betalist]: https://betalist.com/startups/jampay

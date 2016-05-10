---
title: "Validation, SSL and Shipping"
category: buildingJampay
comments: true
episode: 2
---

(Did you miss the first episodes of this series - Check out [episode 0][ep0] and [episode 1][ep1]. Much better way to explore all these coming soon, I promise.)

The past week has been more grinding, getting dangerously close to this thing actually being out in the real world. The highlights are some early customer validation, a whole mess of SSL drama, and overcoming mental hangups about shipping. Let's dive in!

## Making Sure Customers Care

So, there's something I've learned over the years. When you come up with an idea for a thing, there's about a 100% chance people aren't going to give a shit. You might have an interesting take, an interesting stance, but it's likely you're missing some stuff that makes the product something that people are willing to pay for and use on a regular basis.

We're not all Steve Jobs. That's just life.

Steve Blank, in his seminal book [The Four Steps to the Epiphany][foursteps] (I can't recommend this book enough), calls this process "customer discovery", or, as he says: "finding out who the customer for your product are and whether the problem you believe you are solving is important to them". Having wasted time before on a product that didn't quite have product/market fit, I'm not keen to make that mistake again.

So, this past week was about starting that process. While I'm finishing up the app, I can go ahead and show it to folks, get their feedback, and work to make it something they love.

## Starting By Spamming

I wanted to get this off to a quick start, so I turned to a tried and true method: spam. The idea was that I'd find some local musicians that felt like they fit into my target, and email them looking for reactions. Based on that, I'd continue that conversation and work to understand what it is they actually want out of the product. Never assume, amirite?

I started by finding email addresses. To be honest, I just scraped these off musicians' websites locally. Some searching around, and some patience looking for emails in the raw on websites, and I put together a list. Well, actually, two lists.

I decided I'd send multiple batches of email, changing things like the subject line and copy to see if I could learn anything about what gets a response. I started scraping sites for email addresses, and put together lists of 10 email addresses each, hitting them with the following email:

![email](https://dl.dropbox.com/s/9lg7d13zovrwjzb/Screenshot%202016-05-10%2017.48.37.png?dl=0)

No styling, so it'd look more like it came from a person, not a mailing list. The idea behind the copy was to give them a simple thing to respond to - the two questions I list at the bottom.

I've sent this out to two lists so far:

![campaigns](https://dl.dropbox.com/s/nbphp1mjdbxprub/Screenshot%202016-05-10%2017.50.30.png?dl=0)

As you can see, the open rate really isn't that bad, but the response rate was abysmal. One guy emailed me back. He was pretty excited about the idea, and told me I need to think about how this can work for guests of a hotel to charge to their room. Interesting. Would have never thought of that if I hadn't talked to users. See how this works?

## Improving the Process

I'm going to continue working through the validation exercises, making two major changes: I'm going to modify the email copy, making it a bit shorter, to see if I can get folks into a conversation. I may even play with just pinging folks and saying, "Hey, you mind if I email you more details about a thing I'm making for musicians? I want to respect your time, but also would love your feedback", to see if that comes across more authentic and gets a higher response.

Additionally, I'm going to ramp up in-person validation as well. Emails are convenient to send out at 9pm, but they're not a great way to do true user research. The best research is done by talking to folks on the phone or in person, so I'll be heading out to clubs and venues and chatting with folks playing there about what I'm doing.

## More Validation: BetaList

Oh, speaking of validation, another stab at validation was to post the site to [BetaList][betalist], to see what kind of early signups I might get. It's a very poor proxy for actual user research and customer discovery, but it's _something_.

Just to bring you up to speed, BetaList is a site that allows pre-launch startups to post, in order to help build an email list before launch. They've got all kinds of restrictions: you can't be live, you can't use a template for your site, etc. Seemed legit.

So, I busted ass on that a few weeks ago, getting the site ready, building in a little email subscription flow to capture the hoards of excited traffic.

Addtionally, I forked out the $129 to expedite the posting, since I didn't want to leave this thing in limbo for a month. I figured, if I get a few hundred signups, I might get my CAC (Cost Acquisition Cost) down to a respectable amount, and it might be worth it. Besides - it's $129, cheap experiment.

Well, here's how it looks after about a month of traffic. Total traffic from BetaList:

![betalist](https://dl.dropbox.com/s/2wunqz8n7yymbxm/Screenshot%202016-05-10%2018.00.22.png?dl=0)

So, 166 visitors. Meh, not phenomenal. Bounce rate is high, but that's to be expected with single page that only has an email signup. Session duration - at 33 seconds - actually feels long to me. That could be good, or it could be bad. It's honestly impossible to say.

Even still, if 166 visitors signed up, and I converted them, we're at a CAC less than a buck. All things considered, that's cheap. Let's see how they converted to the mailing list:

![jampaylist](https://dl.dropbox.com/s/9imo4fg2h92zygm/Screenshot%202016-05-10%2018.05.03.png?dl=0)

Of these 12 people, 3 are friends and myself. So, 9 total, giving me a 5% conversion rate. Now, given, in many circumstances, a 5% conversion rate is actually decent. But, at a CAC of $14.30/user, it's hard to call this a wise marketing investment. (And truly, this isn't even accurate. The CAC is $14.30 if all 9 turned into users, which is unlikely, making the CAC that much higher.)

Lesson learned, next!

## Getting Secure: Easy, right?

[JamPay is basically a payments platform][jampay] - a mobile payments platform aimed at musicians in a live setting. When it comes down to it, that's the pitch.

As a payments platform, security is **ridiculously** important. I'm transmitting credit card information from a user's device to the server, it's got to be well secured.

Luckily, the internet makes this easy with SSL/TLS. SSL (Secure Socket Layer), and its successor TLS (Transport Layer Security) make sure things are nicely encrypted from the browser to the server, so no snooping folks can see the credit card numbers (or passwords) as they head to and fro.

To enable this, you just get a certificate, install it on the server, and you're off to the races after just a touch of server configuration. That's the easy route. Did I take the easy route? Hell no! I decided to create the certificate myself, using a new technology called [Let's Encrypt][le].

I'll spare you the technical details, but Let's Encrypt basically allows you to create and manage these certificates yourself, skipping the cost of buying the cert. Sounded like a great idea.

In reality, I spent nearly 4 days trying to get this thing to work to no avail. Finally, in the office last week, I was bitching to [a buddy of mine][stavros] about this, and he said "Dude, just go buy a cert from [Namecheap][namecheap] and be done with it. It's $9!".

$9. I spent 4 days trying to save nine fucking dollars.

15 minutes later, cert was purchased, installed, and server configured to use it. The lesson here? At the end of the day, the fastest path to market wins. Spend the money and focus your time on things that actually build your business, not new toys that are interesting but optional.

## Shipping Anxiety

As I write this, JamPay still isn't technically live. It all _does_ work. You can sign up, create a profile, get tips, and get those tips deposited into your account. So, why haven't I flipped the switch?

Because I don't like the design of the signup page.

This might be the stupidest reason to not ship of all time. After all, even if I make it live, no one is likely to sign up without a marketing effort anyway, what am I worried about?

The answer is, I'm making things up. This is shipping anxiety at its worst, and it's unacceptable. The fact is, getting something out in the world - flipping the switch - takes a LOT of mental toughness, but you have to get yourself better at doing it. The only way products make a difference is if people use them. Besides, so what if some folks sign up and something breaks, or they get confused for a moment? It's likely to only happen to 1-2 people before I can fix it in the next day or so.

So, with that, I'm off to ship. Tonight, I'm going to flip the switch and make it live. Fuck it, why not? What's the worst that can happen? Not much. The best thing? I wear down my shipping anxiety that much more, making me more apt to ship faster in the future.

Stay tuned to see what happens! Next week, we'll see where this goes. New logos are on the way, designs for signup/login are on the way, more validation with customers, and most importantly: this thing is going live. Don't miss an episode (and sign up for the email at the top of the screen)!


[jampay]: http://jampay.com?utm_source=building-jampay
[betalist]: http://betalist.com/startups/jampay\
[le]: http://letsencrypt.io
[stavros]: https://twitter.com/SteveLazaridis
[namecheap]: https://www.namecheap.com/?aff=100514
[foursteps]: http://amzn.to/1sbmSPJ
[ep0]: http://justindavis.co/building-jampay/episode-0-lets-get-started.html
[ep1]: http://justindavis.co/building-jampay/episode-1-names-logos-and-other-branding-bullshit

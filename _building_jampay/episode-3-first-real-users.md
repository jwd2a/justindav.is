---
title: "First Real Users!"
category: buildingJampay
comments: true
episode: 3
---

(Did you miss the first episodes of this series - Check out [episode 0][ep0],  [episode 1][ep1] and [episode 2][ep2]. Much better way to explore all these coming soon, I promise.)

Let's get two things out of the way: this blog post is a week late, and I haven't done much with [JamPay][jampay] over the past week, due to being one of the conductors on [StartupBus][sub] last week. That said, there are a few goodies to chat through.

## First Real Users!

As you likely remember from the [last episode][ep2], I said I was going to ship this thing and make it live. Up until then, I had the site up, but only with an email signup, which didn't bear much fruit. Always the one who'd rather ship than sit on something, I did what I said: I flipped the switch and made things live the day after I posted the last episode of this series.

If I recall correctly, I "launched" (if we're referring to making it possible for users to sign up) on Wednesday evening, May 11th. I'm writing this late afternoon on Tuesday, May 24th, nearly two weeks later.

In that time, how many users have signed up? Let's take a gander at the database, shall we?

![firstusers](https://dl.dropbox.com/s/8gsqlkygz3o37im/Screenshot%202016-05-24%2017.13.15.png?dl=0)

(I've blurred out email addresses of actual users to protect privacy, obviously.)

So, if you count, you'll see that - aside from my five test accounts - there are five users. Five users in two weeks. Pretty much might as well be zero. Two lessons to learn here:

- If you're afraid to ship because "people will see an unfinished product!", you're being chicken shit and making excuses. No one's coming to your site, and those that do, probably did by accident.
- Marketing is expensive as hell. You can't just launch your killer idea and expect the world to come flooding in. Every user you get has a cost, and you ought to figure out that cost quickly.

The keen of you will notice something odd about that screenshot above. Two email addresses are missing. What's going on there?

In short, I have no idea. I suspect it's something to do with my Facebook login, where I'm not actually getting the email address back. Bug found!

Another interesting thing to notice: of the five users that signed up, none of them appear to have completed setup. When I ran that query, I got back the email address, and the artist name, and all the new users are missing the artist name. This tells me that either A) they signed up, got to that part of the setup and realized they were in the wrong place, or B) something went awry on that part of setup, preventing them from finishing. Both kinda suck, but A is better. Regardless, more testing of setup coming ASAP.

Yesterday, I emailed the three users for whom I have email addresses, asking them if there's anything I can do to help them get set up. I'm hoping I can help them out and/or find out where something might be broken or confusing in the process.

## Traffic Checkin

While we're talking about people, let's chat about the traffic to the site. As I mentioned above, not shipping because you're worried about people seeing broken things is generally an excuse, not reality (unless you've planned some big reveal, which is another kind of mistake altogether). Let's see that in practice, by taking a gander at the JamPay analytics since "launch" day:

![jampay analytics](https://dl.dropbox.com/s/p5i2napygxfmreb/Screenshot%202016-05-24%2017.27.21.png?dl=0)

Meh. 125 sessions, or around 9/day. Given that some of this is bot traffic, some of it is mistaken clicks, and some is myself (because I don't have my IP filtered yet), we're not talking about much traffic at all.

But, let's dig in further. I set up a custom event on the signup button, to see how many people click to signup. Let's see those numbers for the past week:

![jampay conversions](https://dl.dropbox.com/s/y8mcr3en01y8mvt/Screenshot%202016-05-24%2017.29.22.png?dl=0)

Alright, so, 17, 11 of which were unique. That gives us around a 9% conversion rate, which isn't horribad, but honestly means almost nothing with this low amount of traffic and zero marketing efforts. We'll come back to that number soon as we ramp up traffic.

One more interesting morsel. I'm always interested in knowing how traffic gets to the site, especially organic search traffic. Let's take a look at that:

![webmasters](https://dl.dropbox.com/s/zc0qu2exb4xwfrm/Screenshot%202016-05-24%2017.35.21.png?dl=0)

Here's where things are interesting. There are a number of clicks using the actual name "jampay", which, to be honest, is really surprising. Given almost no one knows about JamPay, I find it hard to believe people are searching for it by name.

What's more possible is that folks are searching for this other company - Jam Payments - an Australian payments company, instead of my site. We'll hope that doesn't come back to bite us in the future, but in the meantime, ride the good fortune of the similar name (I'm not terribly worried about trademark issues, but we are both kind of in the payments space online, so it's a gray area. Being that they're Australian and we're in the US might help, but I'm not a trademark attorney, so I'm not sure).

## Next Steps

So, now that we're "launched" (for whatever that's worth), it's onto making sure the thing is usable and doesn't break horribly. This week, I'm building out new signup and login pages that I had designed (because my original designs sucked), and testing the whole signup flow to make sure it's rock solid. Once I do that, I'll be starting a personal reach out campaign to musicians, aiming to get 100 on the platform by the end of June. That's, admittedly, a slow start, but I want to use that 100 to ensure things are running well and delivering value the right way before I pour money and time into wider marketing efforts.

Until next week!


[jampay]: http://jampay.com?utm_source=building-jampay
[sub]: http://northamerica.startupbus.com
[ep0]: http://justindavis.co/building-jampay/episode-0-lets-get-started.html
[ep1]: http://justindavis.co/building-jampay/episode-1-names-logos-and-other-branding-bullshit
[ep2]: http://justindavis.co/building-jampay/episode-2-validation-ssl-and-shipping

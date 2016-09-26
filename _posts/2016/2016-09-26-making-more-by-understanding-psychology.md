---
layout: post
title: "How Understanding Psychology Can Lead to More Revenue"
summary: "By understanding how people think, and how our minds are wired to work, it's possible to drive people to do what you want, like paying you more. I experienced this first hand recently by _not_ doing it"
comments: true
---

A few weeks ago, a yearly event here in Tampa called [TechJam] happened, a battle of the bands to support charity, where all the bands are comprised of people who work in tech in the area (full disclosure, I played in one of the bands - [SoundWave]). Here's the how the event typically works: attendees pay admission to the event, and are entertained by bands all night. Since it's a battle of the bands, attendees vote for their favorite band by donating to [TechStart] in the name of that band, generally by tossing cash in one of four or five buckets with the bands' names on them. At the end of the night, money is tallied up, a winner is declared, and TechStart benefits from all the money collected through voting. Pretty sweet deal. 

This year, I was talking with my friend [Akira], who runs TechStart, and mentioned [JamPay], the app I built to help musicians make more during live shows by accepting tips via credit card. I pitched to her that we could use JamPay as a way to help raise money, by allowing attendees to donate to each band via the app, with all the money ending up with TechStart. Additionally, we'd be able to tally results in realtime, instead of laborously counting it up at the end of the night. She was stoked, and I was excited to test the platform on this new use case, and we went to work.

Fast forward a couple months later, and we're a week out from the event. I'd finished the customizations to the platform to allow for the donation workflow, and it came time to test. Even though everything worked great locally, with such a high profile event, I wanted to be triple sure that everything would go smoothly, so I decided to test things in production. For each band at the event, I went to their profile, ran a $1 donation, to ensure it showed up and was deposited successfully in TechStart's account. Everything worked perfectly, but as I'd soon find out, that test had an adverse effect on the donations the night of the actual event. 

A week later, it's time for the event. Things are working well, bands are entertaining the crowds, and the donations start to flow through JamPay. Then, I noticed something really peculiar - most of the donations were for *$1*. At first, I panicked - "Uh oh, what it something's wrong where it's processing things as $1 regardless of donation amount?" Even though I'd set the default amount at $5, the $1 amounts kept coming. I was both perplexed and terrified, feeling like I owed Akira an apology for screwing up the donation amounts. 

That's when my buddy [Gregg] pointed out a brilliant observation. As we were talking about the app, he said to me, "You know what's happening, right? People see your $1 test, and they think that's what they have to do to vote. They're just following your lead."

Bingo. He nailed it. 

By running the $1 test on each profile, the first people to donate that night saw that donation amount (each donation/tip is shown on an activity feed, publicly viewable). Those people simply donated $1, thinking that's what they were supposed to do in order to vote. The next people saw their donations of $1, and things kept going from there. 

Eventually, some higher donations (some up to $200!) came through, and the trend was somewhat disturbed, with higher amounts become more normal as the night wore on. However, the first hour or so of the event taught me a valuable lesson: when doing something new, people look for queues about how to act, and will follow those queues in the absense of any other information. Similarly, I'd inadvertently [anchored] people on a low amount, meaning the resulting donations that were above $1, probably weren't as high as they could have been. 

In the end, [JamPay] helped TechStart raise nearly $3000 for their cause, a 10x improvement over the previous year, which I'd consider a massive success. Even though we could have driven donations higher, we learned an incredible lesson about psychology and how understanding how people think and act can directly make a difference in the bottom line. 

If I were to do it again, I would have still tested with $1, but I would have gone in and manually changed the display amount to $10 or $20, instead of $1, providing a higher anchor, and preventing follow-the-leader with the lower amount. Had we done this, I imagine the results would have been even more spectacular than they were. 

[techjam]: http://techstarttampabay.org/techjam2016/
[techstart]: http://techstarttampabay.org/
[soundwave]: https://twitter.com/ineedsoundwave
[akira]: https://twitter.com/theakirakay
[jampay]: http://jampay.com
[gregg]: https://twitter.com/whoisgregg
[anchored]: https://en.wikipedia.org/wiki/Anchoring

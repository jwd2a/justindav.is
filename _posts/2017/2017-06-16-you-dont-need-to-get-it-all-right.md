---
layout: post
title: "You Don't Need to Get it All Correct Immediately"
summary: "Too many people wait on shit to be perfect. Get it close, leave out some stuff, and set yourself up to quickly iterate."
comment: true
---

I design a lot of software, both for myself and for clients. One thing I hear often are statements like "Well, users might need [X functionality] in this [somewhat rare use case]" or "I don't know if that's exactly the right way to handle [X functionality]". Both of these statements are borne out of fear, fear that once it's out in the world, it's unchangable, and fear that if you get it wrong, you'll have a mutiny on your hands. How often do either of these cases end up being true? So close to zero it's statistically unimportant. 

There's a problem in how much software is produced. Instead of being produced with a "get it as close as we can, and set up ourselves to quickly iterate" attitude, it's produced with a "shine everything to a perfect point of polish" attitude. The problem with this is that it _delays getting the product in front of people_, which is an order of magnitude larger an issue than missing a piece of functionality or designing something slightly wrong. 

This issue can be tracked to a number of causes:

- *Culture of Perfectionism*: I know, everyone hears all the Steve Jobs quotes about everything needing to be perfect, and they latch onto it, thinking that if they adopt this attitude, they'll be Jobs reincarnate. Wrong. Even if the stories about Jobs were true, it's such a rare exeception that it's foolish to use as a standard. Many more companies have failed because they ran out of money buying polish than have companies failed because they had to fix a few dings.
- *IT Protectionism*: Launching earlier and setting yourself up to iterate toward perfect requires an extraordinarily level of cooperation across the organization. This is more cultural than anything. When IT departments remain protectionist about their systems, putting up artificial barriers ("We can only deploy every other Thursday, because [mumbling]") or refusing to work with product and business to find ways to get to answers more quickly, it's poison. This self-preservation is all about maintaining power and protecting turf, an attitude that will sink a product incredibly fast. 
- *Lack of Appropriate Operations*: Getting practical here, launching a product and iterating toward the _right_ product requires that you have systems in place for incorporating feedback (user and business) and getting it back out the door quickly. Speed of that cycle is everything. If you don't have [the right devops environment][devopspost] set up, you're restricting yourself from being able to work as quickly as you need to. 

There are probably more, but these three are huge ones that I see on a daily basis.

I also blame agencies, freelancers and dev shops for propagating this attitude. For decades now, consultants and external shops have made their buck by taking in requirements, making a thing, ensuring it's polished perfectly, then dumping it back to the client while they move onto the next thing. Now, not ALL external shops work this way, but enough do that it's created the wrong narrative. Clients, hiring these folks, now want to ensure that they get all their requests handled before sending off the final check. This laboring over details, polishing every little thing, is borne out of the fear that the shop will disappear, and the client will be left with a static product that needs to work perfectly for a long time. Nowhere in that engagement is there a conversation about helping the client to iterate toward the right product - it's almost always "Give us the requirements, we'll make you the perfect thing". Convenient for agencies, shitty for products and the companies that run them. 

As an aside, it's important to note that I [work as one of these external shops][fcp]. We're also changing how we work, away from monolithic deliverables, to a more embedded approch, where we can bring our skills to bear over the long term, helping the product over countless cycles, not just designing and dropping. 

Regardless of the causes, one thing that I've learned over decades of doing this work: you're not going to get it right. You might get it in the ballpark. You might even get it pretty damn close, but you're _always_ going to get things wrong. The longer you spend polishing and adding to the product, the longer it takes you to find that gap, fix it, and move closer to something people love. 

Stop obsessing over features that people _might_ need, colors that aren't _just right_, and polishing until you feel proud. As [Reid Hoffman][rh], founder of LinkedIn, famously said, "If you're not embarrassed by the first version of your product, you launched too late".

One final note. Those who are thinking "This is so stupid, you want people to launch shit for launching's sake" don't have the ability to think critically, nor the ability to recognize nuance in approach. Launching a piece of shit is a terrible idea. This approach assumes you've taken care in what you're doing, have a reasonable understanding of the problems you're solving for people and the ability for your product to solve it, and have done what you can to ensure a good experience to users. Don't mistake launching early with launching a pile of shit.

[devopspost]: http://justindavis.co/2017/06/07/great-products-need-great-devops/
[fcp]: http://firstchairpartners.com
[rh]: https://venturebeat.com/2011/03/15/reid-hoffman-10-rules-of-entrepreneurship/

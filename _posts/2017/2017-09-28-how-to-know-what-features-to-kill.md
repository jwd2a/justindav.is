---
title: How to Know What Features to Kill
author: justin
layout: post
comments: true
header: stock/drippycat-1417871-pixabay.jpg
---

When you build, and eventually maintain, a product, you'll eventually have to
make a hard decisions: what features should you kill? Those ideas you had early on,
that made it into the product, aren't always good ideas. Sometimes, users don't
use those features as much as you want them to. Unless you prune out these
features, you'll end up with bloated, unusable software that leaves your users
looking for other solutions.

So, how do you know what to kill?

There are two things to consider: how *frequent* users use a feature, and how
*critical* that feature is to the application. Grading features on those two
axes will give you a way to have a productive conversation with your team about
whether or not these features should stay or die.

Here's how it works:

![featuregraph][featuregraph]

There are essentially 4 categories. Let's break them down.

**Frequently Used, Critical**

These features are the core of your product, the ones that make up the very base
of what the product is built around. For [CrowdSync][cs] this is the ability to
create a workflow, add actions to it, and add people to that workflow. These are
the features that users are in the application using constantly, and without
them, we wouldn't have a product.

These features should get a lot of attention, should comprise your MVP, and
should be at the forefront of refactoring and stability efforts.

**Frequently Used, Non-Critical**

These features are used often, but if they disappear, users can still get their
core work completed in the product. Things like email notifications, sorting,
searching and other enhancements fall into this category.

Watch yourself with these. They're fine to add, but ensure you're measuring
their usage (more on that in a minute), to make sure they are indeed frequently
used.

These features should be marketed, as they're highly popular, and if
you have an upsell path in your product, should be part of that upsell opportunity.

**Infrequently Used, Critical**

These are the unsexy features of your product: forgot password, account update,
user profiles and the like. Critical for ensuring users can adequately use the
product, and necessary to be there very occasionally, but not something people
are using much.

These features should be made rock-solid stable, but this isn't the place to
innovate. Save your creativity for features in the previous two categories.

**Infrequently Used, Non-Critical**

Here we are - the features to kill. These features border on useless. They're
not important, and don't get used often. **Mark these features for deletion
early and often**.

## What's Frequent, and What's Critical?

Now, onto the hard part - how do we measure frequency and criticality? The
answer is, it depends. Each product is different, and the nature of use is way
too wide to have any useful heuristics.

For determining criticality, ask yourself: "Can our users fully accomplish the
_core task_ in our product without this feature?" If the answer is yes, it's
probably not critical. It might in interesting, and might be popular, but it's
not critical.

Frequency requires measurement. For each feature in your product, you should be
measuring the interactions with that feature, by user. Rolling a simple script
to update a count in a Redis store or database whenever a user interacts with a
feature ("Oh, they filtered that list, +1) is a great way to start getting an
idea for this. There are other software packages out there that can also help
with measuring this, but the fact is, you have to be measuring this, else you'll
end up in a "No, a lot of people use it, I KNOW it!" conversation, which you
don't want to have.

How frequent is frequent enough? Well, that all depends on the app, and it might
take you a bit to start figuring that out. Look at usage by user, by session,
and in the aggregate. Start computing some averages, some trends, and some
deviations from other features you have. Put features on a frequency
leaderboard, and let them fight it out. However you sort it out, just make sure
you've got a process in place for measuring and reporting back on how often
things are used.

## Don't Be Afraid to Commit (Feature) Murder

Building software products is one of the fastest ways to get lured by the [sunk
cost fallacy][sunkcost] (perhaps right after investing). When you spend time
building a feature, you become attached to it. That investment you made in
bringing it into the world clouds your vision, and prevents you from objectively
understanding if that feature should really be there or not.

By grading things on these two axes - frequency and criticality - you're able to
bring some objectivity to the process. Sure, there's some subjectivity in
determining where they land, but the fact that you're being proactive about
saying "What features should we kill this month?" means you're well ahead of the
pack.

Keep shipping, and keep trimming.

Next issue.

[cs]: https://www.crowdsync.io
[featuregraph]: /images/features-to-kill/frequency-criticality.png
[sunkcost]: https://youarenotsosmart.com/2011/03/25/the-sunk-cost-fallacy/

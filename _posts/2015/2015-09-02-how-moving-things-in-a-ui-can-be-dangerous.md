---
layout: post
title: "Before You Move That Button - Stop!"
summary: "We, as humans, are pretty highly reliant on our visual system to help us to understand the world and establish patterns for how we interact with it. Sometimes, this can bite you badly in your interface."
comments: true
---
I use Slack all the time. In fact, it's possible I'm slightly obsessed. I'm currently on 13 slack teams, and spend probably 50% of my day in there.

So, when Slack recently redesigned their mobile app, it messed up my whole world. Now, it wasn't a big redesign - in fact, on the surface, I couldn't really tell anything had changed. Until I tried to switch teams, that's when the wheels came off.

To switch teams in Slack's mobile app (at least on iOS), you tap the upper righthand menu button, which slides out a menu. On the bottom of the menu is a handy little button for switching teams:

![Slack's iOS menu before the redesign](/images/slack_post/before.png)

Easy enough. Slide out, tap the bottom button, new team. Perfect.

Then, they decided to add a new button to the menu: "Invite", for inviting people to a team from the app. Here's the design with the new button:

![Slack's iOS menu after the redesign](/images/slack_post/reversed.png)

Innocent enough, right? NOT SO. Every time I slid the menu out to switch teams, I ended up hitting the Invite button, not the Switch Teams button. But why? The button is still there, what's going on here?

### The Importance of Spatial Memory in UI

We humans are a complicated bunch. Among the hoards of things our brains do for us, one of them is to keep track of objects in space. This _spatial memory_ helps us to navigate cities ("Oh, yeah, that was back behind us and over a block"), and helped our ancestors keep track of where the water and food were when they had to go hunting for it. Spatial memory is a critical part of how we work as a species (and most species, really), and it has a big influence on how we interact with computers as well.

When you come in contact with a user interface, whether it's on a computer, mobile device, or whatever, your brain gets to work mapping it spatially. It stores away where certain items are - button here, nav here, form down here. That's why you can come back to a site or app and so quickly get back to something you remember the location of.

Instead of having to relearn this every time, your brain makes a convenient map for you, making it easier to find your way back to items you've found previously, without needing to spend the extra brain cycles on relearning the interface. Now, if that thing you remember moves, your brain doesn't know - it keeps trying to go back to where the map said it was, and it takes some time to retrain it that things have moved elsewhere.

This is exactly what's happening with the Slack app. My brain had created a map: "Switch teams button is on the lower right when the menu is opened". I never re-read the menu when opening it - why would I? It's been there all this time, no reason to spend the effort to confirm that point. Until it moved, then things got hairy.

What made this worse is that the Invite button is only there on teams you're an administrator of, which means that for teams where you aren't the administrator, the button was back on the lower position. You can't blame my brain for having a difficult time redrawing the map.

### Don't Mess With Users' Minds

The lesson here is that spatial memory affects your user's understanding of your interface much more than you think. The location of items - especially ones that have been there for a while - are deeply implanted into their spatial map. When they return, they'll use that map first to find their way back, and if it's not there, it's a disconcerting and frustrating experience.

One thing to keep in mind is that this probably applies more to small changes than large ones. If you're making a large number of big changes in your interface, it's likely your user's mind with more readily accept that it needs to create a new map based on the number of cues that have changed. However, if there are only slight changes - as with the Slack button - the brain doesn't get the message that the map needs to be redrawn, and uses its old information, and you end up with strange moments.

To Slack's credit, they quickly changed things back. In their release notes in their latest version, they note:

> - Fixed: the “Switch Teams” button will now always be at the bottom of the flexpane instead of occasionally, confusingly, maddeningly trading places with the “Invite” button. Sorry about that.

Have you experienced these weird moments in interfaces before? Post your wildest spatial memory tales in the comments!

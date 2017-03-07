---
layout: post
title: "Review: Auth0"
summary: "Auth0 is a service that provides identity as a service, so you never have to build authentication again. Here, I lay out the good and the bad."
comments: true
---

No one that builds a web application wants to build user management. Tasks like registration, login, logout, forgot passwords, email confirmations and all that are boring to build, and complicated to get right. Because of their high impact on security, these components often take a good amount of time to dial in, and require a good deal of testing to ensure that things are rock solid. Worst of all, in almost all cases, these components of a product don't provide any additional value to the product - they're table stakes. You have to have them, and if you're like most people, you really don't want to spend the time building them. 

Enter [Auth0][auth0], an Identity-as-a-Service provider. Auth0 allows you to fully move user and identity management off your service, onto theirs, with turnkey handling of tasks like login, registration and password resets (among much more). You get all the benefit, without needing to build the logic to handle it. All this, and it's in a secure facility, with the kind of certifications and protections that you'd pay a fortune to build yourself. 

Sounds great, right? I recently gave it a try, and thought I'd walk through my experience.

## Setup

Getting started with Auth0 is a piece of cake. They've got several pricing plans, ranging from free to quite pricey, all depending on how many users you've got, and what kind of capabilities you need. The good news is, their free tier is good up to 7,000 active users with unlimited logins, plenty if you're just getting started, and likely to be all you'll ever need for some enterprise applications. They've also got an Open Source Program, which allows for free usage of their services for open source projects. Gotta appreciate that. You can [check out their pricing here][pricing] and find a plan that suits what you're building.

After selecting a plan, getting set up takes no time. They use their own auth services, so you can sign in with Github, Facebook, etc. if you want, and you're off to the races.

Once you're in, Auth0 has a nice dashboard that'll show you your total user counts, recent logins, and new signups. Snazzy (and all things you didn't have to build manually for reporting).

![dashboard][dashboard]

The dashboard is really easy to get around, and has all the things you'd expect: setting up clients (your app), inspecting users, webhooks, email customization, logging, and all kinds of other bells and whistles. Definitely fully featured. 

Overall, getting started with Auth0 is super simple, you'll be up and running in under 15 minutes. 

## Implementataion

Once set up, implementing Auth0 is where the rubber really meets the road. First, you'll need to really think carefully about how to architect things now that your users aren't in your own store. A bit strange at first, but it gets easier to think about as you go. 

Past that, one of the early decisions you'll need to make is whether to use Auth0's prepackaged UI - called Lock - or to use your own UI and integrate with Auth0 a bit more manaully. 

To be honest, this is where my first beef with the service comes up. Lock, their prepackaged UI, looks something like this:

![lockui][lockui]

This is a component that drops into your app, and handles all the communication with Auth0 on your behalf, calling the login and register endpoints for you, so you don't have to do as deep an integratation. This is great, especially if you want to get auth implemented quickly, and move on. It sucks if you care about your auth sequence having the same look and feel as your own app (yes, you [can customize it][customizelock], to a point). I tend to want everything to be seamless, so I ended up rolling with the manual integration route, instead of using Lock.

This brings us to the second challenge implementating Auth0: documentation. To be honest, I'm still a bit perplexed on this. They have a *ton* of documentation, but it's not terribly well organized, and is set up in the form of "guides", more than API references. Guides are awesome to have, but when doing a manual implementation, I often want to skip straight to the login method, see how to call it and what the parameters are, and get on my way. The docs aren't as easy to navigate as I'd hoped, and slowed me down a bit as I was implementing things. 

Auth0 *does* have SDKs, which is helpful. The one I'm using for Node [is here][nodesdk], and works great. However, we run into the documentation issue yet again. [Peep the readme][nodesdk], I'll wait. 

Where are the docs?! Answer: you have to build them and serve them yourself. Kinda bizarre TBH, especially nowadays, where rich reference documentation for SDKs is readily available almost everywhere. I'm half tempated to registered auth0sdkdocs.com and host the docs myself, but that's a post for another day. 

The SDKs *do* work well, so I'll give them props there, you just have to figure out how to use them first. 

Next on the implementation front is interacting with their API. If you're not using Lock, you'll need to interact with their API directly (they have two: Authentication and Management, which makes things a bit more confusing). Thing is, you can't just spin up an API token and start calling. Auth0 requires that you refresh that token every 24 hours, something you'll need to automate on your backend somewhere. This isn't a huge deal, but it's an additional piece of overhead you'll have to manage. While you develop, you can get a long-lasting token so you don't have to mess with this, but come deploy time, [they strongly recommend you use short-lived tokens][tokens]. I can't say this is a bad thing, as it's definitely more secure, just an additional thing to consider as you work through implementation. As far as I can tell, this is not something you'd have to mess with if you use Lock, as that deals with public/private key pairs, instead of a token-based connection. 

This all sounds like a lot of hassle, doesn't it? Well, yes and no. It's a bit of a different way of thinking, but for something that's so critical in terms of security, it makes sense. Documentation could be better, and they could do a better job catering to the manual integration crowd, as opposed to pushing Lock all the time, but it's nothing insurmountable. Once you've got a hang of how things work, everything moves quite quickly. 


## Moving Users Out of Your Database

I have to be honest, the idea of moving all my users out of my database made me nervous. If you've got an app, your users are...well...everything. Not being in control of that data store is something I really had to come to terms with. That said, Auth0 lets you export things whenever you want, and you're not beholden to them for forever. You can always export everyone, and migrate back to your own store, should you feel the desire. That, combined with the fact that I know they're doing a better job protecting sensitive data than I would, means its a net win for my users, regardless of the mental weirdness of not actually having them in my database. 

Another strange thing about this is how and where to store all the extra information about your users. For me, I wanted a single source of truth - everything about a user should be in one place, not spread around multiple databases on multiple servers. So, if my users have a profile, with a photo, I want that stored alongside their login credentials. Luckily, Auth0 helps you do this through the `user_metadata` and `app_metadata` fields, for storing information about the user, and information about their access to your app, respectively:

![metadata][metadata]

That solves the problem nicely, so I don't have to worry about keeping a separate `user_profiles` collection on my side and joining those up. 

Another huge advantage to using Auth0 is that you get a bunch of administrative controls - updating profiles, reporting, resetting passwords - right out of the box. That's obviously a huge advantage, as it's stuff you don't have to otherwise build by hand. 

## Final Thoughts

Overall, I'm pretty happy with Auth0. Documentation could be structured better, and they could spend more time acknowledging people that do custom integrations instead of pushing their Lock widget so heavily, but I'm happy to take the bad with the good. Using Auth0 relieves me from a massive administrative and security burden when it comes to dealing with user data, and allows me to focus less on this scaffolding, and more on delivering business value via my product, something that should make everyone happy. Their pricing is good, and seems to scale nicely, and they definitely appear to have staying power, [based on the size of the team and the amount of backing they've got][size]. That makes me feel more comfortable using them, knowing they're not likely to evaporate with my user records next week. 

In short, I'd definitely recommend checking them out. It's hard to think of many cases where you'd want to take on the burden of managing identity on your own, with the security and administrative nightmares that can come along with it. Auth0 lets you get started quickly and get this capability in your product, so you can get back to focusing on what's important: delivering unique value to your customers. 

Have you had experience with Auth0? Did I miss an important part of considering a service like this? Leave it in the comments!

[auth0]:https://auth0.com
[dashboard]: https://dl.dropbox.com/s/iqmqt96tvseenbw/Screenshot%202017-03-07%2011.27.16.png
[lockui]: https://cdn.auth0.com/docs/media/articles/libraries/lock/lock-default.png
[metadata]: https://dl.dropbox.com/s/jaigazp8ltncqnt/Screenshot%202017-03-07%2013.06.26.png
[size]: https://auth0.com/about
[customizelock]: https://auth0.com/docs/quickstart/spa/angularjs/10-customizing-lock
[nodesdk]: https://github.com/auth0/node-auth0
[tokens]: https://auth0.com/docs/api/management/v2/tokens-flows
[pricing]: https://auth0.com/pricing


---
layout: post
title: "How to Design Great API Documentation"
summary: "Developers are users too, and when designing your API documentation, you should think about how to make their experience as good as possible."
comments: true
---
I've integrated with, and also built, a healthy number of APIs in my years. Over the course of integrating with and researching a bunch of APIs, I've looked at reams of API documentation. The sad fact is, most of it is terrible. From poorly documented endpoints to a lack of code samples, I've spent hours pinging endpoints trying to get a request right because the documentation was so bad.

Today, I stumbled across a [really cool service named Lob](http://www.lob.com), which is an API for physical mail. Now, I have a bit of a soft spot for this. A [buddy of mine and I](http://joshtronic.com) have been talking about building this exact same type of service for some time, so when I found Lob, it was a nice surprise.

My infatuation only grew when I looked at their API documentation. Now THIS is how APIs should be documented. Let's take a look:

![Lob.com API documentation](https://dl.dropbox.com/s/prqg0hpn9of92or/Screenshot%202015-07-31%2017.37.52.png?dl=0)

This is beautifully done. Methods are broken up nicely on the lefthand side, by functional description, not by endpoint address. Each endpoint has a clear description of what it does, and a very clear set of arguments listed, with the parameters clearly described for each parameter. Finally, the righthand side of the screen features code snippets for each endpoint, available in multiple languages/formats, showing, clearly, the request and response (and even variations on the request if applicable).

This is how all APIs should be documented. It's clear, to the point, and perfectly descriptive of how a developer can expect to interact with the service. If you're documenting an API of your own, take note: this is a master class in how to do it right.

#### Why This Matters

The fact is, if you're developing an API, you have users. Your users are other developers, and you owe it to them to deliver just as good an experience as you do to your end users of your product (assuming your product isn't only an API, where your end users ARE the developers!). Developer Experience is a critically important subset of user experience. If you're creating an API, service, library or other component that involves developers interacting with it, think about them just as you would any other user. They deserve to be treated as first class citizens of your experience, not simply monkeys with a (subpar) manual.

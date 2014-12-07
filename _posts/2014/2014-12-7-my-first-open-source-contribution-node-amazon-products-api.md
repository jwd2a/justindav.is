---
layout: post
title: "My First Open Source Contribution: Node Amazon Products API"
summary: "For the first time, I've released an open source project, a Node.JS module that allows an easy way of interacting with the Amazon Product Advertising API. Available now on npm!"
comments: true
---

I've been developing for almost 20 years now, about half of that professionally. While I've used countless open source libraries and packages in that time, I've never contributed one of my own. Whether it was that I never felt up to the task or the opportunity never presented itself, it doesn't matter - that streak is now broken. 

A couple days ago, I released [amz-products](https://www.npmjs.org/package/amz-products), an npm module that allows an easy interface to the Amazon Product Advertising API. As I'm using the API on a project with my buddy [Josh](http://www.joshtronic.com), it just made sense to package up what I'd created there and release it as open source. Thanks Josh, for the pushing to get this out into the world!

So, why this particular package? Well, [as the readme on the project states](https://github.com/fetchlogic/amz-products/blob/master/README.md), I couldn't find a good package on npm that seemed to work well for this API. Sure, there are a number of Amazon Product API packages out there, but each had weirdnesses about it. Either it had arcane authentication or other interfaces, or it only covered one or two endpoints of the API. Not satisfied with difficult-to-use or incomplete packages, I put this together to provide an easy and comprehensive solution to interacting with the Amazon Products API.

The package itself is pretty straightforward. It's a fairly thin wrapper around the API, but helps solve issues like authentication and response formats, which are pretty horrible in the native Amazon API. I'm hoping that folks find it easy to use and a good solution for getting data from the API.

If your project needs to consume product data from Amazon, I'd suggest [giving my module a look](https://www.npmjs.org/package/amz-products). If you have suggestions for making it better, leave them in the [project issues](https://github.com/fetchlogic/amz-products/issues), send me a pull request, or just leave them in the comments below!
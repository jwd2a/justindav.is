---
layout: post
title: "More Open Source Goodies: Simple Sitemap and Leaderbin"
summary: "Since we're on a tear of open source projects over the past week, here's a couple more worth pointing out. One is a collaboration I did this week, and the other is a buddy of mine's app that he just open sourced."
comments: true
---

Well, it's been a productive week for me in open-source land. Just last week, I [released my first open-source package ever](/2014-12-7-my-first-open-source-contribution-node-amazon-products-api), an npm module called [amz-products](https://www.npmjs.com/package/amz-products) that functions as a nice wrapper for the Amazon Product Advertising API. 

I've now put out a second module, in collaboration [with a buddy of mine](http://joshtronic.com), called [simple-sitemap](https://www.npmjs.com/package/simple-sitemap). This is yet another npm module that provides an easy facility for creating sitemaps for larger websites. We ran into an issue where we needed to generate sitemaps for sites with over 150k pages, and Google has a limit of 50k links per sitemap file. This package automatically creates multiple sitemap files to handle those large sites, definitely handy if you're dealing with that kind of scale. 

Also, the package includes automatic submission to both Google and Bing, so once it creates your sitemap for you, it'll go ahead and submit it, assuring the search engines have the latest from you. If you need an easy way to make sitemaps for your site, I highly encourage [checking it out!](http://npmjs.org/simple-sitemap)

Lastly, the same buddy of mine who worked on the simple-sitemap module with me just open sourced a project of his called Leaderbin. Leaderbin is an app that handles leaderboards as a service. It features a pretty simple API that allows you to pass it data, and it'll keep tabs on your leaderboards for you. Pretty great for folks who are incorporating any kind of gamification or other tracking into their products. It's not hosted anymore, but the code is out there, should you want to pick it up and run with it.

Any open source packages you've seen this week that are worth pointing out? Throw them in the comments!




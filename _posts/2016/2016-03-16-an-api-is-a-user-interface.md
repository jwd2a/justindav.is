---
layout: post
title: "An API is a User Interface"
summary: "More than anytime ever, APIs are user interfaces, not just machine interfaces. That means we need to design them as such."
comments: true
---

For the past few months, I've been working on an API project, helping design the architecture of the API, document that, and help with some of the implementation of it. You might ask why me, a UX guy, is screwing around with API design.

Because an API is a user interface, that's why.

On said project, I was recently discussing some naming conventions with another colleague on the project. He'd made the comment that the naming didn't matter, that it was a "machine interface". The problem is, it's not. APIs are consumed first by humans as they develop against them, _then_ by machines.

This is important, because approaching APIs like they're user interfaces means we have to design them with the same care and thought that we design the front-end of a product. We have to ensure that it follows standard conventions, that the naming is easy to understand, and that it's as self-explanatory as possible for a developer consuming it.

For the past few months, I've been using [Swagger][swagger] to document this API, and I'm super excited about it. Besides providing a set of tool automation around the API (auto-generating mock APIs, tests, etc.), it provides a fixed taxonomy for describing the API, which helps drive consistency that makes it much easier to consume as a developer. If you haven't checked it out, I definitely recommend you do.

Bottom line is this: APIs are consumed by _people_. Yes, machines use them day-to-day, but they have to be easy to understand by the folks writing the code to make the machines use them. Besides, if you're looking to get others integrating with your API, the ease of use will be a big factor in that adoption rate.

Don't think of APIs as a low-level machine interface. Elevate them to the same first-class status as your primary UI of your product, and treat them as what they are: a user interface.

[swagger]: http://swagger.io

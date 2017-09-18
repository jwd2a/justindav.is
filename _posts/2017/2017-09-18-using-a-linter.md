---
layout: post
title: "Using a Linter Will Make You a Better Dev"
summary: "Using a linter while you write code won't only make your code better formatted, it'll make you a better programmer."
comment: true
---

As we've been working on [CrowdSync][crowdsync] (our platform helping you automate workflows with groups of people), my co-founder [Josh][josh] insisted we use a linter as we dev, to help make sure our code is more consistently formatted. We installed [ESLint][eslint] and the [AirBNB Javascript Style Guide][airbnb], and the results have been amazing.

Suffice to say, I'll never write code without a linter again. 

First, the obvious: our code is *much* more consistently formatted, making it easier to see what's going on in various files (especially ones you haven't touched). No more differences in terms of how we indent code, how we declare variables, all that. Everything is consistent, which makes working faster and more fun. 

However, the other big benefit to linting didn't hit me until using a linter for a few days. The linter was *actually teaching me how to write better code.* With CrowdSync, we're writing everything in JavaScript ([read about why we switched from Angular 2 to React here][cspost]), and using ES6. The linter was teaching me when to use certain types of function syntax, and the react plugin we're using for the linter was teaching me when to use stateless components vs. when not to. As I was writing code, I was actually learning how to write code differently, not just with a cleaner syntax. It's a huge advantage. 

If you're not using a linter while you write code, you need to stop what you're doing and get it rolling now. Your team will write more consistent code, you'll write cleaner code, and you'll actually become a better developer as a result.

[crowdsync]:https://www.crowdsync.io
[josh]:http://joshtronic.com
[eslint]:https://eslint.org/
[airbnb]:https://github.com/airbnb/javascript
[cspost]: https://www.crowdsync.io/blog/2017/09/06/why-we-switched-from-angular-to-react/



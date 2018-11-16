---
layout: post
title: Why We Switched From Angular to React
comments: true
---

When we started building [CrowdSync][cs], we started building it using Angular v4.0. Angular had recently gone through a major transformation between 1 and 2, and the subsequent 4.0 version (yeah, they [skipped][nov3] v3) was a further upgrade to the framework. The new version of Angular was much more component-based, and overall a big improvement over Angular 1. Seemed like a perfect choice.

It took us about 4-6 weeks to get a good chunk of CrowdSync built using Angular. Not bad. Not exactly lightning speed, but not slow. The problem was, things were starting to slow down. Building components was getting more complicated. After awhile, we started to question whether Angular was really the right choice. After some healthy debate, we finally decided to give React a try. We figured we could branch the code, rewrite things in React a bit, see how it was going, and evaluate from there.

Nothing like a full rewrite of your core product, eh?

Here's the crazy part: rewriting what we'd built in Angular took **3 days in React**. And no, that wasn't 3, 14-hour overtime days.

Suffice to say, that fast of a rewrite had us pretty jacked, but was React really the right choice? We finally decided that yes, it definitely was, and went whole hog on it. For those who might be trying to weigh your options, here are *three reasons we chose React over Angular:*

- *Size*: React is small. Like, really small. Whereas Angular 2/4 comes with a healthy amount of cruft (not near as much as Angular 1, mind you), React is super trim. Once we'd rewritten the same components in React, we'd dropped our overall application size by **over 70%**. It's a massive savings, helps us deploy faster, and makes maintenance much easier.

- *Community*: When you're building software, speed is absolutely key. The more libraries and drop-in components you can use to speed up your development, the better. React is the hot kid on the block right now, and as a result, there are [scads][react1] [of][react2] [components][react3] out there. Just searching on Github gives you an idea of where things stand in terms of community:

![Comparison of GitHub Search Results][search-results]

(Nevermind the fact that Angular has more than 4x the amount of issues, to a fifth of the repositories. If you consider open issues per repo as a quality metric, that tells a story right there)

Not only are the libraries and components a huge boon to the React ecosystem, but the community of support out there is likewise just as critical. More StackOverflow answers, more tutorials, more help. A bigger community means more places to turn for help, which means faster development.

- *React and Redux Are Love*: If you're not familiar, [Redux][redux] is a global state management system, allowing your application to keep all state in a single store, accessing it from wherever you need it (like global variables, with much less ick). While you can use Redux with anything, technically, it dovetails with React beautifully via the [react-redux][react-redux] library. Once you start using Redux to manage state across your application, everything changes. No more passing state around, no more complex handling of events. A single source of truth across your entire app, simplying everything. AND, it goes so well with React, they might as well be married.

There are bunch of other reasons why we love react at CrowdSync. Have you used Angular and switched to React? Gone the other way? What's your experience been? Make sure to leave your thoughts in the comments!

[cs]: https://crowdsync.io
[nov3]: https://www.infoworld.com/article/3150716/application-development/forget-angular-3-google-skips-straight-to-angular-4.html
[react1]: https://github.com/brillout/awesome-react-components
[react2]: https://react.parts/web
[react3]: http://react-toolbox.com/#/
[redux]: http://redux.js.org/
[react-redux]: https://github.com/reactjs/react-redux
[search-results]: /images/angular-to-react/search-results.png

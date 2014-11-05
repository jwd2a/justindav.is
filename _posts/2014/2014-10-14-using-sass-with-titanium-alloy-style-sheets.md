---
layout: post
title: "Using Sass with Titanium Alloy Style Sheets"
summary: "If you're a Titanium dev, using Sass in your Alloy style sheets can save a bunch of time and make your code much more DRY. This post looks at how to get Sass up and running with Titanium."
---

Today, using CSS frameworks and preprocessors, like LESS and Sass, is an important part of efficient frontend development workflow. These new approaches allow us to use things like variables, mixins, inheritance and imports to make our CSS more flexible, more DRY, and more modular. In short, it makes writing CSS less of a pain.

What if you’re a Titanium developer? How can you harness the power of these CSS tools when styling your app using Alloy TSS?

STSS to the rescue!

STSS is a NPM package that brings the power of Sass into Titanium, allowing you to use all those sexy Sass features in your Titanium apps.

Getting started is easy:

{% highlight javascript %}
npm install -g stss
{% endhighlight %}

I installed the package globally on my machine, but you can it locally in your project if you want. If you install globally like I did, add an Alloy pre-compile hook so that Titanium will compile the STSS files into TSS files before building the project.

To get that pre-compile hook set up, go to your project directory and do this:
{% highlight javascript %}
stss --jmk
{% endhighlight %}

Once you’ve done that, you’re in business! Start naming your Alloy style sheets with a `.stss’ extension, and enjoy the wonderful power of Sass in your Titanium apps!

For more information, [check out the official NPM package here](https://www.npmjs.org/package/stss). To learn about Sass and all the ways it’ll change your life, [check out their site.](http://www.sass-lang.org/)
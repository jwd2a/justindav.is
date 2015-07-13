---
layout: post
title: "Easy List Items with Flexbox"
summary: "One of the most common UI elements in the web is a list of items. The new `flexbox` spec makes creating them a piece of cake."
comments: true
---

Almost anything that displays information uses one of the most common UI elements: a list, with items in it. In today's modern web applications, these list items are no longer single-component items - they're complex combinations of labels, controls and other pieces that allow a user to act on the items in the list.

Take for example, something like this:

![Example of a list item](https://dl.dropbox.com/s/fu0f53hbjc1aem1/Screenshot%202015-07-13%2015.59.36.png?dl=0)

This is a super common pattern - an item in a list, with controls on the right and left for selecting, configuring and removing. Regardless of the specific items, this is a really common piece of user interface that you'll find in almost any application today.

Until recently, these were - frankly - a pain in the ass to create. Sure, laying out the pieces in the line item horizontally is easy enough - a few `float`s here and there, some margin and padding, and boom, you're there. But getting it to center vertically in a perfect line, regardless of content height? FORGET IT. Pain City.

Until now. Until flexbox. This changes everything.

In the past, creating the above list item would require a few different hacks to work. Either you put it in a `table` (not really a hack if it's truly tabular data, but that's a debate for another day), use `line-height` to fool to browser into vertically centering, set `display: table-cell` on items, or some other combination of methods to convince the browser to display things as you want.

Flexbox makes everything so much easier. Using flexbox, we can define just a couple properties on the elements, and away we go. Here's a look at it in action. First, the HTML:

~~~

<div class="listItem">
  <input type="checkbox">
  <span>This is an item</span>
  <i class="settings icon"></i>
  <i class="remove icon"></i>
</div>

~~~

(I'm using the [Semantic UI](http://semantic-ui.com) library for the icons here. This library is a fully featured CSS framework that, to me, is nicer than Bootstrap. Check it out.)

And, now the magic. This is the CSS that makes it all work:

~~~
.listItem, i {
  display:flex;
  align-items:center;
}
.listItem span {
  flex: 1;
  margin-left: 20px;
}
~~~

That's it. Perfectly vertically-centered list items, where everything takes up the right amount of space. And the best part? No `float`s!

Here's what's happening. The first thing we do is to set `display:flex` on the container for the list item. This turns the container into - you guessed it - a *flexbox*. Once that happens, every item inside that item (in our case, `div.listItem`) is turned into *flex items*. These flex items have special properties that allow them to interact with the flex box in super cool ways. To get things to center vertically, we simply apply `align-items:center` to the flexbox, and we're done. Couldn't be easier.

The other thing you'll notice here is the `flex: 1` on .listItem span. This is a shorthard property that tells the `span` that it should expand to fit inside the `flexbox`. The other items have a default value of `0` set on them, and with the `span` having a value of `1`, it takes priority and expands to fit. We could add `flex: 1` to the checkbox if we wanted, and the checkbox and span would evenly split whatever space is leftover in the flexbox. Want the `span` to take up twice as much space as the checkbox? Just set `flex: 2` on it, and `flex: 1` on the checkbox. Frickin' simple.

Flexbox is honestly the best thing to happen to the CSS spec in awhile. A [buddy of mine](http://joshtronic.com) has replaced just about every single float on one of his [really large sites](http://scenekids.com) with flexbox, reducing code footprint and increasing maintainability vastly.

Another beautiful advantage to flexbox: it's [fully compatible across all current browsers](http://caniuse.com/#feat=flexbox), INCLUDING mobile versions. Pretty fly, huh?

Hopefully this gave you a great intro to one of the practical ways to use flexbox immediately. I'd recommend diving in to learn all the other cool tricks it can do - trust me, I've only scratched the surface with this example. One of the best articles on flexbox is [Chris Coyier's article on it](https://css-tricks.com/snippets/css/a-guide-to-flexbox/). I'd highly recommend you dive in and start playing around.

Are you using flexbox on your site or app? How's it working? Got some super cool success stories to share? Leave them in the comments!

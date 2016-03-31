---
layout: post
title: "Quickly Convert 0 or 1 (as a string) to a boolean"
summary: "Came across the need to convert a string representation of a boolean to an actual boolean, and this quick trick saved the day."
comments: true
---

Recently, I came up against a somewhat typical situation. I was working with an API response that returned booleans as 0 or 1, instead of `true` or `false`. To make matters a bit more complicated, they were strings, not ints.

Initially, the thought was to write a little filter that took the value in, manually compared the values, and return `true` or `false`, but I stumbled across a better trick that's _much_ more simple. Let's take a look:

~~~
var myFalsyValue = "0";
var myTruthyValue = "1";

!!+myFalsyValue // false
!!+myTruthyValue // true
~~~

That's it! So, how does this work? Pretty simple, really: first the `+` in the operation changes the string to an integer (handy trick in an of itself). Then, the double bang (`!!`) performs a boolean comparison on it, converting the int to a bool as it reverses it, then reverses it back with the second bang.

Easy as that! Saved me a bunch of time, hopefully it will for you!

---
layout: post
title: "Determine if a number is in the Fibonacci series using JavaScript"
summary: "Given a certain value, how would you find out if that value is in the Fibonacci series, in the most memory-conservative way? Let's look at how to get this done using JavaScript."
---

I recently had a conversation with a [buddy of mine](http://joshtronic.com) who is a kick ass dev. We had been chatting about working on little academic problems, as a way to increase your understanding of code and algorithms. Since we usually build for the web, where things are much more practical, spending some time on contrived problems like this is challenging and helps you think more deeply about solving problems using code.

So, we started tinkering with a question he was asked in an interview recently. How would you find out if a number is in the Fibonacci series? You can’t simply match against the entire series, as theoretically, the series is infinite, and you’d run out of memory.

I worked up a solution using Javascript that looks like this:

{% highlight javascript %}
function isFib(val){
 var prev = 0;
 var curr = 1;
 while(prev<=val){
   if(prev == val){
     console.log("yes!");
     return;
   }
   curr = prev + curr;
   prev = curr - prev;
 }
console.log("nope");

isFib(89); //for example, check if 89 is in the series

{% endhighlight %}

This solution essentially crawls through the series, looking for a match against the value given when calling the function. It should be fairly memory conservative, as we’re only storing the current and previous values of the walk. It’s also quite fast.

How would you improve this? Can this be made more efficient? Give your suggestions in the comments!

For more awesome little challenges like this, check out [HackerRank](http://www.hackerrank.com).
---
layout: post
title: "How to Trim the End of a Path in Javascript"
summary: "Need to trim off the end of a path in Javascript? Here's a one-line solution."
comments: true
---

I came across a situation recently where I needed to trim the end of a path in Javascript, and figured I'd share the quick, one-line solution, in case you need to do the same sometime. 

Here's the deal: I had a filepath that I needed to trim the filename off of, leaving just the path. So, I had this: `/path/to/filename.jpg`, and needed to trim that to `/path/to`.

The easiest way to do it? Use the `lastIndexOf()` method to find the last occurance of the slash, and trim from there, like this:

~~~

var string = '/path/to/filename.jpg'
var trimmedString = string.substr(0, string.lastIndexOf('/'));

console.log(trimmedString); // '/path/to'
~~~

Super easy. I'd considered using some variation of `split('/')`, but stumbled upon `lastIndexOf()`, which works much better. `lastIndexOf()` does just what it sounds like: gives you back the index of the last occurance of that character in the string. Using that inside of `substr()`, you can have it take the substring from the beginning, up to that indexed character. Piece of cake!

Hope this helps you if you need to trim the end of a path. Great for filepaths, and even for paths that might be in dot notation. 

 

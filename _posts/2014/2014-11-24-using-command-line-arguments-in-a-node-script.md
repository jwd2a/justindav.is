---
layout: post
title: "Using Command Line Arguments in a Node Script"
summary: "If you're creating scripts that can run on the command line, being able to pass arguments to the script is extremely useful. Let's take a look at how to do it with Node."
comments: true
---

Recently, I've found myself writing a lot of Node.JS scripts that are run from the command line. In fact, just last week, we looked at how to set up Node.JS modules to run from the command line. Continuing that line of exploration, let's look at how to pass arguments to these scripts when running them from the command line. 

If you've interacted with the command line much, you've undoubtedly seen arguments passed to CLI scripts. Take, for example, a git commit: 

`git commit -m "Your Message Here"`

In this command, you see that we pass an argument using the `-m` flag, followed by the contents of our argument, our commit message. 

Let's look at a couple ways to do this with Node.

### Option 1: Simple Arguments

Let's pretend we have a simple Node script that gets the weather from some api. We'll say that you call this on the command line using the `weather` keyword. It'd be nice for our script to work in either Fahrenheit or Celsuis, to support our international users. So, how would we pass an option to our script to let it know which units to use?

Let's start with the design of the interface on the command line. We've decided that we should pass a simple flag to indicate which unit to use, which would looks like this: `weather -f`. This would return weather in Fahrenheit units. Using `weather -c` might return in Celsius. (A quick note: it's likely you'd have this script default to one or the other, thus only passing the flag as an override, but you get the idea)

Ok, so how does our Node script know what do with this information? Here's a solution:

~~~
var units = process.argv[2];
if(units == '-f'){
    this.setUnits('Fahrenheit');
} else {
    this.setUnits('Celsius');
}
~~~

Easy enough. We're using the `process.argv` directive to grab arguments from the CLI, and parse those out in the script. In this example, we're enforcing order: the second item in the `process.argv` array is the first argument (the first item is the name of script itself). This is good for simple arguments, especially where you may just have a single arugment or flag passed to the script.

### Option 2: Flag and Argument Pairs

In the previous example, we have a simple flag that tells our script what unit to use for temperature, but what if we wanted to pass more information? For example, what if we wanted to pass the city *and* unit into our weather script?

For this, we can get a little more sophisticated, using flag and argument pairs, not unlike our git example at the start of this post.

First, this is how we'd like to pass things to the script: `weather -f -c Tampa,FL`.

Note that I've included both flags: temp and city. I might also just want to pass city: `weather -c Tampa,FL`.

In this example, using the declarative approach to argument order won't really work, since the unit flag is optional. How, then, can we retrieve the city argument if it exists?

Just like this:

~~~
var city;
if(process.argv.indexOf("-c") != -1){ //does our flag exist?
    city = process.argv[process.argv.indexOf("-c") + 1]; //grab the next item
}
~~~

And just like that, we've got the city, regardless of where it appears in the order of arguments. Our snippet here is simply checking to see if the flag has been passed, and if so, getting the element in the array that directly follows it. Piece of cake!

Using arguments and flags like this on the command line is infinitely useful, and if you're using Node on the CLI, you'll find these tricks to be really helpful ways of making your scripts more flexible.

Do you have some great command line tricks for Node? Leave them in the comments!






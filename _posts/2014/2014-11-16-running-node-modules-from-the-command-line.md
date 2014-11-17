---
layout: post
title: "Running Node Modules from the Command Line"
summary: "Being able to run a Node.js module from the command line, while also being able to include it and run it in your application, is a really useful pattern. Let's take a look at how to easily give your modules this super power."
---

Being able to run node.js modules from the command line is a really useful thing, especially if you're building an app that runs on a server, and might occasionally need to have pieces of it invoked manually. 

For example, let's pretend you had an app that creates some kind of report, say, analytics for your site. You might have created a node module called `report.js` that runs the reports, given a type of report you pass into one of the methods. 

Let's assume that script looks something like this:

~~~

var reporter = {};
reporter.createReport = function(reportType){
    //your logic to create a report
}

module.exports = reporter;

~~~

This very simple module exports a method called `createReport`, which can be included in your application and called, like so:

~~~
var reporter = require("./reporter");
reporter.createReport("site analytics");
~~~

But, what if you want to also be able to manually kick this off from the command line, in case someone asks you to run a report on the fly? Well, we can easily refactor our module to permit us to do just that. 

Here's our refactored module:

~~~
#!/usr/bin/env node

(function(){
    var reporter = {};
    exports.createReport = reporter.createReport = function(reportType){
        //your logic to create a report
    });

    if (!module.parent) {
        reporter.createReport(process.argv[2]);
    }
}();
~~~

Let's break down what we've done. 

1. First, we've slightly modified how things are constructed on the object, choosing to assign our method to both the `exports` variable and to make it a method on `reporter`. 
2. Then, we've added logic that checks to see if this module has been required in by another script, and if not, runs our method with arguments from the command line as the arguments for the method. The `module.parent` call is a Node call that returns `true` if this module has been required by another file. By checking to see if the value is `false`, we're telling our script that this wasn't required by another file, and must have been executed as a stand alone file (such as from the command line).
3. Finally, we wrap all of this in a self-invoking anonymous function, so our module logic runs immediately once the file is called.

That's it! Now, you can call this file as we did above where it was required into another file, or you can call it from the command line like this: `./reporter "site analytics"`.

Note that if you don't include the shebang in the file, you'll need to prepend your CLI call with `node`. 

BOOM! Now your node modules can be included and invoked from another file, or simply run ala carte from the command line. I've found a lot of uses for this, and hope you do as well!

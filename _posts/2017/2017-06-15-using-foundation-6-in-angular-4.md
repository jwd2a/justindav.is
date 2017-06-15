---
layout: post
title: "Using Foundation 6 in Angular 4 (or 2)"
summary: "How to use Foundation for Sites 6 in Angular 4 (or any version 2+)"
comment: true
---

I recently [started a project][crowdsync] that's built using Angular 4. As a fairly longtime Angular 1 user, the transition from 1.X to 4.X was...well...big. TL;DR, Angular 4 is nothing like Angular 1, so I had to relearn just about everything about the framework (including how to use [typescript][ts] which has come with its own set of challenges).

In addition, our [frontend dude][doodlemarks] is a fan of [Foundation][foundation], and we're using that for all our frontend framework needs. Recently, as I was working on implementing a modal, I couldn't get it to trigger, despite following the docs line-for-line. If you've had trouble getting Foundation's JS components to work with Angular 2+, here's how to solve the problem.

## Dynamic Components and Binding

Let's look at how you'd set up a simple modal in Foundation:

```html
<button class="button" data-open="myModal">Add Action</button>                                                
<div class="large reveal" id="myModal" data-reveal>                                                           
  <h1>My Modal Title</h1>                                                                                            
  <p>This is the body of my modal</p>
</div>                                                                                                                 
```

Without getting too in the weeds with how Foundation works internally, here's what's happening. Defining the `data-open` attribute on the button binds that button's click to the item it's pointing at, in this case, `#myModal`. When Foundation loads up, it runs through and finds all of these attributes, binds listeners to them, and waits to take action when you click.

Here's the problem. With Angular, components are injected into the DOM after Foundation has loaded. When you load up a new component, and inject it, Foundation _doesn't know it's there_. We need to tell Foundation to reinitialize and bind again, so these attributes will get wired up.

Here's how we do it. Our super simple Angular 2+ component looks like this:

```javascript
{ import Component } from '@angular/core';
declare var $:any

@Component({
  selector: 'my-component',
  templateUrl: './my-component.html'
  // other stuff here
});

export class MyComponent implements OnInit {
  constructor() {}
  
  ngOnInit() {
    $(document).foundation();
  }
}
```

A couple things to note. First, we declare `$` as a variable in the component that we can use (note that this is a typescript thing, if you're not using typescript, you likely won't need this), and give it a type of `any`. This gives us access to jQuery, which is needed to call Foundation. Then, in our `ngOnInit` method on the component, we call `$(document).foundation()`, which tells Foundation to reinitialize and bind to the DOM again. Since our component's HTML is now in the DOM, it finds the attributes, binds the listeners, and you're in business!

This should work for Angular 2 and above, and for Foundation for Sites 6.X. Other versions, YMMV.

[crowdsync]: https://crowdsync.io
[ts]: http://www.typescriptlang.org/
[doodlemarks]: https://twitter.com/doodlemarks
[foundation]: http://foundation.zurb.com/sites/docs/

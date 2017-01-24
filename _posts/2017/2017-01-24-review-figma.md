---
layout: post
title: "Review: Figma"
summary: "A look inside of one of the newest tools out there for user experience and visual designers."
comments: true
---

As a user experience designer, I'm always looking to improve my process and toolset, taking a look at the newest offerings and seeing if they offer something to help increase the quality of my work that I do with clients. In the past, just for producing wireframes, I've used [Adobe Indesign][id], [Axure][axure], [Balsamiq][balsamiq], [Sketch][sketch] and now, [Figma][figma]. 

Figma is the new kid on the block, aiming to compete with Sketch (which is a phenomenal piece of software), but do so in the browser. That offers collaboration and realtime iteration on design work that isn't possible in many other tools. Offering that, coupled with a Sketch-like approach to the interface, made it an attractive option. In addition, I've been trying to reduce my dependence on Mac-only software (for a possible move back to Windows...or Linux), and Sketch has publicly said [they'll never build the software for anything outside MacOS][osxsnobs]. While on that kick to distance myself from these walled-garden applications, I stumbled upon Figma. Having used it for awhile now, I feel good about giving my honest appraisal about where it stands today, in relation to other pieces of software doing similar things.

When I first found Figma, the first thing that immediately caught me was the animation on their homepage (this is a small bit of it, check out [their homepage][figma] for the full thing):

![figmagif](https://dl.dropbox.com/s/prnnyxfl6k2qvlo/figma.gif)

The collaboration! The speed of iteration! The clean UI and sleek toolset! To be honest, I was pretty immediately captured by this whole thing, and dove in to take a look. Now, after having used it for about 6 weeks, and having produced a number of artifacts in it, I've got a fairly good handle on what it does well, and where it could use a bit of help. Let's take a look.

## The Good

It's hard to talk about the good things in Figma without mentioning performance. In short, it's quite stunning. I'm generally pretty suspicious about browser-based applications like this, especially ones that attempt to emulate a desktop-only piece of software like Sketch. I figured it'd fall prey to typical issues like a laggy UI, less-than-smooth transitions, and other trappings of having to operate in the limited memory space of a browser tab. 

Boy, was I wrong. Figma operates _seamlessly_, and it feels like you're using an application on the desktop. Frankly, it doesn't really feel much different than using Sketch, which in my mind, is a gigantic accomplishment. 

Also among the good things are the collaborative aspects of the tool. I haven't had a chance to engage in a fully collaborative session inside Figma, but my limited experience with some of these features has been quite good. Being able to leave comments on a design and have conversations about it is a great feature that blends the review aspect of something like [Invision][invision] with the actual production tool. This makes collaboration and discussion faster and more centralized, which is huge for remote teams. 

![collaboration in figma](https://dl.dropbox.com/s/qjpcbyuakl8rpjb/Screenshot%202017-01-24%2009.47.10.png)

Once inside a document, working, the toolset is quite good. Standard features like lines, paths and shapes come into play, and everything is vector-based, allowing things to scale nicely. Additionally, Figma comes equipped with a number of frames (artboards, for those coming from the Adobe world) of various sizes, to help quickly put together screen designs based on device targets.

![frames](https://dl.dropbox.com/s/z5y2shakt2t325p/Screenshot%202017-01-24%2009.51.06.png)

Customizing things like fonts, lines, shapes and other elements follows the standard metaphors you'll find elsewhere, which means you're up and running instantly, with no extra learning curve required for using those tools (that said, some things like underlining text are buried in a menu, which seems an odd choice).

Another killer part of Figma are _components_, a feature just rolled out last fall before the holidays. Components are really handy, allowing you to create a single object out of multiple objects, copy that, and use inheritence to allow the children to inherit future changes from the parent. While doing so, you can spot change parts of the children, and still have the interitance work for other items in the component. SUPER handy, and also a little difficult to explain. [Check out their blog post about it][componentspost] and check out a quick glimpse at me using these in some wireframes to get an idea for how they work: 

![componentsgif](https://dl.dropbox.com/s/g4f9bzreztaiyjj/figcomponents.gif)

Overall, there's a lot to like about Figma, especially in the performance department. While many of the other things in the application are table stakes for design software like this, it handles them well, and frankly, better than other popular cloud-based design solutions (cough, cough, Balsamiq).

That said, there are definitely some places where improvement is needed, so let's give a fair shake to both sides and look at those items.

## The Not So Good

If there are any places where Figma falls down, it can be summed up in a couple words: workflow and integration. 

First up, workflow. Figma, for all its good, had some workflow hurdles that diminish some of the great things about it. First, there doesn't appear to be an ability to create or use a centralized symbol library, which is a near deal-killer if you're doing UX-based work (and probably visual design work as well). When I'm wireframing or prototyping something, I'll have a number of symbols I draw on that are used as common components across nearly all my files. Image placeholders, common web components, icons - these are the kind of things that are used in almost every mockup or wireframe I put together, and in other software like InDesign or Axure, they're pulled from a centralized symbol library (Balsamiq does this as well, so I don't buy 'browser-based' as an excuse). While, yes, it's true you could create a library, and copy/paste from it in Figma, it requires you either A) have that hand-made library open in another tab all the time, or B) pogo-stick from your file, back to the file manager, and back again. An embedded symbol library as part of the core toolset would be a game changer, and something I hope they'll look at sooner than later. 

Related to this, components (for all their glory and amazingness), don't work across multiple files. This, unfortunately, takes away a lot of the usefulness, as one of the primary uses of components is to have shared elements across multiple parts of an interface (read: design files) that give the design consistency and makes future assembly of interfaces faster and more efficient. [They're apparently working on this][componenttweet], and hopefully it'll come about soon. 

Another area that Figma feels to be lacking in is in the integration department. Let's be honest here: Figma is a direct competitor to Sketch, all the way down to the design of the interface components. There's no hiding that. However, Sketch has a robust and ever-growing suite of integrations and plugins, from [features that allow you to pull in mock content][sketchmock] to sexy new integrations [with Invision][invisionsketch]. These additions to the Sketch ecosystem are widening the gulf between it and Figma, and will end up being an increasing area of pressure, as more and more integrations for Sketch pop up. Given that a lot of designers who are likely to be targeted by Figma are also Mac users, it's hard to believe that the Mac-only issue I have with Sketch is a real issue for most of its audience. Something Figma certainly can't rely on. 

Finally, let's talk about documentation. This isn't something I'd normally be a stickler on, but unfortuately, Figma's documentation and help is quite poor. For a tool like this, with the kind of ambitions it has, I'd expect more robust help documentation, tutorials, blog posts and generally a pretty deep ecosystem of help, tips and tricks. With Figma, there's nearly zero, aside from some cursory help docs that do the bare minimum to explain locations of items in the tool. If I were at Figma, I'd work to establish relationships with bloggers and others to write tutorials and help fill out that ecosystem. Today, however, things feel sparse. Note the distinct lack of screenshots and images in the help docs for....design software: 

![figmahelp](https://dl.dropbox.com/s/ub8qz2qpodvyoi0/Screenshot%202017-01-24%2011.06.48.png)

In short, my biggest issues with Figma are that it just feels _immature_. For a company that has [$12 Million][funding] in funding, I'd expect a bit more rapid development of some of these parts of the tool, and a bit more parity with Sketch on these areas. Sure, they've got additional challenges being browser-based (but also some distinct advantages), but such is the bed that they decided to lay in. At the end of the day, designers will choose the tool that offers them the ability to work more quickly, iterate faster, and produce higher quality work. 

As for me? I'm still undecided. Figma's working alright for me, but would I pay monthly for it? (It's currently free, until sometime this year) I'm unsure. $99 for Sketch, and I've got an incredibly robust tool (if tied to MacOS). I think Figma is going to have to do some work to get closer to their feature set before it's a clear winner. 

If you're looking for a new tool to design in, I defintely recommended checking Figma out. As mentioned, the performance is first-rate, and it's certainly on par with any other design tool in terms of the basic set of features (and some not so basic, as with components). That said, there are certainly some workflow and integration issues to be solved before it's a serious competitor to Sketch. If you're loving Sketch, it might be a tough transition, but worth an hour to check it out. 

Have you tried Figma? What are your impressions? Anything I missed in my assessment? Leave your thoughts in the comments!

[id]: http://www.adobe.com/products/indesign.html
[axure]: http://axure.com
[balsamiq]: http://balsamiq.com
[sketch]: https://www.sketchapp.com/
[figma]: https://figma.com
[invision]: https://www.invisionapp.com
[componentspost]: https://medium.com/figma-design/components-in-figma-e7e80fcf6fd2#.diexa93ak
[componenttweet]: https://twitter.com/jwd2a/status/816381444595404801
[sketchmock]: https://github.com/preciousforever/sketch-data-populator
[invisionsketch]: https://www.invisionapp.com/craft
[funding]: https://techcrunch.com/2015/12/03/figma-vs-goliath/
[osxsnobs]: https://www.sketchapp.com/support/faq/#platforms




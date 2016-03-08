---
layout: post
title: "Designing Interfaces with CRUD and FEE"
summary: "A couple tricks to help make sure you've covered all your bases when designing an interface."
comments: true
---

As [part of my work][firstchair], I spend a chunk of time designing interfaces. On the surface, this is easy enough - lay out controls in a sensible manner, make sure things align with the user's mental model about how they expect to get the work done, and check against some basic design principles.

But, it's not that simple. When we design things for an _interactive_ medium like the web, we have to contend with not only the design of the interface itself, but also the _states_ of the interface - what happens when a user does X, Y and Z.

States can be difficult to design for, because it requires thinking of the design in _motion_, not static, and it requires remembering what states to consider for each component of the interface. Make no mistake, however: poorly designed states are one of the more egregious interface design mistakes. Sure - it's easy to design a static screen, but to think through and design it well as it changes in front of a user's eyes? That's a whole different story.

To help, I use a couple acronyms to keep these states in front of my mind the whole time I design. When designing an interface, I consider CRUD, and FEE. Here's how they break down.

First is the common acronym CRUD - used to represent the basic states of any i/o system:

- **C**reate - how does a user create something in this view? What does that interaction look like?
- **R**ead - what does it look like to view information in this interface? This is usually the default state you'll design.
- **U**pdate - how does a user update something in this view?
- **D**elete - how does a user delete something in this view? Can they? What happens to other items when something is removed?

CRUD is a pretty well-known and straightforward set of states to design for, and can go a long way toward ensuring you've covered the major states of the interface. But, it doesn't end there. There are a few additional states to take care of, to ensure the design performs as well as possible, and provides the best possible user experience. I remember these with FEE (because it'll cost you if you don't think through these):

- **F**ull - how does the interface perform when it's full? If you're displaying 1,000 items, are you paginating, scrolling, etc?
- **E** - the converse to full, how does the interface appear when it's empty? This is also known as "zero state" or "first-time use". [Patterns like these][zerostates] can help suss out how to solve this state.
- **E**rror - what happens when a user makes an error? If you're designing for mobile, what happens if the connection drops? Where you you communicate this, and what language do you use? Helping users recover from errors (because they *will* make them) is a critical part of crafting a great experience.

CRUD and FEE can be great litmus tests for any part of your interface, ensuring you've captured not only the static layout and design of the screen, but the _motion_ of the interface over time as the user interacts with it.

Do you have any acronyms or other devices that help you remember what to design for? Drop them in the comments!

[firstchair]: http://firstchairpartners.com
[zerostates]: http://emptystat.es/

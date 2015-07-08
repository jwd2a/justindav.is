---
layout: post
title: "Idea: Smarter Sprinkers"
summary: "The first in my Idea series, this post looks at an idea for creating better irrigation systems for home and commercial use."
comments: true
---

[I recently wrote about writing before building something](http://justindavis.co/2015/07/06/before-you-build-write/), and this is my first stab at doing just that on this blog. I'm calling this the Idea Series for now, though, I'll likely change that name. Regardless of the name, the point is to write (ideally weekly) about ideas I'm kicking around. I've committed myself to not pursuing a project seriously until the 4th quarter of this year. In the meantime, I'm exploring ideas, and looking to see what feels like it sticks best.

Without further ado, then, the first idea in the series: smarter sprinklers. A shout out to [Steve Lazaridis](http://www.twitter.com/SteveLazaridis) and [Mitch Neff](http://www.twitter.com/MitchNeff) who've also been part of this scheming.

### The Problem

My yard has an irrigation system, as most people's yards in Florida do. The system is pretty straightforward: 4 zones of sprinklers, each with a number of heads, which are operated by a timer in a base station that's mounted on the wall of my garage. Set the length of each zone in minutes, and the days you want it to come on, and you're done. Scheduled irrigation.

Here's the problem: weather doesn't work that way. Some days, it'll rain a bunch. Others, it'll be drier. Still others, my backyard may get more sun than usual because the wind causes the trees to allow more sun in. It's not an exact science.

As a result, parts of my yard inevitably end up drier or wetter than others, and I spend an inordinate amount of time tweaking the timing to try and hone in on the right schedule.

Further, I know _nothing_ about my yard. I don't know how much sun various parts get, I don't know the average temperature of various parts of the yard, and I don't know the PH or chemical composition of areas of my yard. All of this information is really important for growing a healthy lawn, and I just don't have a good way to get it.

### The Idea

I want to create a smarter sprinkler system. That system would replace the existing base station, but use the current irrigation component (pipes and heads, zones, etc.) that are currently installed. With this smarter system, I'd have better data and could automate my lawn watering without needing to manually twist the dials.

I imagine the system as comprised as two parts:

- Base Station: the base station is the brain. It collects data from the sensors, and controls the sprinklers automatically based on its own knowledge of what's happening in the yard at any given time. It also exposes that data through a RESTful API that I (and others) can build apps on top of, in order to better analyze and use the data I'm collecting day-to-day.

- Sensors: in the yard are a network of sensors, which communicate wirelessly with one another and the base station. Each sensor collects a variety of data - hydration level, temperature, sunlight level, PH, and so on. That data is streamed to the base station constantly, and the base station makes decisions about what to do with the irrigation based on what it's learning about the yard on an ongoing basis. These sensors could be subterranean or convertible, so they'd stay out of the way of the lawnmower and kids running around the yard.

With those two parts, we've got the makings of a much smarter irrigation system. The lawn would only be watered when it needs it (based on hydration levels), and only in zones where it's needed (preventing swampiness and saving a ton of water). Additionally, data like sunlight and temperature levels, as well as PH, would help the system to guide the fertilization schedule and even make recommendations on types of turf or other plants that would work well in the yard.

### Residential and Commercial

What's cool about this is that it can easily be used in a residential setting, and also taken into a commercial setting for golf courses, farms, cityscapes and other commercial spaces to help them better manage their own lawn irrigation and maintenance.

### Competition

Currently, there are a [few](http://amzn.to/1NPeGsK) [other](http://amzn.to/1eH5rzg) [people](http://amzn.to/1eH5yuG) working on this problem as well. Most have the smart base station that reads weather, but I think the real answer is in the base station/sensor combination. Seems that there's plenty of space out there for more products, as it definitely feels like this is a nascent, but growing area.

### How It's Sold

I imagine that this would be a package deal: a base station to replace your current base station, and a set of sensors - say 8 of them - for the initial install. Installing the sensors would be as easy as walking around the yard and sticking them in the grass, and installing the base station would take less than 30 minutes. I'd hope you could offer this to consumers for under $300, and commercial packages could get more sophisticated/expensive.

### What Do You Think?

Here's the point: I want to know what you think? Does this die or fly? Would you purchase smarter sprinklers for your yard? Do you know of a way to make the idea even better? Let's hear it!

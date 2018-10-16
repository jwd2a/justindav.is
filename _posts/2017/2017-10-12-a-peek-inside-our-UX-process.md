---
title: A Peek Inside our UX Process
author: justin
layout: post
comments: true
header: stock/viktor-hanacek-website-layout-wireframe-ideas-sketched-on-paper-picjumbo.jpg
---

As we continue to build [CrowdSync][cs], we're constantly needing to come up
with solutions for design problems that crop up. When we think of (or discover
via customer research) a new feature, we need to figure out the best way to drop
it into the app so it's easy to use and understand.

Since this is a process that nearly everyone building products goes through, we
thought we'd give a glimpse into how this process works for us, in case you want
to steal parts of it for your own projects.

## The Brief

Every problem starts with, well, a problem. We don't typically write this out
longhand, it's generally a Slack conversation to the effect of:

> So, we probably need a way for people to create a form to collect information,
> then define the email that sends it out. Thinking we might be able to do this
> as a wizard, or maybe a set of panels that collapse. Thoughts?

We try to keep this pretty fluid, going back and forth on what the key
requirements might be, the key constraints ("We can't really do X, since we're
using the lefthand side of the screen for Y"), and coming to some preliminary
ideas.

Our mantra is to get things into code as quickly as we can, so we see how they
work, so we don't spend much time here. A conversation on Slack for 5 minutes,
and one of us is off to the races to start to dig into solutions.

## Volume and Flow Studies

I (Justin) have been doing UX fulltime for around a decade or so, and I've
developed a process by which I tend to break down UX problems. First, the brief,
as mentioned above. This will generally also include any customer feedback we've
gathered, which manifest as requirements or constraints.

Next up are flow and volume studies. These tend to come out of my experience in
[architecture school][utarch], where designing buildings was similar to
designing interactive experiences.

First, we'll outline the overall experience with rough flows:

![flow sketch][flowsketch]

We're not trying to create art here. We're trying to think on paper as quickly
as possible, to understand the full end-to-end experience of using this feature.
This is fast and furious, sketching quick thumbnails to think through movement,
focusing less on how screens are designed, and more on how the entire experience
weaves together.

Next up are volume studies. This, again, stems from my time in architecture
school, where we'd work with blocks of foam or wood [to create abstract volume
studies of space][volumeimages]. I find this great to do with UI, as it helps to
think about hierarchy and movement within a single space (read: screen). This
starts to help me think about how a user moves through the page, where key areas
of interest might be, and how we might structure a narrative to be easy to
understand.

Here's what they typically look like:

![volume studies for UI][volumestudies]

Again, not art, but thinking. I'll try to create a handful of these, sometimes
3-4, or up to a dozen, depending on the complexity of the task. The goal here is
to allow myself to bring new conceptual and strategic ideas into the fold,
before I let the details get in the way.

## More Detail and Thumbnail Layouts

Flow and volume studies typically take 15-20 minutes of exploration, and give me
the groundwork for ways to start to structure the experience. With that intact,
it's time to jump into some screen level details at a high level.

Here, I'm starting to block out areas of the interface that I know will be
required, again, not paying much attention to high-fidelity detail, but
capturing the key content and interaction areas:

![thumbnail UI sketches][thumbnails]

These, combined with the previous sketches I've done, start to paint a pretty
vivid picture in my head about how a user might move through this experience. I
can start to weigh specific UI elements ("Hmmm, a wizard would give us this
advantage, but collapsible panels let us do this"), and think through the
tradeoffs we'll inevitably have to make.

Like the volume studies above, I try to go for quantity with thumbnails. As a
rule, I never only sketch one concept, and in fact, I'd argue that I never
sketch less than 3 ideas. Because they're small, quick and lacking much detail,
it's fast to go through these ideas, and the lack of detail gives you permission
to throw the bad ones away, since you haven't spent so much time on them (see
our post about [sunk costs when dealing with features][kill], and you'll know
why it's important not to get wedded to certain ideas too early).

Another thing about volume: sometimes your first idea _is_ the right idea, but
oftentimes, it's not. Often, you'll combine several ideas into the right
solution, making the number of ideas critical to helping get to better
solutions.

If I can give you one piece of advice when designing something, don't design one
solution and be done. Consider different approaches, then converge to the right
one.

## Selecting and Refining

Once we've done the thumbnail sketches, it's usually time to start talking
through it with the team. We'll toss the sketches in Slack, and discuss the
relative merits of each one, eventually coming together on what we think is
probably the best approach.

This kind of collaboration is important, because we can socialize these early
ideas with areas of the company that might affect implementation ("Oh, that idea
you have there, going to be hard due to X, Y, Z limitations. Maybe we can do
this instead...").

Once that's done, it's onto final sketches:

![detailed UI sketch][finalsketch]

As you can see, still not high artwork! Again, we're not striving to make
artifacts for the sake of artifacts, we're trying to think on paper before
jumping into the code.

Once we've got this level of detail in place, it's generally time to jump into
the editor (we love [Vim][vim] at CrowdSync), and start to build things out.
Rarely do we find the need to formally wireframe or comp out these interfaces,
unless there are highly complex issues that we need to see at a detail level
before committing the time to prototyping them.

## From Here to Launch

The rest of this process is pretty straightforward. Develop a prototype of the
feature on a branch (quickly, within a day or so if possible), show it to the
team, show it to some users, get feedback, and iterate. Polish things up, kick
it to production, and onto the next one!

Do you have any UX tricks in your process? Any special things you like to do to
think through new features? Leave em in the comments!

Next issue!

[cs]: https://www.crowdsync.io
[vim]: http://www.vim.org/
[kill]: https://www.crowdsync.io/blog/2017/09/28/how-to-know-what-features-to-kill?utm-source=crosspost
[utarch]: http://archdesign.utk.edu/
[flowsketch]: https://dl.dropbox.com/s/bitczeczrev1rel/flow.JPG
[volumeimages]: https://www.google.com/search?q=volume+studies+architecture&tbm=isch&tbo=u&source=univ&sa=X&ved=0ahUKEwj217Pm7OjWAhVF7iYKHcjUCb8Q7AkIMQ&biw=1482&bih=1299
[volumestudies]: https://dl.dropbox.com/s/xknnx11ffhji9tw/volume%20studies.JPG
[thumbnails]: https://dl.dropbox.com/s/mehubnxbgeq1t8g/thumbnails.JPG
[finalsketch]: https://dl.dropbox.com/s/i837ec79ociy05m/final%20sketch.JPG



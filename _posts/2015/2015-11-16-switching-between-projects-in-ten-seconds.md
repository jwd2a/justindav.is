---
layout: post
title: "Switching Between Projects in Ten Seconds (or less)"
summary: "If you work on multiple projects at a time - as most of us do - switching between them can be a pain and a momentum killer. There's a much better way."
comments: true
---

If you work on more than one project at a time, as most of us do, switching between projects can be a major timesuck and momentum killer. For me, I work on a number of things throughout the day - at the very least, a couple client projects and a side project. For each of those, I might have the following things open/running:

- Atom for editing
- Indesign for UX work
- Terminal: running mongo
- Terminal: running node
- Terminal: at directory, for git management
- Browser tab for Github issues
- Slack team related to project
- Toggl for tracking time on the project

...and who knows what else.

What that means is that each time I switch between projects, I have to close all that, and reopen it to a new directory, configuration or workspace. Depending on the project, this can mean a lot of time spent managing the environment. Time spent managing the environment is [tool time][spool], not goal time, and it can sap the momentum out of you as you switch between tasks.

## A Better Way Forward

Recently, my buddy [Josh][josh] turned me onto using [tmux][tmux] for better managing sessions of terminal windows. Tmux in itself is awesome, but combined with [tmuxinator][tmuxinator], it's really killer. Tmuxinator allows you to - among other things - create configurations of tmux sessions and launch a number of configured session with a single command.

Let's look at a quick example of how that works. I'm working on a little side project right now - it's a web app, built in Angular with a MongoDB backend and using Grunt to do the build.

Here's my tmuxinator configuration for the project, written in yaml:

~~~

name: tipping
root: ~/Code/tipping/app

windows:
  - server:
    layout: main-horizontal
      panes:
        -
        - grunt serve
  - database: mongo

~~~

When I run this (`mux start tipping`), I end up with the following:

![tmuxsessions](https://dl.dropbox.com/s/m5izwd1uqzkfta5/Screenshot%202015-11-16%2017.59.37.png)

How about that? It starts a tmux session, creates a window for the database, and another running the server and giving me a command line at the project directory.

## Adding Gas

So, tmuxinator is cool enough, but I stumbled on [a post][shellpost] that kicked it into high gear by creating a shell script for handling setup of other things that tmuxinator doesn't necessarily handle. This is a game changer. To take the tmuxinator concept and blow it out, I created a shell script that looks like this:

~~~

#!/bin/bash

dir=/Users/jdavis1002/Code/tippingapp
projectname = "Tipping"

atom $dir

toggl stop
toggl start $projectname

open /Applications/Robomongo.app
open https://github.com/jwd2a/tipping/issues
tmuxinator tipping

~~~

I stashed that file in `/.dotfiles/projectconfigs/tipping`, and symlinked my entire `/projectconfigs` directory to a directory on my PATH, and boom, we were in business.

Now, all I have to do is open a terminal, type `tipping`, and it does the following:

- Opens Atom (my editor) to the project directory
- Stops toggl from tracking any existing projects, and restarts for this one
- Opens Robomongo for monitoring/interacting with MongoDB
- Opens my github repo for the project to the issues
- Creates a tmux session with mongo running, the server running, and a command line I can use for managing git, etc. (all the stuff shown in the earlier section).

I definitely feel like this is a HUGE timesaver and momentum saver. Now, for each new project, I just create that config file, and off I go.

As an added bonus, I use [Alfred][alfred], so I can simply call up Alfred, type `> tipping`, and the entire environment is created. No need to even open the terminal first.

In the future, I'd like to expand the config to do more things. I'd love to open specific files in Indesign, open specific Slack teams, etc. The other missing piece is hooking up a window manager to the config as well - something like [Divvy][divvy] or [Slate][slate], to have it automatically do the layout of applications.

If you're looking to make your process of switching between projects easier and quicker, I definitely recommend looking into this method. It's definitely made a huge difference for me, and I can only imagine it'll get much better as I made the project configs more robust.

Got any tips or tricks to add? Do you use a system like this to help speed up switching between projects? Leave your thoughts in the comments!

[alfred]: https://www.alfredapp.com/
[divvy]: http://mizage.com/divvy/
[josh]: http://joshtronic.com
[shellpost]: http://blog.sayan.ee/quick-start/
[slate]: https://github.com/jigish/slate
[spool]: https://www.uie.com/brainsparks/2006/04/20/dividing-user-time-between-goal-and-tool/
[tmux]: https://tmux.github.io/
[tmuxinator]: https://github.com/tmuxinator/tmuxinator

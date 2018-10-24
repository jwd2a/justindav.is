---
layout: post
title: How to Push to Git from an Airplane
comments: true
---

Look, sometimes, you need to work wherever you can. I found myself in a similar
situation recently, cruising at 30,000ft, trying to ship some code for CrowdSync.
Connected to wifi (JetBlue's wifi is FANTASTIC), editing code was no problem.
However, when I went to push to git:

![Fatal Git push][fatal]

If you've ever had this happen, there's an easy solution. If you're using SSH,
chances are, the network you're connected to blocks the standard SSH port (22).
But, they'll likely have standard ports open, like 80 and 443. Lucky for us,
Github allows us to connect to a repo via SSL, instead of SSH.

So, if you want to push to Git while on a plane (or wherever you can't access
SSH):

- Grab your SSL URL for your repo. Do this by selecting "Use HTTPS" in the menu
  that the "Clone or download" button pops out:

<p class="text-center">
  <img src="/images/git-from-airplane/clone-menu.gif" alt="GitHub Clone Menu">
</p>

- Add a new remote with that URL:

```shell
git remote add nossh https://github.com/username/repository.git
```

- Start pushing and pulling to that remote, instead of the one you usually use,
  and boom, you're in business!

Hope this helps you in times where you need to push to Github, but you're
blocked for whatever reason. It's great on airplanes, and probably good for
other restricted scenarios as well.

Special thanks to [Josh][josh] for the tip on figuring this out!

(BTW - this post was also written and pushed to Git at 30K feet - putting our
money where our mouth is!)

![Successful Git Push][success]

[fatal]: /images/git-from-airplane/push-fatal.png
[success]: /images/git-from-airplane/push-success.png
[josh]: https://joshtronic.com

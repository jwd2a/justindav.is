---
layout: post
title: "How to Post to Private Slack Channels from Zapier"
summary: "If you automate posting to Slack via Zapier, you might need to post to
a private channel. It's not entirely obvious how to do it, but actually pretty
damn easy."
comment: true
---

[Zapier][zapier] is cool. We use it at [Crowdsync][cs] to automate a bunch of
things, oftentimes, needing to post to a private channel on Slack to deliver
some kind of notification. We've got a private support channel, and a private
monitoring channel, letting us know when support requests come in, or when new
users register, respectively.

When we first set this up, I was kinda bummed. It didn't look like Zapier would
let you post to private channels on Slack. But, some experimentation led to a
simple solution.

When setting up a Zap with Slack, first, set it up to send a channel message:

![channel message setup][channel]

Next, authorize your Slack account, or choose the one you want to use:

![slackaccounts][slackaccounts]

After you've done that, you'll setup this template. This is where you'll choose
the channel, but alas, I only see my public channels in the "Channel" list!

![channeldropdown][channeldropdown]

Here's the trick: 

**From this list, select "Use a Custom Value (advanced)":**

Then, in the box below that one, which says "Custom Value for Channel ID",
simply type in the name of your private channel:

![private][private]

Boom! You're in business! Go ahead and set the rest of the template up and give
it a test. You should now see your notifications coming into your private
channels!

Hope this helps you be more productive with Zapier and Slack!

[zapier]: https://zapier.com
[cs]: https://www.crowdsync.io
[channel]: https://dl.dropbox.com/s/depll6viwkjuoc3/Screenshot%202017-10-16%2011.00.56.png
[slackaccounts]: https://dl.dropbox.com/s/2qy8qlgva513eju/Screenshot%202017-10-16%2011.01.12.png 
[channeldropdown]: https://dl.dropbox.com/s/f3uvc5rc3mppf3l/Screenshot%202017-10-16%2011.01.34.png
[private]: https://dl.dropbox.com/s/ue7ljvf906iefcn/Screenshot%202017-10-16%2011.01.49.png


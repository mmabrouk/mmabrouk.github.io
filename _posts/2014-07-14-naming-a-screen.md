---
layout: post
title: (re)naming a screen session
analytics: true
category: screen
---
I have always had a hard time relocating my screens. I would start four or five of them at one time, detach them, the attach them one by one looking for the correct one. I realize now that that was stupid.

To create a new screen and name it myscreen, use

{% highlight bash %}
screen -S myscreen
{% endhighlight %}

To reattach it simply do

{% highlight bash %}
screen -r myscreen
{% endhighlight %}

Note here that you do not need to use the whole name that is schown when running screen -list (in other words, you do not need to use screen -r 12392.myscreen).

Other than that, you can also simply rename a screen by doing (Control-a :) while the screen is on to toggle the command mode, then write:

sessioname myscreen


I hope that was helpful


---
layout: post
title: Testing and debugging using IPython
---

## The Issue 
One issue I always had when debugging with IPython was the need to reload all my modules each time I make a change. It would be nice if modules could be reloaded automatically each time before running a command.

## The Solution:

Use autoreload, an IPython extension which automatically reloads modules before executing each line.

To use it run IPython the following commands:

{% highlight python %}
%load_ext autoreload
 
# Reloads all modules (except those excluded by %aimport) every time before executing the code
%autoreload 2

# Mark module 'module_foo' to not be autoreloaded
%aimport -module_foo

import my_class

my_function()
# outputs 1
# Let's say I change the code to make it the function returns 2

my_function()
# outputs 2
{% endhighlight %}

-----

Now you can easily test each part of your implementation in IPython online and with no trouble at all.

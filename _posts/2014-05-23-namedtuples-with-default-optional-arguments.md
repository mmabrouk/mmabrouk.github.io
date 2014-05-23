---
layout: post
title: Creating namedtuple classes with optional/default argument
analytics: true
category: Python
---

## The Issue 

Say you want to create a simple class for rectangles using named tuples:

{% highlight python %}
Rectangle = namedtuple("Rectangle", "length width color")
{% endhighlight %}

The issue is that you don't know the color of some of your rectangles, so you whish to set it to None or white per default.
Unfortunately namedtuples do not allow that, if you try,

{% highlight python %}
Rectangle(5,10)
{% endhighlight %}

You'll get the error:

TypeError: __new__() takes exactly 3 arguments (2 given)


## The Solution:

Create a subclass out of the namedtuple and override its __new__ method to allow optional parameters:

{% highlight python %}
class Rectangle(namedtuple('Rectangle', [ "length", "width", "color"])):
    def __new__(cls, length, width, color="white"):
        return super(TemplateContainer, cls).__new__(cls, length, width, color)
{% endhighlight %}

Now we can run

{% highlight python %}
r = Rectangle(5, 10)
print r.color
>> "White"
{% endhighlight %}

---
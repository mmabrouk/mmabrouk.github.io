---
layout: post
title: Iterating over the list of all combinations between elements of a list
---

## The Issue 
Did you ever had to compare all elements of a list and you had this ugly code:

{% highlight python %}
for elem_1 in my_list:
	for elem_2 in my_list:
		if elem_1 != elem_2:
			# Do Stuff
{% endhighlight %}

We're near the 80 charcter limit before even starting to write the main code.

## The Solution:

Use itertools.combinations(iterable, r). It's a function that creates tuples with length r (e.g. (x,x) for r=2, (x,x,x) for r=3 ...).

{% highlight python %}
from itertools import combinations
for (elem_1, elem_2) in combinations(my_list,2):
	# Do stuff

{% endhighlight %}
-----

Blessed be the negative programmer!

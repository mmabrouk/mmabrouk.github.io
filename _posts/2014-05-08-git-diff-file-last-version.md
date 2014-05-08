---
layout: post
title: Get difference to the last change in git
analytics: true
category: git
---
You've just pulled the last changes from your team's git repository, and, guess what, you find someone has changed the script you've been working on, and you ask yourself what did he change?
Or, your code is starting to behave in a different way than the last week and you ask yourself, what did I change?

To see the changes you can easily diff any file to an older version using git diff version_number filename. But who remembers the hash of the last version? (a note here, you don't have to use the whole hash, 
the first characters are sufficient). Well, in git HEAD^ point to the last version, HEAD^^ the one before...

E.g.:

{% highlight bash %}
git diff HEAD^ my_folder/my_script.py
git diff HEAD^^ my_folder/my_script.py
{% endhighlight %}

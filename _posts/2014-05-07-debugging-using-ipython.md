One of the fastest (and dirtiest) ways to debug a python script is to put a pdb.set\_trace() in the problematic code section, and debug the code on the command line.
Although useful, debugging this way is always a pain in the ass, there is no code completion, neither any of the advanced features of IPython.


Today I have discovered an extremely easy method to debug your code in an IPython terminal, simply add an 'i' to the 'pdb'; but first we have to install the ipdb package:

{% highlight bash %}
python -m easy_install ipdb
{% endhighlight %}

Then we simply swap the import pdb and the pdb.set\_trace() with import ipdb and ipdb.set\_trace()

{% highlight python %}
import ipdb
# Do Stuff
ipdb.pdb.set_trace()
{% endhighlight %} 

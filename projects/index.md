---
layout: page
title: Projects
permalink: /projects/
---

# Projects

This is a test placeholder for projects.

With an in-line code sample:

{% highlight python linenos %}
class Student(object):
    def __init__(self, args, kwargs):
        self.__id = None

    @property
    def id(self):
        return self.__id

    @id.setter
    def id(value):
        self.__id = value

{% endhighlight %}

[Link to HN](https://news.ycombinator.com)

[Link to about]({{ site.baseurl }}{% link about.md %})

[Link to OG blog]({{ site.baseurl }}{% post_url 2016-04-05-inspiration-and-the-lack-thereof %})

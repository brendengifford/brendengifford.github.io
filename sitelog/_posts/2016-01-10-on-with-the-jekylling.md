---
layout: post
title:  "On with the jekylling"
date:   2016-01-10
category: sitelog
---

Well alright, had to jump through some hoops to get this stuff working on github. Sadly, haven't figured out how move the posts to their own folder yet. Had some other problems with the syntax highlighter not building. Just an overall pain - but it's kind of fun, is that masochistic?

So, I think I found out how to show jekyll code in jekyll -- does this work??

{% highlight html %}
{% raw %}
{% for post in site.posts %}
{% if post.categories contains '<categoryname>' %}
    <h2>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </h2>
{% endif %}
{% endfor %}
{% endraw %}
{% endhighlight %}
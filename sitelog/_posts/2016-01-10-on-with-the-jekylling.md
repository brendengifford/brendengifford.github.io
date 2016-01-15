---
layout: post
title:  "On with the jekylling"
date:   2016-01-10
category: sitelog
---

Well alright, had to jump through some hoops to get this stuff working on github. Sadly, haven't figured out how to move the posts to their own folder yet. Had some other problems with the syntax highlighter not building. Just an overall pain - but it's kind of fun, is that masochistic?

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

Nice. Can I show you how I did it? lol no, that'd be a bit much. You use a {% raw %} {% raw %} {% endraw %} does that even work? Kind of, need an endraw on there too, then wrap in {% raw %} {% highlight %} {% endraw %} -- you can figure it out!

Yay for this [stackoverflow question][stackoverflow-question1]!

Okay, also figured out the folders thing, instead of `/_posts/folder/`, it has to be `/folder/_posts/`. Sheesh! Actually, makes sense. 

What's next? Oh wait, allow me to finally present the code for how to put an image into jekyll from your `/img/` folder:

{% highlight liquid %}
{% raw %}
![The view out of my window]({{ site.url }}/img/out-my-window.jpg)
{% endraw %} 
{% endhighlight %}

Siiiiiiiiiiiiiiick.

Oh, just found out you can add line numbers

{% highlight liquid linenos %}
{% raw %}
{% highlight ruby linenos %}
def foo
  puts 'foo'
end
{% endhighlight %}
{% endraw %}
{% endhighlight %}

hehe close enough?

how about something easier

{% highlight js linenos %}
$(document).ready(function() {
  if ($('.seen').is(':visible')) {
    alert('your presence is known!');
  }
  else {
    alert('nothing to see here, move along.');
  }
});
{% endhighlight %}

lol no, it worked right, it's just the stupid css rule on it I think. Who sets `overflow:scroll`?? I'm about to fix it and you'll have no idea what I'm talking about.

Okay, close enough. Could still do with some better styling, but at least there aren't scroll bars within scroll bars.

So, in the [last post][last-post] I mentioned [figuring out the live reload][live-reload].

*climbs out of deep dark hole*

**Did it work?**

It appears to be working! I can't believe it! Props to this [stackoverflow question][stackoverflow-question2] for finally giving me a working method. I have to run two command prompts, `jekyll server` in one, and in the other, `bundle exec guard` (with live reload in the Guardfile). Woof. What a pain. Looks like [using grunt to set up live reload][live-reload2] might have been a better way to go -- just so I could do it with one command pompt. Maybe I'll refactor later. 

###Things I'd like to do.

- Create a page of usefull links
- Overhaul styles -- maybe bootstrap? HTML5 Boilerplate?
- Alias my domain
- Rebrand (bren.codes)

Here's a couple links I'm thinking of for a 'useful links' page

- [Liquid](https://github.com/Shopify/liquid/wiki)
- [markdown-syntax](http://daringfireball.net/projects/markdown/syntax)
- [highlight-languages](https://github.com/jneen/rouge/wiki/List-of-supported-languages-and-lexers)

---

**Unrelated**

Here's the subreddits I'm subbed to:

  - [7daystodie](https://www.reddit.com/r/7daystodie/)
  - [AnimalsBeingJerks](https://www.reddit.com/r/AnimalsBeingJerks/)
  - [announce](https://www.reddit.com/r/announcements/)
  - [apple](https://www.reddit.com/r/apple/)
  - [ArtefactPorn](https://www.reddit.com/r/ArtefactPorn/)
  - [AskReddit](https://www.reddit.com/r/AskReddit/)
  - [askscience](https://www.reddit.com/r/askscience/)
  - [aww](https://www.reddit.com/r/aww/)
  - [bestof](https://www.reddit.com/r/bestof/)
  - [bicycletouring](https://www.reddit.com/r/bicycletouring/)
  - [bicycling](https://www.reddit.com/r/bicycling/)
  - [bikecommuting](https://www.reddit.com/r/bikecommuting/)
  - [chess](https://www.reddit.com/r/chess/)
  - [CommercialCuts](https://www.reddit.com/r/CommercialCuts/)
  - [CrazyIdeas](https://www.reddit.com/r/CrazyIdeas/)
  - [CyclePDX](https://www.reddit.com/r/CyclePDX/)
  - [drunk](https://www.reddit.com/r/drunk/)
  - [firstworldanarchists](https://www.reddit.com/r/firstworldanarchists/)
  - [funny](https://www.reddit.com/r/funny/)
  - [Futurology](https://www.reddit.com/r/Futurology/)
  - [gaming](https://www.reddit.com/r/gaming/)
  - [geek](https://www.reddit.com/r/geek/)
  - [gifs](https://www.reddit.com/r/gifs/)
  - [Graffiti](https://www.reddit.com/r/Graffiti/)
  - [HistoryPorn](https://www.reddit.com/r/HistoryPorn/)
  - [humor](https://www.reddit.com/r/humor/)
  - [IAmA](https://www.reddit.com/r/IAmA/)
  - [interestingasfuck](https://www.reddit.com/r/interestingasfuck/)
  - [iphone](https://www.reddit.com/r/iphone/)
  - [Jokes](https://www.reddit.com/r/Jokes/)
  - [listentothis](https://www.reddit.com/r/listentothis/)
  - [mildlyinteresting](https://www.reddit.com/r/mildlyinteresting/)
  - [movies](https://www.reddit.com/r/movies/)
  - [Music](https://www.reddit.com/r/Music/)
  - [news](https://www.reddit.com/r/news/)
  - [NoSillySuffix](https://www.reddit.com/r/NoSillySuffix/)
  - [oregon](https://www.reddit.com/r/oregon/)
  - [OutOfTheLoop](https://www.reddit.com/r/OutOfTheLoop/)
  - [PCMasterRace](https://www.reddit.com/r/pcmasterrace/)
  - [pics](https://www.reddit.com/r/pics/)
  - [politics](https://www.reddit.com/r/politics/)
  - [Portland](https://www.reddit.com/r/Portland/)
  - [ProgrammerHumor](https://www.reddit.com/r/ProgrammerHumor/)
  - [programming](https://www.reddit.com/r/programming/)
  - [sca](https://www.reddit.com/r/sca/)
  - [science](https://www.reddit.com/r/science/)
  - [Showerthoughts](https://www.reddit.com/r/Showerthoughts/)
  - [soccer](https://www.reddit.com/r/soccer/)
  - [streetart](https://www.reddit.com/r/streetart/)
  - [StreetArtPorn](https://www.reddit.com/r/StreetArtPorn/)
  - [talesfromtechsupport](https://www.reddit.com/r/talesfromtechsupport/)
  - [technology](https://www.reddit.com/r/technology/)
  - [timbers](https://www.reddit.com/r/timbers/)
  - [todayilearned](https://www.reddit.com/r/todayilearned/)
  - [trees](https://www.reddit.com/r/trees/)
  - [TrueReddit](https://www.reddit.com/r/TrueReddit/)
  - [TrueTrueReddit](https://www.reddit.com/r/TrueTrueReddit/)
  - [ussoccer](https://www.reddit.com/r/ussoccer/)
  - [videos](https://www.reddit.com/r/videos/)
  - [wheredidthesodago](https://www.reddit.com/r/wheredidthesodago/)
  - [woahdude](https://www.reddit.com/r/woahdude/)
  - [worldnews](https://www.reddit.com/r/worldnews/)

Well, I guess using html in markdown breaks everything, eh?
Cool, re-did them in markdown.

<!--links-->

[stackoverflow-question1]: 	http://stackoverflow.com/questions/20568396/how-to-use-jekyll-code-in-inline-code-highlighting
[stackoverflow-question2]:	http://stackoverflow.com/questions/8395526/using-live-reload-with-jekyll


[live-reload]: 				http://dan.doezema.com/2014/01/setting-up-livereload-with-jekyll/
[live-reload2]: 			http://kctang.github.io/jekyll/livereload/2014/01/25/github-pages-with-jekyll-and-livereload.html/
[last-post]: 				{% post_url 2016-01-09-im-back %}
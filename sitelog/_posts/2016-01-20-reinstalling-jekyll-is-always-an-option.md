---
layout: post
title:  "Reinstalling Jekyll is Always an Option"
date:   2016-01-20
category: sitelog
---

I thought it was all over. I was having some trouble getting the site to build on GitHub even though it was building fine on my computer, so I installed the [github pages gem][gh-pages-gem], thinking that would clean stuff up. I'm not sure if that's what started the trouble, but soon after that the site wasn't building. It was complaining that it didn't have a gem called kramdown, but it did have kramdown! I tried googling the error like any normal person only to find weak suggestions like using `bundle exec jekyll build` (actually, good suggestion, but it didn't help). 

I uninstalled kramdown. I reinstalled kramdown -- nothing. I wiped my repo and got a fresh pull from remote -- still wouldn't build. Finally I went through and deleted every gem I had and reinstalled Jekyll. It built! I ran `bundle install` -- fucking deleted bundler by accident. Installed bundler and ran it again. *Failed*. Ugh. Then I realized I could have deleted all of the gems by removing them from them gemfile and running `bundle clean`. So that's what I did. Then I re-added stuff one at a time until my gemfile looked like this:

{% highlight javascript %}
	source "https://rubygems.org"
	gem "jekyll"
	gem "guard"
	gem "guard-livereload"
	gem "wdm", ">= 0.1.0" if Gem.win_platform?
{% endhighlight %}

Now everything is hunkydory and everything will work when I press `Ctrl-S`... Right?

[gh-pages-gem]: https://github.com/github/pages-gem
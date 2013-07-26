---
layout: post
title: List all git branches, most recently updated first
---

{% highlight bash %}
$ git config alias.ls "for-each-ref --sort=-committerdate refs/heads/ --format='%(committerdate:short) %(refname:short)'"
$ git ls
{% endhighlight %}

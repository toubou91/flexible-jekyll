---
layout: post
title:  "How to sync a fork"
date:   2018-02-25 20:00 +0200
comments: true
tags: [git, how-to, fork, sync]
img: git-logo.png
---

### 1. Introduction
So, you forked a repo, started working on it (or just forgot it there because you also had other stuff to take care of 😂😂️). The parent fork continued evolving and you ended up at point where you want to also update your fork with the last HEAD of the parent,

### 2. Use Case
Next month [Utrecht Java User Group](https://www.meetup.com/Utrecht-Java-User-Group/) hosts...one of its co-organizers :bowtie: , Sendil Kumar N, who's gonna give a talk about [JHipster](http://www.jhipster.tech), so, I thought about taking a look at it, before the meetup, in order to educate myself a bit. However, after some time I ended up playing with its [Kotlin porting](https://github.com/jhipster/jhipster-kotlin), which is still a WIP (for the ones who are interested in contributing :smiley:

The latter implies that it is often updated, so locally, today I still had this in my HEAD:

![first]({{site.baseurl}}/assets/img/25-02-18/local-old.png)

Whereas, remotely, this was the latest update of the day:

![second]({{site.baseurl}}/assets/img/25-02-18/remote-new.png)

So, **my fork was behind** .

How could I easily update it according to the latest HEAD of the parent?

### 3. Solution

First, check your local's **remote** references:

![third]({{site.baseurl}}/assets/img/25-02-18/local-remote-1.png)

Ok, it only contains my fork, so, I have to also add the parent as an `upstream`:

```
$ git remote add upstream https://github.com/jhipster/jhipster-kotlin
```

Let's confirm it was added:

![fourth]({{site.baseurl}}/assets/img/25-02-18/local-remote-2.png)

Time for [magic](https://github.com/thodorisbais/dotfiles/blob/master/usr/local/bin/sync-fork)!!!

![fifth]({{site.baseurl}}/assets/img/25-02-18/sync-fork.png)

### 4. References

- [Configuring a remote for a fork](https://help.github.com/articles/configuring-a-remote-for-a-fork/)
- [Changing a remote's URL](https://help.github.com/articles/changing-a-remote-s-url/)
- [My dotfiles](https://github.com/thodorisbais/dotfiles)

### 5. Closing quote

> The more you practice, the easier it becomes.
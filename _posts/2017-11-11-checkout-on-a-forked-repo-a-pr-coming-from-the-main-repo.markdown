---
layout: post
title:  "How to checkout (on a forked repo) a Pull Request coming from the main repo?"
date:   2017-11-11 18:00 +0200
comments: true
tags: [git, pull-request]
img: git-logo.png
---

### 0. Introduction
By reading the [related question on StackOverflow](https://stackoverflow.com/questions/47218516/how-to-checkout-on-a-forked-repo-a-pull-request-coming-from-the-main-repo), you can get a very first understanding of today's topic.

### 1. Situation
[As I mentioned in an earlier post](https://toubou91.github.io/hi-again/), I am using [flexible-jekyll](https://toubou91.github.io/hi-again/) for this blog, which implies that I am working on the forked version of the main project from [artemsheludko](https://github.com/artemsheludko).
So, I have [opened an issue on the main project](https://github.com/artemsheludko/flexible-jekyll/issues/7), regarding the possibilities of having post thumbnails for twitter, facebook, etc., which by the way, I find really important.
[kentonh](https://github.com/kentonh) [opened a pull request](https://github.com/artemsheludko/flexible-jekyll/pull/11) which seemed to resolve this issue, so I really wanted to test this locally, because I couldn't wait for at all 😋 🔜

### 2. Solution
First, we check what we currently have:

![first]({{site.baseurl}}/assets/img/11-11-17/1.png)

We then have to add a new entry to map the parent project from Artem:

![second]({{site.baseurl}}/assets/img/11-11-17/2.png)

We should be good to go now:

![third]({{site.baseurl}}/assets/img/11-11-17/3.png)

Or **NOT**?

![fourth]({{site.baseurl}}/assets/img/11-11-17/4.png)

Of course NOT! Till now, what we have been doing, was only about managing branches.
In order to be able to checkout a Pull Request, we have to add the following line, in our .git/config :

```shell
fetch = +refs/pull/*/head:refs/remotes/origin/pr/*
```

So, after that my upstream reference looks like this:

![fifth]({{site.baseurl}}/assets/img/11-11-17/5.png)

I should now be able to finally fetch the PR, right?

![sixth]({{site.baseurl}}/assets/img/11-11-17/6.png)

Yes, we got it!!!
We should be able to check it out using this git command:

```shell
git checkout origin/pr/11
```

Right?

![seventh]({{site.baseurl}}/assets/img/11-11-17/7.png)

YES!!!

### 3. Closing Quote
> If it hurts, do it more often.
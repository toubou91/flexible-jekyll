---
layout: post
title:  "Executing git commands on a different directory"
date:   2017-09-30 22:40 +0200
comments: true
tags: [how-to, git]
img: git-logo.png
---
### 1. The Problem
So, you are on a specific directory, but would like to execute a git command on a different one.
I don't know whyl for me, it's just only that I'm lazy.

### 2. The Solution
Here is your command's format:
```git
git -C [directory] [git_command]
```

And here is a screenshot to make things more clear:

![Git command different dir]({{site.baseurl}}/assets/img/git-command-different-dir.png)

### 3. The Reference
For further reference, you can consult [this](https://stackoverflow.com/a/20115753/2486904) StackOverflow thread.

Cheers!

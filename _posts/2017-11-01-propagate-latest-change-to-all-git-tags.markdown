---
layout: post
title:  "Propagate latest change to all git tags?"
date:   2017-11-01 20:25 +0200
comments: true
tags: [git, thoughts]
img: git-logo.png
---
### 1. Situation
Sometimes you have to perform a hotfix release, which essentially means that you have to checkout a specific (old) tag and perform some changes over there. However, there is a case that there are other changes that need to be applied also, since the codebase has been updated from the time of that specific tag and there are new dependencies between classes, new external dependencies, etc.

### 2. Workaround
Cherry-picking usually comes to the rescue for such cases.

### 3. Thoughts
Wouldn't it be nice if we came up with a solution that automatically propagates a specific commit from the master branch to all existing/remote tags?
Because you know, you might sometimes miss a specific cherry-picking and despite the fact that your project compiles and runs successfully, there might be a specific use-case scenario that you missed and the reasoning behind this is probably that something went wrong while cherry-picking.

On the other hand, as it happens with cherry-picking, it might not always be that easy to propagate a single change to all your branches, just for the same reason I fore-mentioned (codebase has changed quite a lot since that version and you need to manually make the changes), so, maybe, what I'm thinking about is just daydreaming :bowtie:

In any case, I thought I'd share.

Cheers!
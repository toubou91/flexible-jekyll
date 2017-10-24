---
layout: post
title:  "How to make a day last for 26 hours"
date:   2017-10-19 22:40 +0200
comments: true
tags: [thoughts, java, fun]
img: java-logo.jpg
---
You know, it was one of these weird days that I start doing open-source and hop to hop I end up with meaningless ideas. One of these was the [god-requests](https://github.com/toubou91/god-requests) repo.
Till now, I have only "submitted" 1 request (feel free to also contribute to this meaningless effort :-P ), which is about making a day last for 26 hours:

![26-hours]({{site.baseurl}}/assets/img/day-with-26-hours.png)

It seems, though, that Java already provides such a solution:

```java
Calendar.add(Calendar.HOUR, 26);
```

Problem solved!

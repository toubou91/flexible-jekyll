---
layout: post
title:  "GitHub bug"
date:   2017-01-24 21:00 +0200
comments: true
img: software.jpg
categories: [social]
---
<h1>Situation</h1>
Today, on a Windows machine, I was about to create a new issue in GitHub.

<em>We have a saying in Greece: "1 picture = 1000 words", so, I always try to provide visual representation of such technical situations, when possible.</em>

In today's case, it was enough if I just provided a screenshot, 'cause it perfectly depicted the erroneous situation. So, being lazy as always, I just use the preinstalled [Snipping Tool](http://www.digitalcitizen.life/how-use-snipping-tool) from Windows to work around capturing a snapshot of a part of my screen and copied the snapshot to clipboard, using the "copy" button that Snipping Tool provides:

![Copy button]({{ site.url }}/assets/snip_copy.png){: .center-image }

Following step is obvious: navigating to the github issue I am about to open/create and ```Ctrl+V```.
I then thought I had some remnants of a previous paste, which was wrong in my opinion, so I had to first delete the pasted from clipboard snapshot and hit again ```Ctrl+V```. Hitting "Delete" is an extra button and I fore-mentioned I'm lazy, so I just selected all the contents of the text area (```Ctrl+A```) and instantly tried to replace them with my clipboard (```Ctrl+V```):
![](https://i.gyazo.com/8e547b492eab5767261f42956606fdac.gif)

Boom! A cat is killed! Previously added contents are added on top of the latest pasted content.

<em>Too minor, but I thought I'd share, in case GH support ends up here sometime.</em>

<h4>Closing Quote</h4>
> Motivation starts when you start working on your long-term goals.

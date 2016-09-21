---
layout: post
title: How to remove the border of a JFrame
date: 2014-01-31 00:59
author: toubou91
comments: true
categories: [java, JFrame, Programming, swing]
---
<div dir="ltr" style="text-align:left;"><div dir="ltr" style="text-align:left;">Assuming that you 're developing an application, in which the default look-and-feel doesn't match, at all.<br /><br />To be more specific, imagine the following example: I sometime wanted to develop a real-time clock JAVA application. It would be a bit ugly for the application's purpose to have the annoying border around its JFrame.<br /><br />Indeed, there is a way to implement this: you just need to set the frame's undecorated method to true:    <code><span style="color:red;">frame.setUndecorated(true);</span></code><br /><code><br /></code><b>Keep in mind that the above code has to be placed before frame's</b> <code>setVisible()</code> <b>method</b>. Otherwise, it's like initializing the frame and then telling it to be undecorated, sth that doesn't make sense. <b> So, you first customise the frame as you wish (undecorization, etc) and then you enable its visibility</b>.</div><i><br /></i><i style="background-color:#f4cccc;">The full application that supports this post is related <a href="https://github.com/toubou91/DigitalClock" target="_blank">here</a>.</i></div>

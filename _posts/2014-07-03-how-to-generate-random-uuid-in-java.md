---
layout: post
title: How to generate random UUID in Java
date: 2014-07-03 11:59
author: toubou91
comments: true
categories: [java, Programming, UUID]
---
Hi there!  Generating a random UUID is much more easier than you could ever imagine! I use the following block of code, whenever I'm in a need of more than ten:  <pre class="brush:java"><br />for(int i = 0; i &lt; 30; i++) {<br />   System.out.println(UUID.randomUUID());<br />}<br /></pre> <i>If things get difficult and time passes, working with UUIDs, you 'll probably get lost, if the way you chose to generate your UUID was "a bunch at a time", like above, so you could either visit a site, like <a href="http://www.famkruithof.net/uuid/uuidgen">this</a> or modify your program like below:</i> <pre class="brush:java"><br />   System.out.println(UUID.randomUUID());<br /></pre> Cheers!

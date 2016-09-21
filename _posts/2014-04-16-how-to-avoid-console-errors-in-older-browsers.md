---
layout: post
title: How to avoid console errors in older browsers
date: 2014-04-16 22:53
author: toubou91
comments: true
categories: [javascript, Programming]
---
<pre class="brush:javascript;"><br />    <br />        if (!window.console)<br />            window.console = {};<br />        if (!window.console.log)<br />            window.console.log = function() {<br />            };<br />        if (!window.console.debug)<br />            window.console.debug = function() {<br />            };<br />    <br /></pre>

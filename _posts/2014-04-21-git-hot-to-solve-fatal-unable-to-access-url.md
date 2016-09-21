---
layout: post
title: Git&#58; Hot to solve fatal&#58; unable to access [url]
date: 2014-04-21 12:01
author: toubou91
comments: true
categories: [git, github, Tools]
---
<div dir="ltr" style="text-align:left;">So today, while trying to push the latest <a href="https://github.com/toubou91/JavaCodeGeeks_examples/tree/master/PanelGridJSF" target="_blank">commit</a> for my <a href="http://examples.javacodegeeks.com/enterprise-java/jsf/message-and-messages-example-with-jsf-2-0/" target="_blank">last</a> JSF tutorial <a href="http://stackoverflow.com/questions/7438313/pushing-to-git-returning-error-code-403-fatal-http-request-failed" target="_blank">here</a>, I got an error like this:<br /><br /><code>fatal: unable to access 'https://github.com/toubou91/JavaCodeGeeks_examples.git/': SSL read: error:00000000:lib(0):func( 0):reason(0), errno 10054</code><br /><br />After a small investigation, I found myself reading <a href="http://stackoverflow.com/questions/7438313/pushing-to-git-returning-error-code-403-fatal-http-request-failed" target="_blank">this</a> thread but the question persisted, as I knew that I had configured properly both my local repo's <code>.git</code> and git's <code>.config</code> file, so I tried pinging my remote repo from a browser.<br /><br />I noticed that I was prompted to insert my account's credentials (so the reason was that I have been logged out from my remote repo and the local push couldn't match the destination).<br /><br />After signing-in again, <code>git push</code> succeeded!<br /><br />Cheers!<br /><br /></div>

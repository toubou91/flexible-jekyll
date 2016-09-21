---
layout: post
title: How to create a MySQL database with default encoding and collation
date: 2014-06-30 12:21
author: toubou91
comments: true
categories: [MySQL, Programming]
---
<div dir="ltr" style="text-align:left;">Hi there, pretty much time since my last post (and I 'll apologise in a future post)!  <br /><br />During the project that I was exposed to, to the company I work for, the last months' google searches resulted finding myself with the difficulty to reach a solution for <b>creating a database with default encoding/character set and collation</b>, so I decided to write this post, when finding some free time.  <br /><br />Assuming that we want to create a MySQL database from command line, with default encoding and collation, the command should look something like this, in a generic format:  <br /><pre class="brush:sql">CREATE DATABASE [preferred_database_name] DEFAULT CHARACTER SET [preferred_encoding] DEFAULT COLLATE [preferred_collation];<br /></pre><br />More specifically, if I would like to create a database named <code>test_db</code>, with the default encoding of <code>utf8</code> and default collation of <code>utf8_general_ci</code>, the generic format, easily converts into:  <br /><pre class="brush:sql">CREATE DATABASE test_db DEFAULT CHARACTER SET utf8 DEFAULT COLLATE utf8_general_ci;<br /></pre> <div class="separator" style="clear:both;text-align:center;"><a href="https://thodorisbais.files.wordpress.com/2014/06/dcf1d-mysql_database_creation.png" style="margin-left:1em;margin-right:1em;"><img border="0" src="https://thodorisbais.files.wordpress.com/2014/06/dcf1d-mysql_database_creation.png?w=300" /></a></div> <br />Pretty easy, huh?! Have a nice week!</div>

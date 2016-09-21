---
layout: post
title: How to change the default installation directory in Windows
date: 2015-04-11 15:34
author: toubou91
comments: true
categories: [OS, registry, windows]
---
<div dir="ltr" style="text-align:left;"><br /><h2>1. The problem</h2>I've got a partitioned ultrabook, where OS is installed in the <b>C:\</b> drive. That is, my <b>C:\</b> drive has a small amount of available GBs, so, each time I want to install a new software, I have to manually change the setup wizard's default directory ( <b>C:\Program Files\</b> ) to my <b>D:\</b> drive.  <br /><h2>2. The solution</h2>In order to change the default installation directory for a Windows machine, we have to modify its <a href="http://windows.microsoft.com/en-us/windows-vista/what-is-the-registry" rel="nofollow" target="_blank">registry</a>:  <br /><ul><li><b>Start</b> -&gt; <b>Run</b>, type <pre class="brush:bash"> %systemroot%\syswow64\regedit</pre> and hit <b>OK</b>. <br /><br /><div class="separator" style="clear:both;text-align:center;"><a href="https://thodorisbais.files.wordpress.com/2015/04/e7bef-1.png" style="margin-left:1em;margin-right:1em;"><img border="0" src="https://thodorisbais.files.wordpress.com/2015/04/e7bef-1.png?w=300" /></a></div></li></ul><ul><li> Navigate to <code>HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion</code> and change the highlighted variables (right-click -&gt; <b>Modify</b>) with the desired ones:  </li></ul><div class="separator" style="clear:both;text-align:center;"><a href="https://thodorisbais.files.wordpress.com/2015/04/e76da-3.png" style="margin-left:1em;margin-right:1em;"><img border="0" src="https://thodorisbais.files.wordpress.com/2015/04/e76da-3.png" height="72" width="400" /></a></div><div><br /></div>Enjoy! </div>

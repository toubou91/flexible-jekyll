---
layout: post
title: Open source contribution on DevIT site
date: 2016-03-28 14:42
author: toubou91
comments: true
categories: [css, Front-end, github, jquery, Open Source]
---
<h2>1. Preface</h2>
Well, it's been a while since my last blog post and honestly, many things changed.
<h3>1.1 Transferred blog to WP</h3>
First of all, according to the blog: it has been transferred from <a href="https://www.blogger.com/home" target="_blank">blogspot</a> to <a href="https://wordpress.com/" target="_blank">WordPress</a> and ooh, although I have spent a lot of time trying to configure it properly, it still seems that there is no "custom" future for it. So what? Migrating again to wordpress.org? No, no, no. If it has to be more customization effort on the ground, I would definitely go for <a href="https://jekyllrb.com/" target="_blank">Jekyll</a> (and yes, DevIT site is made of Jekyll :-) ), as I at least see the following advantages:
<ul>
	<li>Less effort required for customizing it.</li>
	<li>The effort spent for customizing it indeed worths it, as it's nearer to my personal interests (open-source, front-end tools) and involves a bit of programming.</li>
</ul>
<h3>1.2 Relocated to the Netherlands</h3>
The main reason that Ι was inactive for a while is my relocation to the Netherlands. For now, I won't provide any feedback on this, as I am waiting the end of year, where I will post my annual review and I will surely have a more genuine opinion for both sides.
<h2>2. DevIT Conference 2016 contribution</h2>
Having had the opportunity for a "long weekend" (yesterday Easter was celebrated here, so, today is an official day-off under the name of "Easter Monday"), I decided to make a small contribution to open-source: this time, for the <a href="http://devitconf.org/" target="_blank">DevIT Conference 2016</a> site.
<h3>2.1 The major issue</h3>
Let's make a visual comparison first, to understand the problem/issue before providing its lectical description.
First, here is an animated screenshot of a last year's speaker, <a href="https://mathiasbynens.be/" target="_blank">Mathias Bynens</a>, a professional I admire a lot and met in person in last year's event, on occasion of the fact that we both contributed on the <a href="https://github.com/peric/GetCountries" target="_blank">GetCountries</a> project:

[caption id="attachment_143" align="aligncenter" width="286"]<img class="wp-image-143 size-full" src="https://thodorisbais.files.wordpress.com/2016/03/mathias.gif" alt="Figure 1. Speakers' contacts visible only on hover" width="286" height="556" /> Figure 1. Speakers' contacts visible only on hover[/caption]

That is, it would be far way better to have the speaker's social contacts visible by default, without having to hover over the specific speaker's panel to see them.
<h3>2.2 The procedure</h3>
So, how to do it with not so much experience on css? Two words:
<ol>
	<li><a href="https://addons.mozilla.org/en/firefox/addon/firebug/" target="_blank">Firebug</a></li>
	<li><a href="http://astrogrep.sourceforge.net/" target="_blank">Astrogrep</a></li>
</ol>
<em>Ok, there is a third word, too, that matches your favourite editor, but the above two make the difference for a small change like the one explained today.</em>

Inspecting a speaker's panel revealed something good :

[caption id="attachment_144" align="aligncenter" width="638"]<img class="wp-image-144 size-full" src="https://thodorisbais.files.wordpress.com/2016/03/firebug.png" alt="Figure 2. Inspect speaker's element" width="638" height="133" /> Figure 2. Inspect speaker's element[/caption]

The <code>speaker-contacts</code> class. Next step? Performed a proper search with Astrogrep:

[caption id="attachment_145" align="aligncenter" width="800"]<img class="wp-image-145 size-full" src="https://thodorisbais.files.wordpress.com/2016/03/astrogrep.png" alt="Figure 3. Searching for &quot;speaker-contacts&quot; occurences" width="800" height="600" /> Figure 3. Searching for "speaker-contacts" occurences[/caption]

The occurence on <code>responsive.css</code> file seemed to be ok, but also revealed something more: the <code>speaker-active</code> class, which by its turn made me think of a possible jQuery manipulation for displaying/hiding the speaker's contacts, on hover.

So, as a first step, the removal for all the occurences of the <code>speaker-active</code> class on both <code>style.css</code> and <code>responsive.css</code> files, was required and to be more specific, here is the offensive line, that made the transition to happen:

<code>.speaker.active .speaker-info { margin-bottom: 50px; margin-top: -50px; }</code>

But still, the fore-mentioned changes weren't enough, as they ended up hiding the speakers' contacts panel:

[caption id="attachment_146" align="aligncenter" width="1080"]<img class="wp-image-146 size-full" src="https://thodorisbais.files.wordpress.com/2016/03/hidden-panel.png" alt="Figure 4. Things didn't go as expected" width="1080" height="409" /> Figure 4. Things didn't go as expected[/caption]

Why? Because the <code>speaker-contacts</code> class (<code>style.css</code>) defined the <code>position</code> property with a value of <code>absolute</code>, which means, that the specified element (speaker's contacts panel) was positioned relative to its first positioned (not static) ancestor element (speaker's info panel), which lead to an overlap between those two, after the previous change.

<em>Nonetheless, it worked perfectly (with <code>position: absolute</code>) before my change and the reason is that , prior to this, there was a transition of the speaker's contacts panel to the bottom of its parent (speaker's info panel), on mouse hover, That is, using the <code>absolute</code> value for the <code>position</code> property, just placed the contacts panel where it should, by taking into account the existence (or not) of the <code>speaker-active</code> class, too.</em>

So, just changing the value to <code>position: !absolute</code> provided a working solution:

[caption id="attachment_147" align="aligncenter" width="255"]<img class="wp-image-147 size-full" src="https://thodorisbais.files.wordpress.com/2016/03/soledad.png" alt="Figure 5. Speakers' contacts always visible" width="255" height="570" /> Figure 5. Speakers' contacts always visible[/caption]

Truth is, that using the negative operator is not a good solution, but on this case, I believe it was better, in comparison to setting the property's value to either <code>static</code> or <code>initial</code>, as for our case, both of them do not make so much sense.
<h3>2.3 Cleaning up the neighborhood</h3>
Ok, problem solved, but didn't we talk about a guess (jQuery manipulation of the speakers' contacts panel)? Yes, walking again around with Firebug's inspector, one might see that on hover of the speaker's div, the respective script is:

<code>$(this).toggleClass("active");</code>

So, again, same procedure with Astrogrep and removing the entire function:
<pre class="brush:js">// Speakers
$(function () {
  var speaker = $(".speaker");
  speaker.hover(function () {
  $(this).toggleClass("active");
 });
});
</pre>
<h2>3. Conclusions</h2>
More a come-back post, rather than a super-solution.
An easy task for the majority of front-end and full-stack devs, in general, but a good step for me to their world, as, except from the common tools that I have already had some exposure on (Grunt, npm, bower), this one also included <a href="http://bundler.io/" target="_blank">bundler</a>.

My commit can be found <a href="https://github.com/skgtech/devit/pull/174/commits/7574d9a93f91ab8a0501805169f7d9a7af1f280c" target="_blank">here</a> and I will be more than happy to receive any feedback.

&nbsp;

Have fun!

---
layout: post
title:  "div styled spans"
date:   2016-11-18 00:53 +0200
comments: true
categories: [front-end, css]
---
<h1>Situation</h1>
Someone is totally amateur to front-end stuff, but likes a lot this totally new process of learning.

I am in React and I wanna create a small header-like thingy, without using any <code>table</code> tag. 
So, only divs, but wouldn't it be better just for readability purposes to use a [```span```](https://developer.mozilla.org/en/docs/Web/HTML/Element/span) for every header itself and then wrap them all together around a <code>div</code> ?

Yeah, better, so, I end up like this:

```html
<div> 
  <span>Header 1</span> 
  <span>Header 2</span> 
  <span>Header 3</span> 
</div>
```

Of course, I have a CSS like below for my spans:

```css
span {
  width: 30%;
}
```

Correct? Could be, if ```<span>``` wasn't an inline container.
That is, this one will just ignore the specified ```width``` in our css file and place every ```span``` next to each other.
What about mimicing the behavior of a [```div```](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div)?

Yeah, inline-block!

<p data-height="265" data-theme-id="0" data-slug-hash="bBBKed" data-default-tab="html,result" data-user="toubou91" data-embed-version="2" data-pen-title="bBBKed" class="codepen">See the Pen <a href="https://codepen.io/toubou91/pen/bBBKed/">bBBKed</a> by Thodoris Bais (<a href="http://codepen.io/toubou91">@toubou91</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="https://production-assets.codepen.io/assets/embed/ei.js"></script>



<h4>Closing Quote</h4>
> Mistakes are for braves.

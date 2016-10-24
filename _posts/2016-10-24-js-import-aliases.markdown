---
layout: post
title:  "Import same-named classes from different libraries"
date:   2016-10-24 20:53 +0200
comments: true
categories: [javascript, reactjs]
---
<h1>The problem</h1>
Import same named classes from differenet modules

<h3>Use case</h3>
Someone was investigating the already existing solutions for bar graphs, so, at some point, he wanted to test in the same page two different bar chart components, let's say from [react-svg-chart](https://github.com/jwarning/react-svg-graph) and [recharts](https://github.com/recharts/recharts) libraries. 

Talking about external libraries, he had to import what he needed from them, so, he ended up, among the rest, with the following two imports, too:

```javascript
import { BarChart } from 'react-svg-chart';
import { BarChart, Bar, Brush, ReferenceLine, XAxis, YAxis, CartesianGrid, Tooltip, Legend } from 'recharts';
```

Apparently, the intention was to render both of those, like:

```javascript
<BarChart
	width=800
	height=600
	//rest of properties
/>
```

But what he didn't think about was that the compiler wouldn't be able to identify what kind of <code>BarChart</code> he was referring to, every time: the one from <code>recharts</code> or the other from <react-svg-chart>?!

<h3>Alias to the rescue</h3>
Although he is totally new to the js world, the [import alias](https://developer.mozilla.org/nl/docs/Web/JavaScript/Reference/Statements/import) worked like a charm!

```javascript
import { BarChart } from 'react-svg-chart';
import { BarChart as RCBarChart, Bar, Brush, ReferenceLine, XAxis, YAxis, CartesianGrid, Tooltip, Legend } from 'recharts';
```
 
That is, then he could test both components in one page/render, without receiving any complaints:
```javascript
<BarChart
	width=800
	height=600
	//rest of properties
/>
<RCBarChart
	width=800
	height=600
	//rest of properties
/>
```

<h4>Closing Quote</h4>
<em>Even the easiest things in life reveal you some kind of magic when you discover them alone.</em>

---
title: What exactly does {box-sizing:border-box} do?
summary: "An explanation of what  { box-sizing: border-box } actually is."
date: 2015-10-10
tags: ['css', 'border-box']
---

`box-sizing: border-box`

I first  came across border-box during an assignment on making my own css column layouts from scratch. Those examples can be found [here](http://codepen.io/franklynroth/pen/BoKvPp) and [here](http://codepen.io/franklynroth/pen/BoKvPp). I won't delve into them right now, but will explain what `box-sizing: border-box` actually does.

According to the [MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/box-sizing){:target="_blank"}, `content-box` is the default style of the `box-sizing` property. This means that <q>the width and height properties are measured including only the content, but not the padding, border or margin.</q> `border-box` means that <q>the width and height properties include the padding and border, but not the margin.</q>

Now if you are like me, I needed to build a codepen example to truly understand what I ust read. Take a guess at what will happen to the code below. Then scroll down for the result.


## HTML
{% codeblock lang:html %}
 <div class="content-box"></div>

<div class="border-box"></div>     
{% endcodeblock %}

## CSS
{% codeblock lang:css %}
.content-box{
  background-color:tomato;
  width:350px;
  height:100px;
  border: 10px solid black;
 }
.border-box{
  background-color:seagreen;
  box-sizing:border-box;
  width:350px;
  height:100px;
  border: 10px solid black;
  margin-top:10px;
 }
 {% endcodeblock %}
Check out the size of the red and green divs for yourself by hovering over them after pressing`CTRL + SHIFT + C` in chrome and notice the difference. The only propery that has changed other than the color is `box-sizing:border-box;` on the `.border-box` div.



<p data-height="268" data-theme-id="0" data-slug-hash="OyNBKB" data-default-tab="result" data-user="franklynroth" class='codepen'>See the Pen <a href='http://codepen.io/franklynroth/pen/OyNBKB/'>border-box functional example.</a> by Franklyn (<a href='http://codepen.io/franklynroth'>@franklynroth</a>) on <a href='http://codepen.io'>CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

In short, the `border: 10px solid black;`is taken into account when calculating the `width:350px` and `height:100px` of the green div. This shrinks the content area down to 330px by 80px to ensure that the entire element takes up the declared height and width of 350px by 100px instead of taking up a larger area than initially declared like the red div does at 380px by 120px.

---
title: CSS Specificity.
summary: "What CSS Specificity is and how to calculate it so it doesn't bite you."
date: 2016-05-11
tags: ['css']
---

This week I refreshed my memory on CSS specificity. In laymen terms certain selectors have different point values. The more specific a selector the greater precedence that selector takes. In cases with equal specificity the selector that came last will be applied aka the cascade in cascading stylesheets. Specificity is the reason why CSS-rules don’t apply to some elements when you think that they should? Hacve you ever pulled your hair out asking yourself why that certain style is not applying? Then you've wresteled with CSS specificity. Higher specificity wins if two selectors are applied to the same element.

## Code Examples
 
<p data-height="265" data-theme-id="0" data-slug-hash="Wwmayb" data-default-tab="css,result" data-user="franklynroth" data-embed-version="2" class="codepen">See the Pen <a href="http://codepen.io/franklynroth/pen/Wwmayb/">Wwmayb</a> by Franklyn (<a href="http://codepen.io/franklynroth">@franklynroth</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>
<img src="/images/first-last.gif" alt="Will Ferral Quote. If you are not first, you are last." />
 
 >The opponents were equally matched and the declaration that comes last wins.
 
Now lets look at another example, based on what you saw above you would think that the text would still be red. But its not because of specificity.
<p data-height="265" data-theme-id="0" data-slug-hash="GZeYGe" data-default-tab="css,result" data-user="franklynroth" data-embed-version="2" class="codepen">See the Pen <a href="http://codepen.io/franklynroth/pen/GZeYGe/">GZeYGe</a> by Franklyn (<a href="http://codepen.io/franklynroth">@franklynroth</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

`body h1` has a greeater value than just `h1` even though `h1` came last. Lets see how to calculate this.

## How to calculate specificity
 
* HTML selectors and pseudo elements have a value of 1 point.
* A class or pseudo-class has a value of 10  points. HTML selectors and pseudo elements have a value of 1 point.
* An ID selector is 100 points.

Add them up with some high school math and you have your specificity value. Lets see some examples. Try and gues what the values will be before looking at them.

| selector                    | point value|
|-----------------------------|------------|
| p                           |           1|
| div h1                      |           2|
| .boat                       |          10|
| div p.boat                  |          12|
| #green                      |         100|
| body #content .main p:hover |         122| 
 
### Some lesser known things
 
* `*` has a rule of 0
* `not()` has no value by itself but `not(.btn)` has a value of 10. Only whats inside the parentheses matter.
* `!important` is superhuman, it can beat anything. Yes even inline styles which have a value of 1000. `!important` isn't the best practice and makes debugging difficult because it breaks the natural cascade in the style sheets.
* `!important` can be useful when debugging something you are currently working on to see if your declaration is simply being overrulled by something else. Also useful to utility calsses.
* `!important` [is like doing this...It goes to 11!!](https://www.youtube.com/watch?v=uMSV4OteqBE&t=78s){:target="_blank"}
* Combinators have no value.

>`ul > li {color: red}`
>`ul  li {color: blue}`
><strong>Blue Wins!</strong>
 
 * You can chain a selector to itself to increase its specificity.
 * `.btn.btn` will double its specificity Using an #ID is way wat too high, it is 100 points and [cannot be overruled by 255 classes even.](https://codepen.io/chriscoyier/pen/lzjqh){:target="_blank"}
 * `.btn.btn` has little maintenance overhead, has no reliance on location or context  like an `#ID` might and this prevents the use of inline styles or god forbid `!important`.
 
A very useful specificity calculator can be found at the web address below.
<a href="https://specificity.keegan.st" target="_blank">
    <img src="/images/specific-calc.PNG" alt="Example of the specificity calculator website at the link below." />
</a>
[https://specificity.keegan.st/](https://specificity.keegan.st/){:target="_blank"}
 
## On Creating Selectors.
 
You want to be a general as possible in your selectors because if you start using very specific selectors then in order to change something then the next selector needs to be more specific and so on and so forth. It’s like when you are at a bar or restaurant and then a loud  group comes in, then your group needs to speak louder and eventually everyone is shouting and you get really busy inefficient selectors this way. 

* The shorter the rules, the better. 
* Shorter selectors are more efficient and easier to read. 
* Getting fancy with `nav .nav > ul > li > a` should be the exception when `li a` works just fine.

Thanks for reading. In short its not that hard but its also really easy to forget. I know I've had more than one occasion where this tripped me up.
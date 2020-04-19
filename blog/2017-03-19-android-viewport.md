---
title: Android keyboard messes with viewport dimension
summary: There is a little quirk on how the android soft-keyboard totally messes with css orientation rules.
date: 2017-03-19 20:20:00
tags: ['mobile']
---
There is a little quirk on how the android soft-keyboard totally messes with css orientation rules. It’s probably a lesser known gotcha, but it tripped me up longer than I would have liked. Here I will explain it and how to get around it.

I was targeting a very specific set of devices using a media query of `(orientation: portait)` whenever the user selected the search bar the on screen soft-keyboard would open up on the android tablet and it would then break my styles.

I reached out to my team and another developer noticed that when the height was changed it would also break the layout in the same manner as the keyboard popping up. I did some google fu and came accross two excellent links.

* [stackoverflow-soft-keyboard-breaks-orientation](http://stackoverflow.com/questions/8883163/css-media-query-soft-keyboard-breaks-css-orientation-rules-alternative-solut)
 
* [android-bowser-orientation-change](https://web.archive.org/web/20141109111220/http://abouthalf.com/development/orientation-media-query-challenges-in-android-browsers)
 
It ultimately has to do with how orientation is calculated as I was using `(orientation: portrait)`. The W3 calculates orientation portrait by checking if the height or width is greater, not the actual device orentation itself. So you could still have the device upright but if the height is less than the width you are in "landscape" mode.

[W3.org says](https://www.w3.org/TR/css3-mediaqueries/#orientation)
<strong>The ‘orientation’ media feature is ‘portrait’ when the value of the ‘height’ media feature is greater than or equal to the value of the ‘width’ media feature. Otherwise ‘orientation’ is ‘landscape’.</strong>

So when the keyboard pops up the height is less than the width and it breaks out of the `(orientation: portrait)` media query. iOS doesn’t have this issue because the keyboard is overlaid over the browser window vs resizing the actual browser.

So the solution is to stuff the styles that you want to still be applied in an `(orientation: landscape)` media query.


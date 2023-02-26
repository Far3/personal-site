---
title: What is CSS Flexbox
path: /what-is-css-flexbox
date: 2023-02-25
summary: What is CSS Flexbox?
tags: ['front-end', 'web', 'css']
---
CSS Flexbox is a web layout model. It allows elements to be arranged on the web page.

A web page is composed of HTML, CSS & JavaScript.

HTML: Hypertext markup language defines the content and the logical structure of the pages

CSS: Cascading style sheets define how it looks..The colors, layout, styling.

JS: JavaScript: Defines how it behaves.

Flexbox is a way to define the layout of those HTML elements. It provides an easy and clean way to arrange items within a container.

In the past other technologies and techniques were used including designing with tables, the float property and inline-block elements to varying degrees of success.

Flexbox is new because it fits based on its viewport. Can adjust in size accordingly on desktop, tablet and mobile devices. Until flexbox, Bootstrap and foundation popularized a gird style layout and helped standardize layout on the web.

Flexbox has 2 axes, the main axis and the cross axis. Main axis is the `flex-direction` property.

Values of the flex-direction can be a `row` or `column` and `row-reverse`/`column-reverse`.

An area on the web page that is using flexbox is called a `flex-container`. You set the `display` property to `flex`. After that the direct children become flex items. The default display of the items are `row` of the `flex-direction` property.

A key feature of flexbox is the ability to align and justify items on the main and cross axes. Distributing space between items used to require adding margin or padding between elements, and then adjusting that margin/padding at different viewports. You could get close by using percentages or em units vs pixels, but it usually required some adjustments at certain viewports.

Flexbox automatically takes care of this and keeps the elements distributed based on what property you select.

`align-items`: `Justify-content`. Probably the most useful value is `space-between` to take all the space of the items and share them evenly between items.

![](https://lh5.googleusercontent.com/6AFyn1ht4X-ZqM27MyWs9MftW60dssj8pyMOUt_lTg70C67uF4kMrM-d7T2xkORBTcsE8rAeegAqD3Q2046OtM23T-0NiPmJygZvg8qbWPravPvkon26sLq3nqva84M6pbuYJfvVoDwMgkRBPWutc-c)

Most of the time, flexbox is already existing in the code base and you need to edit or add the properties to a new component. When developing I typically have a resource pinned. The best one I have found on the web is the one below on CSS Tricks.

<https://css-tricks.com/snippets/css/a-guide-to-flexbox/#aa-flexbox-properties>

TLDR;

-   Flexbox is a CSS layout model that arranges elements in an efficient manner on desktop and mobile.
-   2 main elements in flexbox: `flex-container` and `flex-item`
-   2 axes, the main axes and the cross axes with multiple properties.
-   This is much improved from the table, block/inline model and float/position techniques in the past.
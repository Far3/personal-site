---
title: What is CSS Float
path: /what-is-css-float
date: 2023-02-25
summary: What is CSS Float?
tags: ['front-end', 'web', 'css']
---
Floats are a CSS property that is meant to move images inside blocks of text. It became one of the most common ways to create multiple column layouts on pages. With the arrival of css frameworks like bootstrap/foundation, css technologies such as Flexbox and Grid, float has gone away..thankfully. It is a legacy technique.

![](https://lh3.googleusercontent.com/v3KGcUIKCC2-KeXOcSz-wWhYPhcMiJ8QOKvocSU0BqNZsEGw-y5ILh2B0YUvVPJUwXz4HKRlQHkHfS2OSFIa4STiSPaCpzlv9-Hq1H3KDO4vng7JF2Ul9GtO_fTxKuaIgzy2uagtGX7cZl38NG_mpQ8)

The float property removes the element from the document flow and other elements will be displayed right beside it. If we don't want the elements to move up we will need to clear it. It was pretty common to have a clearfix hack, this involves inserting generated content after the box. This should behave the same as if you created a div below the items.

With CSS Grid and flexbox we don't need float to positon web pages anymore. The only instance I would use float if we were in an older codebase, 10-12 years old that hasn't been decommissioned yet. We needed to make a small update and the rest of the site uses floats.

I would not come in and refactor the site to use flexbox or CSS Grid, their is potential for their to be fallout from this refactor. I would continue to use float and have consistent coding practices followed in the codebase, even if they are 'technically' outdated or incorrect.

<https://css-tricks.com/all-about-floats/>

For all new development, please definitely use the latest and greatest standards where possible.
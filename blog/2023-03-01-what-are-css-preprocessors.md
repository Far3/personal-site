---
title: What are CSS Precrocessors?
path: /what-are-css-preprocessors
date: 2023-03-01
summary: What are CSS preprocessors?
tags: ['front-end', 'web', 'css']
---
What are CSS preprocessors

A CSS Preprocessor is a program that lets you write CSS from the languages own unique syntax. This lets you do more programmatic style features to CSS.

Some examples include setting variables to colors, having loops and generally more robots features than native CSS. The preprocessor is then ran and generated on development and in production to compile the syntax into native CSS that the browser can understand.

Their are many CSS preprocessors out there, the big 2 that I have worked with are LESS and 

SASS

SASS Usage

![](https://lh3.googleusercontent.com/n28bsufSfY0hkL6_BrWMWSQ8XO1bCgZCFeWjmGsfqEp465wcNyPHoL0J7ib-lRLNNh2Q1AYfNqVxMCOggBLPZ4mBjq44qJSqgQPLAjmk_dIuj9ZyZWXnJcaHDiF7t4GXcL_dAcz3SYYC7qOh119FiHE)

LESS Usage

![](https://lh6.googleusercontent.com/5c5l_6Dm0Dyol9RCUpRh05qOEmTSYTKyiNGZ0PGXkKhE3JKVA6HlIV2VdisdMSCaWrD_59p3Zt5ZyBqx5S0qUlm4-XaF6iXSFgUbNO3czjJI8mfEr99zAKSIvYB1K2FPYlgMTvCJbelVRH3L994gX3c)

Other CSS preprocessors

-   <https://www.npmjs.com/package/stylus>

-   <https://www.npmjs.com/package/postcss>

-   <https://www.npmjs.com/package/sass>

-   https://www.npmjs.com/package/less

SASS is the more popular one with 11 million downloads per week at the moment. Preprocessors add features such as mixins (basically a function), nesting selectors, inheritance selectors etc. All in all it makes the CSS structure easier to read and maintain. If you wanted to update a core color on the site, in the old way you would have to go to every place that color was declared and change the hex value. With a preprocessor all you would need to do is update the variable like `@brand-primary`: green` and it will propagate thought the codebase with a one line change.

Stylus and postCSS are other ones that I don't have experience with, but postCSS seems to have taken the lead in npm downloads.

To use a preprocessors, it has to be setup in the codebase and usually runs on a development server. Often times when developing with a client side library a server is already running, so it is hooked into the development processes.

SImple example of using SASS

![](https://lh3.googleusercontent.com/9zf3LI-MC_IZZwkwuqSkUDK_di19pE7PqnAaux_LHC5fKsJ5cunPycikneZUu_ILt7yg6iR2ppicbY2Nb9fLp0bL7eeSm5wPIHqzSL3tzyIroz88hEQZkayl5q4GyHfDZkt-t6QjUtuxNffeOhxeJ-8)

<https://codepen.io/franklynroth/pen/ZYaObK>

In the example above, a variable is declared for `$background` and `$`test-color`, this can be very helpful because it is now possible to reuse this same exact value throughout the entire document. In larger codebases you typically see a variables.scss folder declaring all the initial values.

Text weight, size, font color, font family etc.

Their are many other features of preprocessors such as loops, if/else statements etc. This helps your code be easier to maintain, keep your css DRY (don't repeat yourself), have your css be more maintainable (ever switch 5+ color updates before?), time savings and it is enjoyable to use.

TLDR;

-   CSS preprocessors run on a local server and allow more programmatic features that native CSS does not have.
-   SASS, LESS and Stylus are the popular ones.
-   They have variables, if/else statements and are fun to use
-   THis saves you time, and makes your code more maintainable.
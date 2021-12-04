---
title: How optional? chaining works in javascript
path: /optional-chaining
date: 2021-12-03
summary: A nice way to null check values is something called optional chaining
tags: ['javascript']
---
When developing on a project you will 100% come across a scenario where you need to do conditional logic. Conditional is basically handling multiple decisions and it is often taught very early in any introductory computer science class.

## Standard Conditionals

We are all familiar with the standard if else below
**If else conditional statement**

![if statement](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/gurcsc7hiet2tw9zjpyl.JPG)
This is basically saying if the hour is before/less than 18 (3pm in the afternoon) it is a good day greeting and after 3pm is a good evening greeting.

Another example are switch statements. Ie. Rule of thumb is if the logic is “over 3” a switch statement should be used instead of multiple if else statements.

**Switch statement**

![switch statement](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/xen5bepfu537vykb20ef.JPG)

The most common way you’ll see ? used in JavaScript is using it in what is called a ternary operator or inline if. A ternary is a shorthand way of writing the above if / else statement, the first time I saw it as an intern..it broke my brain. I have grown to really enjoy using it, it is short, concise and can be easily read on one line. You will commonly see it in react and other front end JavaScript libraries.

**React Example**     

![react conditional](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/u1xw32r9f9nu1etgaccg.JPG)

The above example with ternary or inline if

![inline conditional](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/mizkz7vqr8i8jh61yjap.JPG)

The condition to test is on the left side of the ?. If the value is true the value to the left side of the colon will display. If the value is false the one to the right will display. Much more effective and easy to read.


## Optional Chaining

Optional chaining enables you to read the value of a property deep in a chain of connected objects. Instead of causing a runtime error, the expression short circuits and returns undefined. 

Lets say you want to render a component and the data value is deeply nested in the return object.

![optional chaining example](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/ws6l4i91orordjuvihmt.JPG)

If we didn’t have the ? after doe we would get an all too familiar runtime error.
This saves us from having to explicitly check each value before we render it to the browser.

catAge = adventurer && adventurer.cat && adventurer.cat.age
console.log(catAge);

By just using adventurer.cat?.age. JavaSCript know to check to make sure the cat? Object is not null or undefined before attempting to a access the age property. If it is, it automatically short circuits and returns undefined.



**Conclusion**
We’ve had a short review on conditionals and how to write them as well as switch statements. How to shorten them with ternary/ inline If’s for more readable and succinct code. Finally we learned something new called optional chaining, which prevents you from checking each individual value. I hope this was helpful and you can take it back to your codebase.


Resources: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Optional_chaining
https://www.freecodecamp.org/news/how-the-question-mark-works-in-javascript/

https://reactjs.org/docs/conditional-rendering.html
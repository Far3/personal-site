---
title: What is the virtual DOM?
path: /what-is-the-virtual-dom
date: 2023-03-10
summary: What is the virtual DOM?
tags: ['front-end', 'web', 'css']
---
What is the virtual DOM?

The virtual DOM is a programming concept found in client side libraries and frameworks such as react, vue and angular. It stands for the virtual document object model and is a virtual representation of the real DOM. It is different from the shadow DOM which is a browser technology designed for scoping of variables and CSS. Virtual DOM is a concept found in javascript client side libraries.

Updating the virtual DOM is faster than updating the actual DOM. This makes it more performant for the javascript library to find the difference between the previous virtual DOM and current one. Once these differences are compared, only the necessary changes affect the actual DOM.

Now what is the actual DOM? When the web browser receives a HTML document from the server, it constructs a tree-like structure from the HTML to show the user. This tree structure is the Document Object Model or DOM for short. Structural representation of the HTML. You can sort of see this by opening dev tools in chrome and inspecting the elements. (NOw this isn't the actual DOM but the tools' interpretation of it. Edge and firefox have similar tools).

![](https://lh3.googleusercontent.com/6e_1xlBm01KOpfmkxTQIAeKcIF1fZ--43qJHOBexRtZkoXIaNc_L0AFPuGkb2Bq-kjxhXL2xMO8uCzZ6ZSE8O2-OpE2SAijG059cXYwQfLqregyJ_umeTW31qhETmpEGHYrM8pMv2X5Jc8qgtzISPz8)

Example of dev tools representing the HTML and CSS of wikipedia.org

The virtual DOM will compare each element seen here starting from the root, then work its way up to find the difference in elements. It will then only update the element vs re-render the ENTIRE DOM. This is to minimize re-renders and increase performance. It is found in react and vue.

Vue: <https://vuejs.org/guide/extras/rendering-mechanism.html#:~:text=You%20have%20probably%20heard%20about,with%20the%20%E2%80%9Creal%E2%80%9D%20DOM>.

React: <https://reactjs.org/docs/faq-internals.html>

TLDR;

- DOM is a structural representation of a web site
- Virtual dom takes a 'diff' from one change to the next and only updates the DOM with the changes.
- Virtual dom is found in vue.js and react.js frameworks
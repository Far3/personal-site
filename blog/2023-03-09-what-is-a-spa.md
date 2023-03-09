---
title: What is a SPA?
path: /what-is-a-spa
date: 2023-03-09
summary: What is a SPA?
tags: ['front-end', 'web', 'css']
---
Before the SPA, or single page application appeared. Web pages were built on static html documents and then server side rendered with PHP, ASP C#/Java or other backend language.This led to a lot of server requests and each request, an entire web page had to be reloaded. This meant that all of the content had to be resent, even though only some of the information has changed.

AJAX was introduced and stands for Asynchronous JavaScript and XML. It used various web technologies to create asynchronous applications, or applications that look and behave like desktop applications at the time. This means no reloading of the web page (server requests/responses were done in the background without interfering with the display or behavior of the site). Today in 2023, it has moved from XML to consuming JSON data.

The first time I remember seeing AJAX in real world form was when Gmail was introduced by Google in 2004 and Google Maps in 2005. It was revolutionary and so easy to be taken for granted today. A variety of javascript libraries were developed to facilitate this new AJAX technology/paradigm and jQuery was a big player up until 2015/16s (then the client side libraries/frameworks starting gaining ground react/vue/angular etc). Some earlier javaScript frameworks before the proliferation of react, angular vue were ember.js, Ext.js, knockout.js and meteor.js that looked to solve these issues.Most were build on the MVC or MVVM framework.

In an information interview around 2014 one developer said to me they didn't even touch vanilla JavaScript, just jQuery. We can see in the google trends graph below the interest is switching from jQuery to more client side frameworks like react, angular etc.

![](https://lh4.googleusercontent.com/IWpnfhODqj1Lk8dxDkyifW7d1uaVbSYpxnk6RF9kPDz0alaBXHCus4a5K08dvT25ymAgt29frIRbM7xVaeSFkIaOiSwed5dUV6o4EWUkDO6BmSEPaf6VpY9TuyGvShPFj1iPN5zlMB8OKDB0a9gkH8A)

This new found AJAX technology developed over the next 10 years until client side libraries and frameworks took hold. React, vue and angular are the big ones today...but svelte is gaining ground as an alternative.

The client side technologies break up the UI info components and keep things tightly coupled. As apps grew more and more complex in the 2015s and beyond it was increasingly complex to leverage jQuery...and you would end up with what is known as 'jQuery spaghetti'. This was a series of design paradigms and principles cobbled together over the years as different developers joined and contributed to the project. The frameworks were so great because they were declarative. Meaning the developer would tell the framework what they wanted to happen, and the framework would make the changes to get there vs the imperative form that jQuery had...managing state and data was on you to keep track of jQuery at the end of the day was created for UI focus (css forward developers at the time)..not handling data and state.

The rise of the single page application was the answer to this increasing complexity and proliferation of mobile devices. Initial load times can be higher as the web page will need to load the framework itself, but once loaded it is very fast and performance as their will be no 100% re-renders (just the components that need to change). This is done by the virtual DOM that is handled by the framework or library. A SPA is also cross platform that can be loaded on a mobile device or tablet(can re-use the backend APIs). They are best used for mobile apps, software as a service solutions. SEO is a drawback of SPA since their is only a single 'page' that can be indexed. Their are solutions to try and solve this with server side rendered solutions such as next.js.

Popular sites that are SPAs include facebook, netflix, gmail, google maps.


TLDR;
- SPAs are one of the later web development solutions that have been popular within the last 5-8 years. 
- They are the predecessors that came after web technologies such as ajax and the popularity of jQuery. 
- They can be helpful when building a fast performant site for private networks, Saas etc. 
- React, vue and angular are the three most popular technologies when developing SPAs.
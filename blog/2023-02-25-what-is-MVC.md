---
title: What is MVC
path: /what-is-mvc
date: 2023-02-25
summary: What is MVC?
tags: ['MVC', 'web']
---
As the web and technology evolved. We went from simple static HTML pages to more complicated pages that often look and feel like desktop applications. To deal with this increased complexity, different patterns emerged to make the code less complicated for developers and offered better maintainability.

The most popular industry standard framework/design pattern is MVC. It enables developers to split large applications into smaller concerns each with their own job. Business logic and the view.

This is helpful and you could have one team work on the model and logic layer while another team works on the UI/view layer. Other sub-variants such as MVVM (model-view-viewmodel), MVP (model-view-presenter) etc.

![](https://lh5.googleusercontent.com/RQZw9v6SH6fIJn7SXN16UroilD8_jd8tQS0W3ybz6k9_knfqYIpvKVs6xT51VsnUzjr1pxWVY38I2MVBDMfU3rg50vP4gKW4Wg7IkZRpU5KW69yPd-s20b7fQoxtEEkSwSMTfEEWvv08bvBHthjCQg8)

MVC: Model View Controller

Model: Handles the data and business logic.

View: Handles layout and display.

Controller: Receives the initial request, routes the request properly to the model/view and submits a response to the user.

Typical Request Flow

Controller: Where the request begins, the controller decides where to send the request.. The control handles the request, tells it what to do. Middleman to model and view. Asks the model to get the data, and perform the business logic of the request. 

Model: Handles all the data and business logic of the application. An example would be a customer object interacting with the database, manipulating the data, updating it and then sending it to the controller to send to the view.Username, the account number, bank account balance etc.

View dynamically displays the data, only cares about how to present it. Displays the dropdowns, account information, text color, font etc..

Model and view  should not interact with one another. This is all in theory and there have been times where there is business logic in the view or controller. Need to be diligent in code reviews and set and adhere to codebase standards. You can physically write model logic in a controller, and view etc...but it is a convention or suggestion to adhere to.

This was developed in the late 1980s, continued into the early 2000s on the web front. Ruby on rails framework, django python framework had similar MTV take and also ASP.NET MVC Pattern with microsoft.

![](https://lh4.googleusercontent.com/MmtEcU_hCFNsMMDE-kWxr6T0xtWwA2nK11nmoLYYMj3_Nk19fqCZYKYgOwd3YcLC9w3bH9xVwVaAYE7JC7-9c73YZwVRogaI34zJIWqwD2ks69rslEIotYYa4VuAkMkzcGFCpnsVpMwDLKBDsjL-WFE)

Currently the web is moving more toward client side service and a [REST] API(https://franklyntech.netlify.app/what-is-api). This is known as a SPA (single page application) with many different apis and smaller apps split into microservices. This is a big benefit because you can have an API that works with the web app and also the mobile app. You would not need to duplicate business logic for the web version and mobile app version.

MVC was instrumental in the development of the web and there are many many applications out there still supporting the MVC pattern.

TLDR;

-   MVC is a way to structure and separate your business logic from view logic so you don't end up with spaghetti code

-   Model: Handles all business logic

-   View: Handles presentation and UI

-   Controller: Receives the request and sends it to the correct place, Model or View, and sends the response back to the user.

-   It was developed in late 80s and was very popular on the web frameworks until recent years
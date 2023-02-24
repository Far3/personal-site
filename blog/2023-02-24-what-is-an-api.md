---
title: What is an API
path: /what-is-api
date: 2021-12-03
summary: What is an API?
tags: ['javascript', 'API']
---
What is an API?

In short an API stands for application programming interface. They are mechanisms that allow 2 software components to talk to one another using definitions and protocols. Ex. The National Weather Service has an API.

It allows companies to consume pre-existing programs without building their own in-house. Ex weather applications

<https://www.weather.gov/documentation/services-web-api>

Collective list of free APIS (many many different types)

<https://github.com/public-apis/public-apis>

![](https://lh6.googleusercontent.com/dSTPK4diKC6mDVTSojrvqIbJvV48aoSMCu4Rd2PXIh7kf_wRRlVtk5O5jYS-x2bqvOYmCFOSTpXNtRQfEky-ku2LAp7AxSb4ge6y1RIRSe9YODYWULF_E2Zl1J7w169hRhnE69Tz6AO30fE6t6PNC0I)

In the above example you are a customer making a request. The API is the waiter or waitress. You have a predefined protocol/language. Have a set menu of items (schema) and protocol (language ie. english, spanish).

The customer in this case is the client, such as web browsers, mobile apps, smart TV etc. The waiter is the API that interfaces with the backend. In this case the chef. The chef takes the inputs from the request. Ie. Cheeseburger, cooked medium with a side of sweet potato fries. No tomatoes.

Then the chef or backend service fulfills the request and hands it to the server. A good response is you get exactly what you have asked for. Also known as a status 200.

If this don't go 100% there are different status codes

200 - OK, successful responses

300 - re-direction

400 - client error (bad input, or resource was not found or not authorized)

500 - server error responses (service unavailable, internal server error etc.)

<https://developer.mozilla.org/en-US/docs/Web/HTTP/Status>

Modern APIs often have common conventions and standards and have evolved over the years.. The most common one  we see now are known as RESTful api. REST stands for representational state transfer. There are a defined set of functions like GET, PUT, DELETE on a defined protocol exchanging data using HTTP <https://developer.mozilla.org/en-US/docs/Web/HTTP>.

It appears stateless meaning that servers don't save clients data between requests and the response is plain data

The main advantages of A REST api are how easy they can be to integrate with new applications and existing systems. Can make development faster because you are not reinventing the wheel.

It allows innovation and businesses can re-write just the API portion of their application vs their entire codebase.

If you look around the web on different sites, you will find many different API uses.an example would be a wether app. Lets look at top new sties around the web. Here is a small example of a weather API implementation.

Google News

![](https://lh4.googleusercontent.com/MfnyWWvo_gIzWU4vPAfWF0W7YjSf9jKRNlA2S5eT2YM99yIhsCTBjKEJQ_QON4Ipr0RnSllTVtHtKrNfqm_xJlGF0t4mpUAQEExpEGeeNiedCEG_STPtcWGDmMThNvT6RVsGyReqLTEkeKPJ1BaK_jY)

<https://news.google.com/>

The new york times

![](https://lh3.googleusercontent.com/Jf-yAfr8GMaoIJHAsonx-n2g1zF2UPSpXYI46Ml-WaczjkPa39gz_pg5xS8YB7CN9PhqtzEIaYsXt6RyS1r0SQ8ncvTAo1G1x7AqkHScevTCsoVmaAM8uaY7OEiURc-jYqKnVHC1G8VebOZf92Cg-r8)

<https://www.nytimes.com/>

MSN

![](https://lh6.googleusercontent.com/Rwwi1j1a6RcWBAt2DvQN6OBGAtKzxjxZMDoirWqpN52DQPy8thZig7jTLtsm8D8p7gZrLqUE8Cl7IODi5BDsVQmtL87HJbzH8x3XkBKL42VcXT7huoJCVFDaWJfDe365D7iaTOVzXcxiVmgm9JaJXuY)

https://www.msn.com

Yahoo

![](https://lh4.googleusercontent.com/6For6CQ63QpzmL3Vq2pLgFr0F9O3kbA4ELP6UfiV6w_AKiT1hF-vEdvEqsuBhqqXugWV0nOZh7OJiu4woPxEzv2q2qEXQyvZfB3O3oddckPRRa56Y5U877KrZzTodxrVljSOXF2_2dgDXhi1ewaV69I)

<https://www.yahoo.com/>

If we do some investigation below we can see that the weather for nytimes comes back from the following endpoint. It probably uses another API to get the relevant location, pass in the longtidue/lattitude coordinates to get a 'location' unique ID.

<https://content.api.nytimes.com/svc/weather/v2/current-and-seven-day-forecast.json>

We can see it is returned in JSON format a very common data object response.

In conclusion

TLDR

-   API stands for application programming interface

-   It is a way for applications to consume services/functions from other applications ie. weather, finance data, gps data)

-   APIs connect have a client and a server

-   Most common one today is REST API
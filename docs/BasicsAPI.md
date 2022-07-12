---
tags:
  - Coding
  - API
  - Cheatsheet
---

# API Basics

_**Authors:** Teun Engels, Chinou van Maris_

---

This document will cover all the basics about APIs (Application programming interface's).

## **GET**

The GET method is used to retrieve data from the server.

This is a **read-only** method, so it has no risk of mutating or corrupting the data.

## **POST**

The POST method sends data to the server and creates a new resource.

The resource it creates is subordinate to some other parent resource. When a new resource is POSTed to the parent, the API service will automatically associate the new resource by assigning it an ID (new resource URI).

In short, this method is used to **create a new data entry**.

## **PUT**

The PUT method is most often used to update an existing resource.

If you want to **update a specific resource** (which comes with a specific URI), you can call the PUT method to that resource URI with the request body containing the complete new version of the resource you are trying to update.

## **DELETE**

The DELETE method is used to **delete a resource** specified by its URI.

## **Synchronous / Asynchronous**

Synchronous/asynchronous APIs are [application programming interfaces](https://nl.wikipedia.org/wiki/Application_programming_interface) that return data for requests either immediately or at a later time, respectively. Synchronous/asynchronous APIs provide a way to make immediate or scheduled requests for resources, data or services when available.

The synchronous and asynchronous nature of an API is a function of the time frame from the request to the return of data. In the case of synchronous APIs, the expectation is that there will be an immediate return of data. The application requests data and waits for it until a value is returned.

In the case of asynchronous APIs, the availability of a resource, service or data store may not be immediate. These APIs may provide a callback to the requester when the requested resource is ready. Asynchronous requests are useful in maintaining functionality in an application rather than tie up application resources waiting on a request.

**An API may be synchronous where data or service availability, resources and connectivity are high and low latency is a requirement. An API may be asynchronous where data or service availability and connectivity are low or oversaturated with demand.**

## **REST API**

Representational State Transfer Application Program Interface is an architectural style that allows software to communicate with other software over a network or on the same device. Typically, developers use REST APIs to build web services.

REST is often called RESTful web services and uses HTTP methods to retrieve and post data between a client device and a server.

## **HTTP API**

A web API is a protocol that describes how your clients can access resources and what methods work with your architecture. These resources can be of a variety of media types like JavaScript or HTML elements, metadata, or images. You can essentially think of it as a translation guide from one technology to another. An HTTP API is an API that uses Hypertext Transfer Protocol as the communication protocol between the two systems. HTTP APIs expose endpoints as API gateways for HTTP requests to have access to a server.

For example, you use an HTTP API every time you set a Zoom meeting in your Google calendar. The API defines how Zoom can communicate directly with Google’s servers to embed a Zoom meeting into the event rather than having to copy and paste the meeting invitation into a field.

HTTP APIs is a broad category, meaning they come in various forms based on their target use case. HTTP APIs are further categorized by the architectural design principles used when they’re created. Most are used in hypermedia information systems or web development, but each has particular pros and cons.

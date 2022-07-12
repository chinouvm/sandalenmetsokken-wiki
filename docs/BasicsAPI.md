
# API Basics

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

## REST API 

Representational State Transfer Application Program Interface is an architectural style that allows software to communicate with other software over a network or on the same device. Typically, developers use REST APIs to build web services. 

REST is often called RESTful web services and uses HTTP methods to retrieve and post data between a client device and a server.



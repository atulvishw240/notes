In contrast to front-end development, you can run pretty much any language you want to on your server since it doesn’t rely on your user’s browser understanding what’s going on.

As long as it can take in an **HTTP** request and spit out some **HTML**, you can probably put it on a server somehow.

## What is a back-end?

The back-end is all of the technology required to process the incoming request and generate and send the response to the client. This typically includes three major parts:

- The **server**. This is the computer that receives requests.
- The **app**. This is the application running on the server that listens for requests, retrieves information from the database, and sends a response.
- The **database**. Databases are used to organize and persist data.

>The pair of an HTTP verb and URI is called a *route*, and matching them based on a request is called **routing**.

## What is a Web API, really?

An API is a collection of clearly defined methods of communication between different software components.

More specifically, a _Web API_ is the interface created by the back-end: the collection of endpoints and the resources these endpoints expose.

>The code that runs on the server between the request and the response is called _middleware_.


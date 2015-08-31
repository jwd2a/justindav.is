---
layout: post
title: "Cross-Origin Requests in Express.JS"
summary: "If you're building an API or application in Node with Express, being able to accept cross-origin requests is an important part of making sure your application is as usable as possible."
comments: true
---

If you've ever done any API work, you've certainly run into cross-origin restrictions. Designed as an important security aspect for the browser, these cross-origin restrictions quickly get to be a pain in the ass when you're trying to build a service that, by its very design, is for allowing clients from different domains to connect to your service.

### A Brief History of CORS

Cross-Origin Resource Sharing (CORS) [came about in 2004](https://en.wikipedia.org/wiki/Cross-origin_resource_sharing#History) as a modern alternative to JSONP. It was designed to permit a wider range of request methods than JSONP allows - which is only `GET`. With CORS, servers now had a way to control which clients could connect, how they could connect, and which methods they were permitted to execute on the server.

### Options, Options, Options

There are two types of cross-origin requests that can happen: simple requests, and preflighted requests.

In a *simple* request, the request is made per usual, and the server abides, as you'd normally expect. These happen under two circumstances:

- A `GET`, `POST` or `HEAD` request with the following content types: `application/x-www-form-urlencoded`, `multipart/form-data`, or `text/plain`.
- A request that doesn't set any custom headers.

In these cases, the client makes a request, and access is handled per usual, via a `Access-Control-Allow-Origin` header, which indicates which clients may connect(A domain name or wildcard, for example). For these, no extra configuration is required on your end (unless you're configuring standard `Access-Control-Allow-Origin` headers for these requests).

In *preflighted* request, things get a bit more interesting. In requests that don't match our criteria above, the browser fires off a special _preflight_ request, with a special header: `OPTIONS`. The `OPTIONS` header tells the server to respond with the CORS configuration available. If the server agrees, it will send back a response with a number of possible headers on the response, most commonly `Access-Control-Allow-Origin` and `Access-Control-Allow-Methods`.

There are a number of other headers a server can respond with, including headers that specify headers it'll accept, credentials it'll accept, and others. For this type of advanced configuration, [review the full set of these headers](https://developer.mozilla.org/en-US/docs/Web/HTTP/Access_control_CORS#The_HTTP_response_headers).

These preflighted requests are protected with this initial `OPTIONS` request, to assure that modification/access of user data is appropriately controlled. The server will respond back with the origins that can access the server, the methods it can execute on the server, the headers it can send, and a variety of other options spelled out in those response headers.

With these preflighted requests, we're able to allow for cross-origin requests in a secure manner, making the web a much more interesting place to build things. In today's API-driven, service-oriented environment, CORS is part of the glue that makes it all work.

### CORS in Express.js 

Alright, we're getting to the code, I promise. Now that you have a decent enough understanding of how CORS works, let's look at how we'd do this in Node, more specifically, in [Express](http://expressjs.com), one of the most popular Node frameworks.

According to our explanation about how CORS works above, we need to configure our Express server to support `OPTIONS` requests, and tell it how to respond, should it encounter one.

I like to put my CORS handler as a piece of middleware in my Express server. In `app.js`, I have the following:

~~~
var allowCrossDomain = function(req, res, next) {
    if ('OPTIONS' == req.method) {
      res.header('Access-Control-Allow-Origin', '*');
      res.header('Access-Control-Allow-Methods', 'GET,PUT,POST,DELETE,PATCH,OPTIONS');
      res.header('Access-Control-Allow-Headers', 'Content-Type, Authorization, Content-Length, X-Requested-With');
      res.send(200);
    }
    else {
      next();
    }
};

app.use(allowCrossDomain);
~~~

What we're doing here is creating a little piece of middleware that Express will route requests through. Each time a request comes in, Express will run it through this little method. The method is really pretty simple: it checks to see if there's an `OPTIONS` request coming in, and if so, sets the CORS headers as needed, and fires off a success response to the client with those headers. The client, then, upon receiving this response, will respond back with the actual AJAX request. Couldn't be easier.

If the request that comes in doesn't have the `OPTIONS` header, it simply runs to the next piece of middleware and skips the whole thing.

I've included a bunch of optional request values here, but you'll want to tailor these to your situation (read: don't just straight up copy this). These headers are pretty open - they allow any origin to connect, and allow for a wide array of methods to be executed, in addition to allowing for a wide variety of headers to be sent. Tighten these down as you need to for your situation.

That's all there is to it! With this setup, you'll be able to support CORS and configure cross-origin access for your Node/Express app easily. Don't forget, having other clients connect to your service means a heightened level of attention that needs to be put on examining and sanitizing requests, so don't let using CORS open up big security issues in your application. You should still check requests in your controllers to make sure everything is cool.

Got a better way of handling CORS with Express? Drop it in the comments!

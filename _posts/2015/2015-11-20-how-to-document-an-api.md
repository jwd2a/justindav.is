---
layout: post
title: "How to Document an API"
summary: "Recently, I was in the middle of project where I needed to design and document a new API. Here's what I found as the best method."
comments: true
---

I've been working on a project where I've had to design - and document - a brand new API. The API is RESTful, and exposes services out to a number of clients. Pretty standard stuff.

As part of this project, I needed a way to document how we were designing the API architecture - all the endpoints, data models, all that. In our case, the API hasn't even been built yet - we're designing it completely, then going to build it.

## API Doc Immaturity

When we kicked off the project, I was focused on creating documents that could be consumed by a development team for building the API. My gut was to make sure the documents were readable and presented nicely. Beyond that, I didn't really have much of an opinion on how they were put together.

With that in mind, I turned to [Slate][slate], an open-source package that provides usable, attractive documentation for APIs. I liked Slate because of the UI - it's really nicely done, easy to understand, and pretty flexible. Also, creating docs was as easy as writing Markdown (how I write my blog posts anyway), so it felt natural. So, happy with that, I went and started to build the docs.

## Getting More Legit

Shortly into building out the docs with Slate, I started to get curious about other documentation standards. Flitting about various Github repos, I stumbled upon [API Blueprint][apiblueprint], and it was a massive aha moment. API Blueprint is an actual spec! It's a structured way to define an API, which documents are then automatically generated from.

This felt like a huge improvement. Now, I could manage a spec, but decouple the design/spec of the API from the presentation/docs layer.

I started digging into API Blueprint more, building out nearly the full spec of the API in it. What I loved about API Blueprint was the structured way it approached the design of the API. Create endpoints, define requests and responses for them, indicate parameters, etc. It felt much more organized, and helped me to think through the lower-level bits of the API more intentionally. Also, it was written in Markdown just like Slate, so it felt like a natural transition.

That said, there were things that bothered me about API Blueprint. I hated some of their strict indenting rules (tabs were four spaces, really irked me), and over time, it because difficult to read the spec. At one point, I broke it up into chunks of smaller markdown files (per endpoint) using [markdown-pp][markdownpp], and created a shell script that compiled all the individual markdown files into a single markdown file every time I modified one of the smaller files.

Also, there were some odd rules about how endpoints were defined, and I felt like it didn't give me the kind of flexibility in design I wanted. Too opinionated, too stodgy in its approach.

Workable, yes, but still felt a bit lacking. However, I was onto something at this point: API specs should follow a more structured pattern, and should be decoupled from the docs. Good to know.

## Mature API Spec FTW

Still a bit unhappy with how the spec was coming together, mainly due to the formatting issues and increasingly difficult job it was to manage the spec, I started exploring other alternatives to API Blueprint.

That's when I found [Swagger][swagger]. Now, to people who are familiar with API specs, this isn't going to be a shock. Swagger is the big kid on the block, arguably the most mature API spec tool out there, and it shows.

(The crappy nature of their website initially turned me off, but I got over it)

Swagger is what API specs should be like. Now on v2.0, it's a well-reasoned, fully-considered specification for documenting APIs. Plus, the new version of Swagger supports writing the spec in Yaml, a huge bonus IMO.

With Swagger, documentation is easy and effortless to write. Here's how we might define a spec (taken from the official Swagger demo):

~~~

swagger: '2.0'
info:
  title: Uber API
  description: Move your app forward with the Uber API
  version: 1.0.0
host: api.uber.com
schemes:
  - https
basePath: /v1
produces:
  - application/json
paths:
  /products:
    get:
      summary: Product Types
      description: |
        The Products endpoint returns information about the *Uber* products
        offered at a given location. The response includes the display name
        and other details about each product, and lists the products in the
        proper display order.
      parameters:
        - name: latitude
          in: query
          description: Latitude component of location.
          required: true
          type: number
          format: double
        - name: longitude
          in: query
          description: Longitude component of location.
          required: true
          type: number
          format: double
      tags:
        - Products
      responses:
        '200':
          description: An array of products
          schema:
            type: array
            items:
              $ref: '#/definitions/Product'
        default:
          description: Unexpected error
          schema:
            $ref: '#/definitions/Error'

~~~

To me, this just makes sense. A path - `/products` - with a set of nested methods underneath (`get`, `post`, etc.). Parameters are easy to define, as are responses. You'll also notice that `$ref` down there in the responses. That allows you to define a model and reference it on the responses - no more trying to update multiple response signatures when a model changes slightly. DRY FTW.

As if the spec format itself isn't enough, Swagger brings with it a host of tooling as well. [Swagger UI][swaggerui] automatically builds documentation from the spec. [Swagger Codegen][swaggergen] automatically creates client libraries and server-side stubs from the spec (what?!). As if the official tools from Swagger aren't enough, there are [a whole host of projects on Github][swaggergh] offering tooling for the spec. Suffice to say, Swagger is the shit, and the way to document APIs IMO.

Swagger is also helping to put ahead the [Open APIs][openapis] initiative, aiming to help create a standardized way of interacting with RESTful APIs between companies. Folks like Google, IBM, Apigee and others are on board, and it's great to see that kind of initiative shaping up. In today's ever-increasing service-oriented world, this kind of industry adoption of a single specification for defining the design of APIs is a huge step in the maturity of the field.

I should note that I also looked at [RAML][raml], and just about went that direction for documenting the spec. RAML is also a Yaml-based way of doing things, and frankly, is somewhat similar to Swagger in some ways. When it came down to it, however, the wide amount of tooling already available for Swagger kicked it over the edge for me, and I'm really thrilled to be using it.

## Why This Is Important

Standardization is important. As we develop more services, it's going to become more and more critical that we understand how these services operate, and reduce the amount of time it takes for developers to learn the specifics about an API. By standardizing around a specification, we can move toward developing sophisticated tooling around those specs, and help APIs play together more seamlessly in the future. That interoperability is huge, and something all of us should strive for.

So, if you're looking to document your API (and if you have an API, you need to document it), I'd highly recommend looking at Swagger. It's incredibly powerful, and just the kind of approach that modern API development really needs.

Have you used Swagger or another documentation tool? Have success or horror stories? Toss them in the comments!

[apiblueprint]: http://apiblueprint.com
[markdownpp]: https://github.com/jreese/markdown-pp
[openapis]: http://openapis.org
[raml]: http://raml.org/
[slate]: https://github.com/tripit/slate
[swagger]: http://swagger.io
[swaggergen]: https://github.com/swagger-api/swagger-codegen
[swaggergh]:https://github.com/search?utf8=%E2%9C%93&q=swagger
[swaggerui]: https://github.com/swagger-api/swagger-ui

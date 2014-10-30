## The best of rest - from the basics to what's next

### Keith Casey

__Summary:__
When we discuss APIs, most people immediately think of OAuth, GET and POST, and JSON. A few people think of the underlying concepts of nouns and verbs, idempotence, and uniform interfaces. But even fewer consider how we can combine these concepts into hypermedia to build APIs that are useful, logical, and future-friendly. Luckily a number of people are already on the outer edge building and experimenting with these concepts to give us perspective on what's to come. In this presentation, we'll begin with the basics, combine them to describe the larger concepts, and look at the standards that are leading the way.

---

* [A Practical Approach to API Design](https://leanpub.com/restful-api-design)
* [API Evangelist](http://apievangelist.com/)

REST is _not_ a standard; it's flexibility all leads to ambiguity

* client-server
* stateless
* cacheable
* layered system
* uniform interfaces
* code on demand

**richardson maturity model:**

* level 0: the swamp of POX (plain old XML)
* level 1: resources
* level 2: HTTP Verbs
* level 3: hypermedia controls
* Glory of REST

REST is not...

* XML over HTTP
* JSON over HTTP
* there's no specific data type (no specification for payloads)

REST can be...

* XML over HTTP
* JSON over HTTP
* binary files over HTTP

RESOURCES == NOUNS

### Uniform interfaces

* identification of resources
* manipulation of resources though these representations
* self-descriptive messages
* HATEOAS - hypermedia as the engine of application state

#### Identification of resources
* generally
	* /nouns/:id
	* /nouns/:id/subnoun/:subid


#### Collections too...
* generally
	* /nouns
	* /nouns?page=n&limit=100 (adjectives!)


#### GET, POST, PUT, DELETE

http verbs are great, use them, _don't create your own_!!

#### self-description

* each messages should tell you:
	* if that resource is cacheable
	* how to process itself
	* how to request the next resource

#### Code on demand

* a request doesn't just retrieve a resource but also the code rot act upon it
	* we don't have to know or understand the code, just how to run it
	* allows for flexibility, upgradeability

descriptive messages:

* HAL (most-common) - hypermedia application language
* Collection JSON
* Siren

#### HATEOAS

APIs using hypermedia:

* github
* twilio
* sendgrid
* foxycart


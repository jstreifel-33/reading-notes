# API Design Best Practices

## RESTful Web API Design

Source *(article)*: [Microsoft Docs: RESTful web API design](https://docs.microsoft.com/en-us/azure/architecture/best-practices/api-design)

* **What does REST stand for?**
  * REST stands for REpresentational State Transfer. It is an architectural style for building distributed systems based on hypermedia. It is not tied to HTTP, but most REST APIs use HTTP as their application protocol.
* **REST APIs are designed around a ____.**
  * REST APIs are designed around resources. These can be any kind object, data, or service. REST APIs are language independent from clients.
* **What is an identifer of a resource? Give an example.**
  * A resource is identified by a URI (Uniform Resource Identifier). This can be a url such as `https://adventure-works.com/orders/1` (example from Docs).
* **What are the most common HTTP verbs?**
  * GET, POST, PUT, PATCH, DELETE
* **What should the URIs be based on?**
  * A good URI should be based on nouns, and generally refer to the resource to be accessed in some way.
* **Give an example of a good URI.**
  * From the docs: `https://adventure-works.com/orders` <- Good (uses a descriptive noun) / `https://adventure-works.com/create-order` <- Bad (uses a verb)
* **What does it mean to have a ‘chatty’ web API? Is this a good or a bad thing?**
  * A chatty web API is one that requires many small requests to get a complete set of information. It is better to store data in large batches and sort through it in a single request, to avoid overloading an API with too many repeated requests. This must be balanced, however, with trying to avoid retrieving large amounts of unneeded data, as that can lead to high latency and bandwidth consumption.
* **What status code does a successful GET request return?**
  * 200 - OK
* **What status code does an unsuccessful GET request return?**
  * 404 - Not Found
* **What status code does a successful POST request return?**
  * 201 - Created
* **What status code does a successful DELETE request return?**
  * 204 - No Content

## REGEX

Source *(medium post)*:[Regex tutorial - a quick cheatsheet by examples](https://medium.com/factory-mind/regex-tutorial-a-simple-cheatsheet-by-examples-649dc1c3f285)

Regex is super cool and worth learning for string manipulation. I usually forget it 2 days after learning it, but someday it will stick. I'm not going to deep dive here, but storing the tutorial cheat sheet here for future reference as needed.

* To search my name in regex, I would use use `/Joseph/g`

## Things I Want to Know More About

I think the last bit on versioning was interesting. I've always felt like versioning of things was generally arbitrary, but it's nice to see some guidance on it. A lot of the database talk went over my head, so I'd like to learn more/read up on database management and organization. I don't really understand what pagination means but it sounds awfully important.
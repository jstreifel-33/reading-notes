# CRUD

## Status Codes Based on REST Methods

Source *(Blog Post)*: [Which HTTP Status Code to Use for Every CRUD App](https://www.moesif.com/blog/technical/api-design/Which-HTTP-Status-Code-To-Use-For-Every-CRUD-App/)

* In your own words, describe what each group of status code represents:
  * 100’s = Informational status codes, which usually tell the client that a request has been received.
  * 200’s = Success codes. These inform a client when a request is accepted.
  * 300’s = Redirection codes. These tell the client that a requested resource is no longer available at it's expected location.
  * 400’s = Client error codes. Used to notify the client of an invalid request.
  * 500’s = Server error codes. Used to indicate overwhelmed or unreachable servers. Usually indicates that a client send an incorrect input.
* What is a status code 202?
  * **Accepted** - Often used for asynchronous processing. Notifies the client that their request was valid and is processing to be finished in the future.
* What is a status code 308?
  * **Permanent Redirect** - Tells the client to use another URL to access the resource instead of the current URL.
* What code would you use if an update didn’t return data to a client?
  * **204 No Content** is the most fitting code for DELETE requests, since we wouldn't return data that does no longer exists.
* What code would you use if a resource used to exist but no longer does?
  * **410 Gone** used similarly to 404, but for resources that we know did exist at some point.
* What is the ‘Forbidden’ status code?
  * **403 Forbidden** is used when a client doesn't have authorization to access a resource.

## Building a REST API With Node.js, Express, & MongoDB

Source *(Video)*: [Build A REST API With Node.js, Express, & MongoDB - Quick](https://www.youtube.com/watch?v=fgTGADljAeg)

* Why do we need to pull our MongoDB database string out of our server and put it into our .env?
  * So that we can easily change the database string when we eventually deploy. Environment variables make it easy to change things like URLs via deployment settings.
* What is middleware?
  * Code that gets run when a server receives a request but before the request gets sent through routes.
* What does app.use(express.json()) do?
  * Allows the server to accept JSON as a body of a request to the server.
* What does the /:id mean in a route?
  * It means that id is a parameter that can be accessed by using req.params.id. id will be whatever comes first in the path.
* What is the difference between PUT and PATCH?
  * Put us used to add data to a database and patch is used to update data in a database.
* How do you make a default value in a schema?
  * in the value object for a key, include `default: value` in the object.
* What does a 500 error status code mean?
  * 500 status code is used to indicate an error on the server. The error originates from the API, which is our fault and not the client's.
* What is the difference between a status 200 and a status 201?
  * 200 is a general "everything was successful" message and 201 is an "object was created" message to indicate a successful post request. 201 is basically a more specific 200.

## Things I want to know more about

The routing structure from the video was new to me. I'd like to dive more into it and work to understand it better. I imagine we'll get there with various other requests to our server.

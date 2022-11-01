# Status Codes Based on REST Methods

[SOURCE](https://www.moesif.com/blog/technical/api-design/Which-HTTP-Status-Code-To-Use-For-Every-CRUD-App/)

***In your own words, describe what each group of status code represents:***

100’s = Informational status codes
200’s = Success codes. Tell client request was accepted.
300’s = Redirection codes. Informclient resource being requested isn't availableor at expected location.
400’s = Client error codes. About invalid requests a client sent to a server.
500’s = Server error codes. Indicate problems with overhwelmed servers or unreachable servers.

***What is a status code 202?***

```Accepted``` Tells the client that the request was valid , but its processing will finish sometime in the future.

***What is a status code 308?***

```Permanent redirect``` Tells the client to use another URL to access the resource and not use the current URL anymore. Useful when we have multiple endpoints but we dont wnat to read from all of them.

***What code would you use if an update didn’t return data to a client?***

```204 No Content```

***What code would you use if a resource used to exist but no longer does?***

```410 Gone```

***What is the ‘Forbidden’ status code?***

The client has no permission to access the resource.

## BUILDING REST API

[SOURCE](https://www.youtube.com/channel/UCFbNIlppjAuEX4znoulh0Cw)

***Why do we need to pull our MongoDB database string out of our server and put it into our .env?***

We don't want to expose that to the public and to the client. .env does not get pushed to github. furthermore, ,it allows that variable to be changed if necessary, without changing the code.
***
***What is middleware?***

Middleware is code that runs when the server gets a request but before it gets passed to your routes.

***What does app.use(express.json()) do?***

Lets our server accept JSON
It sets up the server to use JSON as return data from a request

***What does the /:id mean in a route?***

```/:id``` refers to a parameter passed in to get a specific piece of data. It can be accessed with  ```request.params```

***What is the difference between PUT and PATCH?***

```PUT``` updates a piece of data to a new value, while ```PATCH``` is only a partial update to a piece of data.

***How do you make a default value in a schema?***

You add a ```default``` field in the properties object for a key

***What does a 500 error status code mean?***

```Internal Server Error```

***What is the difference between a status 200 and a status 201?***

``` 201``` is specifically returned after something is successfully created.

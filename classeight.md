# API Design Best Practices

[source](https://learn.microsoft.com/en-us/azure/architecture/best-practices/api-design)

***What does REST stand for?***

Representational State Transfer

REST APIs are designed around  ```resources``` which are any kind of object, data, or service that can be accessed by the client.

***What is an identifier of a resource? Give an example.***

It is a URL that uniquely identifies that resource

```https://adventure-works.com/orders/1```

What are the most common HTTP verbs?

1. ```GET```
2. ```POST```
3. ```PUT```
4. ```PATCH```
5. ```DELETE```

***What should the URIs be based on?***

URI should be based on the nouns```the resource```

***Give an example of a good URI.***

```https://gikomba-works.com/clients```

***What does it mean to have a ‘chatty’ web API? Is this a good or a bad thing?***

It is a bad thing because it exposes a large number of resources and such an API may require a client application to send multiple requests to find data that it requires.

***What status code does a successful GET request return?***

HTTP status code 200 (OK)

***What status code does an unsuccessful GET request return?***

HTTP status code 204 (No Content)

***What status code does a successful POST request return?***

HTTP status code 201 (Created)

***What status code does a successful DELETE request return?***

HTTP status code 204 (No Content)
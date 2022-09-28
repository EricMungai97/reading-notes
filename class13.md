# Reading Notes 13

## Why would a developer use local storage for a web application?

HTTP as the main transport layer of the web is stateless. This means after using an application and closing it, its state is reset the next time you open it.Local storage enables you to store the state of your application.

## What information should not be stored in local storage?

We should not store any sensitive information. Things like user passwords, credit card info et.c.

## Local storage can store what type of data? How would you convert it to that type before storing?

Local storage stores strings. We would convert is using the following method.

```JSON.stringify();```


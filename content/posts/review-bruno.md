+++
date = '2025-06-24T20:31:29-05:00'
draft = false
title = 'Product Review: Bruno'
tags = ['api-development', 'programming']
categories = ['review']
+++
## Synopsis


## Content
I've been using [Bruno](https://www.usebruno.com/)for about six months now, and I'm really enjoying it. I wanted to write a few examples of why its better than Postman (or others). 

I love the assertion mechanism. Assertions allow you to check basic properties of responses, such as status code, number of elements in the body, etc.  Its much more convenient and approachable than a full javascript test. It has a massive amount of validators as well, making it very robust. If you need to do some quick validations on a test, such as it returns the appropriate status code, it is much easier and still is part of the testing suite. I find I'm doing assertion checks more than full javascript tests with Bruno.

Second is the file format. Instead of all your calls in one large, obscure file, you get one file per request. So if you have 10 requests, you don't have many more than 10 files (there are a few folder and collection level files, but they're not massive or obtrusive). Here's an example from my service dependency api project. This is it, the entire file that runs the request. Notice that even without the Bruno app, this is easily readable. We know its a `GET` call named "Time" and that we expect the status code to be a `200 OK`. Additionally we can easily read the markdown formatted documentation at the end!

```json
meta {
  name: Time
  type: http
  seq: 2
}

get {
  url: {{baseUrl}}/time
  body: none
  auth: inherit
}

assert {
  res.status: eq 200
}

docs {
  # Current Time
  
  Gets current time of the server
  
  ## Parameters
  **none**
  
  ## Return
  String of the current time
}

```

Additionally, these files are very easy to share via git, Slack, or whatever to help another engineer debug a problem. I personally have a "scratch pad" collection to hold one off requests that serves as a dumping ground for files to help debug.

Lastly, I've spent some time using the companion bru CLI to implement automated HTTP testing. It's very easy to set up a sub folder for smoke tests and have your GitHub Release action run that folder recursively to ensure that all smoke tests pass on every release. Additionally, the bru CLI has different reporter options, such as JUnit, that make reporting as part of the release very easy. Its easy to pass not only an environment, but also specific environment variables (like passwords) in to run these tests. I find it best to match my Bruno environments to my GitHub environments so its seamless to send in the environment and any special variables required.

Overall I really like the tool and think its very powerful. Its changing the way I develop tests and makes it much easier to document HTTP calls. I look forward to seeing what they add in the future. 

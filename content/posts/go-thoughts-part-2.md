+++
date = '2025-06-17T20:09:12-05:00'
draft = false
title = 'Go Thoughts Part 2'
tags = ['go']
categories = ['programming']
+++

I've spent several months and two side projects working with Go, so I think its time to revisit [this post](https://blog.joshpotts.net/posts/initial-go-thoughts/). Overall I've come to really enjoy the language and think about it differently now.
## The good
- The concurrency system is extremely good and allows you to do things very quickly.
	- It also allows you to not worry about *if* something is done, just *when* its done. 
- I like that so much is built in.
	- http server
	- testing
	- lots of synchronization tools
- Lightweight applications.
- The way you can put functions with receivers in multiple files in a package reminds me of python, but allows you to even better organize your code.
- Receivers make your objects very extensible
- The syntactic sugar of being able to define types to make code more readable is nice. 
## The not so good
- Error handling is very boiler plate.
- There's additional mental complexity/overhead to deal with.
- It takes a bit to get used to the syntax. 
- Its easy to get into a race condition. 
- Receivers on functions are kind of weird to get used to. 
## The other takeaways
- Using pointers makes you think more deeply about reference and values in other languages (like C#)
- It feels like you have more memory control (I think of it as C lite)
- It makes you think about coding in a different way
	- Go is like having a distributed system baked into a single app
- There's less ceremony than a language like C#, there's also less guardrails. 


Overall I find I enjoy working in it. I'm sure people could argue that any of these points apply to the language they like, and I'm not here to discount your opinion. This is simply my thoughts on the language. It has a lot of power, but that doesn't mean you have to use it for everything. It's simply a useful tool in your toolbelt. 

An example of such: we were looking at traversing a tree of unknown size. Using go, its actually really easy to use somewhat recursive functions and wait groups to traverse the tree. In a language like C# it can be done, but you don't know *when* your traversal algorithm is done without some additional overhead. Go's wait groups take care of all that for you. I think its important to think about languages not as the sole thing to work in, but more as a tool to get a job done. 
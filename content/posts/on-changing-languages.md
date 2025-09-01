+++
date = '2025-08-31T20:06:01-05:00'
draft = false
title = 'On Changing Languages'
tags = []
categories = ['programming']
+++

Been a long couple of weeks on a tight deadline project, and I'm just now having time to begin thinking about moving to the projects I was supposed to be working on.  This work has been pretty exclusively in C#, with some minor reviews of JavaScript. This swapping languages, coupled with a new want to write more in Go, has me wanting to writing about languages and changing them frequently.

Your senior/staff+ engineers will tell you "the language is just a tool in your toolbox, pick the best one for the job," and frankly that should be true. Some languages are just better suited for some uses than others. Take Python vs C# for example. If you're working in lambda, Python is the superior choice because

- its a first class citizen in the AWS ecosystem
- it has a faster cold start time

Does Python have limitations? Of course it does, but it's really good at doing functional programming and doing one thing really well, which are core architectural underpinnings of serverless functions.

Sometimes though, you just miss using some languages. My experience with that has been working in C# pretty heavily and missing working in Go. C# just *feels* like it has more boilerplate to it, which is odd to type considering how much boilerplate exists in Go error checking. I know not all C# is like this, its a symptom of the legacy architecture I'm working on. I've written better C#, heck I've written the same basic code with repositories, services, etc. in both C# and Go and they are almost identical. But I do miss working in Go, it makes you think about how you code differently, a [reoccurring theme](https://blog.joshpotts.net/posts/go-thoughts-part-2/). 

Thinking differently in different languages is something I see more and more as I interchange languages more and more frequently. For example, C#'s by ref passing of classes as variables allows you to do things you couldn't in Python (if these things are good or bad I won't comment on in this article). I can tell my thought patterns are different when I'm programming in Python vs C# vs Go vs SQL. Each requires a different mindset because each has its own strengths and weaknesses. 

Overall I think the point of this article is that yes, languages are tools in the developers toolbox, but its ok to have a favorite tool. Or to be interested in a new tool. Each new tool expands your horizons and makes you think about things very differently. 
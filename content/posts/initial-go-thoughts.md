+++
date = '2025-04-09'
draft = false
title = 'Initial Go Thoughts'
tags = ['go']
categories = ['programming']
+++
I've been watching [Learn Go in 3 Hours](https://www.oreilly.com/library/view/learn-go-in/9781788992053/) this week and I've decided to make this blog post my observations on the language so far. I'll compare this in a month or two after I finish this [service dependency api](https://github.com/users/jlpdeveloper/projects/8/views/3?pane=info) project.

## Initial Observations
- The language is very strict with its typing, but feels very loosey goosey with its control structures (a `for` loop without a condition or stop point, really?). It kind of makes sense that you don't *need* structures like `while`, it just feels wrong
- Channels seem like they hold great promise
- `switch` cases in place of `if/else` blocks is fancy, but it feels like it was taken too far
- It could be really hard to switch back to something like Python or C# after a while in this language
- The fact you don't have to expressly define what implements an interface is weird

Overall I think the gif below sums up how I feel. Its got some strange features that are probably going to be insanely powerful once I get used to using the language. 

![goose](https://media3.giphy.com/media/v1.Y2lkPTc5MGI3NjExOGJ5ZTlqeXdzYXEzcmxnOG5vd3B4b2JlYWlhNnV3eDZrNnRhMWEyayZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/WGqRQcDTShkJi/giphy.gif)
+++
date = '2025-10-28T19:52:03-05:00'
draft = false
title = 'Why We Overcomplicate Things'
tags = ['rant']
categories = ['programming']
+++

Something I've been more and more aware of lately is the tendency of engineers, good engineers, to over complicate the hell out of something. Is it a product of the time they were working? Or is it something else?

Seeing engineers come out the other side of the age of monoliths, I wonder if this is a major contributing factor. It could be, old habits die hard. Before we had "the cloud", you had to build your own queues, callers, etc. I remember that time, even though I got in at the tail end of it when cloud was becoming the new thing. Everything lives in one service and talks to each other. What a mess. These engineers have taken that mess and slapped the label "microservices" on it in order to make it a distributed mess over http. They took the approach they knew. Looking at it through an archaeological lens, in the age of serverless as FaaS (Functions As A Service), its just atrocious. And through this lens it was "good enough" then, but not anymore. We've grown and expanded so far beyond these things of the past. This is like looking at punch cards, or the horse and buggy, or the Romans' [sponge on a stick](https://en.wikipedia.org/wiki/Xylospongium) for the bathroom. All great ideas at the time, but you don't see that in 2025. We have better tooling that ever before. I can literally pay per invocation of a function. Heck, I'm taking advantage of the free tier that so many services offer that this blog, along with several other projects are being hosted for no cost out of pocket to me. That would seem like absolute insanity for someone 25 years ago. 

A second reason I think engineers over complicate though, is its "their" code. They think they'll maintain it forever, and want it to withstand the test of time. But the truth is they won't. They'll find a new job, be fired, or worse. Then its someone else's baby and someone else's problem. I think the key here is emotional attachment to code is a bad habit, and progressing past that is a major milestone to becoming a really good engineer. I can remember being attached to my code, but those days are long past. Its not that I don't care, its that I know that the code only satisfies the present needs, and the future needs are always in flux. What works today won't work tomorrow. 

We have to learn that simplicity and documentation beat out fancy, convoluted solutions every time. We've been handed tools to make small, simple tasks; so lets use them to the best of our abilities. Make functions that do one thing, and do it damn well. Keep your code light and your tests sane. 
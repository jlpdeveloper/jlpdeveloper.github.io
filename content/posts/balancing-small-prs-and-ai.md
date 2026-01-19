+++
date = '2026-01-18T19:13:30-06:00'
draft = false
title = 'Balancing Small PRs and AI'
tags = ['ai']
categories = ['programming']
+++

One of the core tenets of a good working engineering team is to limit the Work in Progress (WIP). This has been written about so many times, I could spend an entire article just documenting all the people who say this is the key to efficient flow, so lets assume that's true. I was reading [this article](https://codecraftdiary.com/2025/12/20/development-workflow-failures/?ref=dailydev) and was reminded of that once again. One of the tenets of this article is to create small, reversible changes. But there's a strong counter to that happening in the era of AI. Agents and MCP make it incredibly easy to create thousands of lines of documentation, code, etc. at a rate never encountered before. 

I've seen it time and again, and sadly am guilty of it myself. AI can be incredibly useful for writing code, but it can write so much code no one can review it; and therefore no one knows what the hell is going on. How can we balance small work with the AI firehose? I think there are few ways we can do this. First of all, make sure your work is broken down into small chunks. You get the request to build feature X, but that requires a new endpoint, service, repository, tests, logging, and documentation. That's not one story, that's 4-6 stories easily. Each one is mergeable and could be easily feature flagged (if even necessary). This transforms the work from a large, unwieldy review request to a series of small requests. 

Second of all I think you need to be more cognizant of self review. The engineers job is changing from coding to reviewing. Its your responsibility to keep the AI on track and ensure that its code is well written and is conforming to the task at hand. I think this is where many people get lost. Its really easy to understand what the AI is doing when you're the human in the loop, but when that turns into 10-20 commits, all the context of how you corrected the AI is lost. All that remains is a few thousand lines of code no one else is going to have any hope of understanding. 

Lastly, I think we can start asking for opinions earlier. Draft PRs are cheap, and its easier to ask a colleague "does this PR seem to big?" than "can you look through this 5,000 line review?". Does it take a bit of time from someone else's day? Yes, but that time is less than what a bad PR would be. Over time, your team can start standardizing what "feels" like too big of a code review (at least in terms of files/lines changed). This will allow you to better standardize your review policies and allow you to know when a review is getting too big. There's no shame in splitting work into smaller portions. WIP is one of the major destroyers of a person or team's velocity. If you're trying to juggle too many things at once, then *nothing* is going to get done. 

So to recap, don't be "that guy" with AI pull requests. AI makes it incredibly easy to write alot of code, but then no one will know what the hell is going on. Its best to keep yourself deeply involved and ensure that your work is targeted and easily reviewable in small chunks. 
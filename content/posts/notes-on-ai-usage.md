+++
date = '2025-03-25T20:22:57-05:00'
draft = false
title = 'Notes on AI Usage'
categories = [ "programming"]
tags = ["ai", "llm"]
+++

I didn't get a chance to work on another Staff+ engineer post this week, so I thought I would share how I've been using generative AIs and my experience with them for this week.

Recently I've had the chance to compare Amazon Q and Copilot. Both seem pretty good, but I've found that Q has different ideas of what is a security concern over Copilot. Both do a pretty decent job with overall for the simpler things I ask. Both do good at writing unit tests with minimal hallucinations, but I find you should still consider this code boilerplate and run your own coverage and sanity checks against it. I do like that Q provides links to stack overflow, etc. when you ask it a question about a problem. 

One trap I've noticed that's very easy to fall into is using AI generated files as "good enough" (i.e. the "vibe coding" that everyone hates now). I'm lucky that logging issues were caught in code review, but also didn't enjoy that so many comments were left on that PR. 

Overall I think having the AI in my IDE is a useful tool, but I can tell its not going to replace engineers anytime soon. There's just too many contextual decisions between "do the thing" and implementing how the thing is done.  I think we should limit AI usage to tests and as a reference tool when we need a slightly more sentient rubber duck. 
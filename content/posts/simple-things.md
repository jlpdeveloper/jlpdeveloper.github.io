+++
date = '2025-07-08T20:44:39-05:00'
draft = false
title = 'Simple Things'
tags = []
categories = ['organization']
+++
This weeks topic is another obvious one, but I thought it would be good to talk about as I've reaped the benefits of it in the past few days. Today I'm going into why little things add up over time. There's a myriad of small things you can do that can make pay dividends in the future. From a simple email system to taking the extra time to set up extra configuration, the 30 minute tasks add up over time.

First I want to share a success story with small tasks. AWS frequently recycles tasks to upgrade the underlying host drivers and whatnot, you've probably encountered this if you run any Fargate workloads in AWS. In one critical app we set up lifecycle rules for stopping, stopped, and starting. Is it too many emails? Maybe. But I'm glad to have them. When AWS recycles that app, I'm confident I don't need to log in to the platform or AWS to validate my app *because* I get that set of emails in that order. It acts as both alarm and source of comfort surrounding that app. 

So what constitutes a "small" task? I like to define a small task as: 
- low mental complexity
- low time (1-2 developer "days") 
  *note:* a developer day is only how much time you get to put hands on keyboard, your mileage will vary based on the chaos in your job. 
- medium to high return
In my email example, it only took a few hours to get it to work and the return has been a confidence that the system is behaving normally. Other examples might be:
- automate that report you send weekly
- add automated tests around flakey api calls
- daydream/prototype a full refactor
-  [automating API testing](https://blog.usebruno.com/automating-api-testing-github-actions?hs_amp=true)

Do the small things that will make your life easier or more comfortable. Tools and practices like these are worth the security and quality you get in your code. 
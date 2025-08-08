+++
date = '2025-08-07T20:27:22-05:00'
draft = false
title = 'On Software Engineering'
tags = []
categories = ['programming']
+++

I recently read the article [Writing Code is not Software Engineering](https://rrmartins.medium.com/writing-code-is-not-building-software-d55b9cc9539a), which I highly recommend reading. I thought I would take this weeks article to share my personal experiences with it. First and foremost, context is king. If you don't know why you're writing something, you're going to get the how wrong because you never had a good target in the first place. The language and methods don't really matter. I've found I can write the same thing in C#, Go, or Python and achieve the same results. They are all just tools in my toolbox. Once you define the what and the why, then you can select the best tool for the job. If you're doing something that makes several other calls, use Go. If you're comfortable in C# and need it done fast, use C#. The key is knowing why, then you move on to the next step: planning.

Planning on a project is what makes a project great. You hammer out you're architecture and make your code domain aware and easily changeable. Being able to adapt to evolving business needs is one of the hallmarks of a well designed system. Such systems allow you to change minor components without refactoring dozens of other pieces. Each piece is independently testable, single focus/responsibility and just...does its job. I've worked in software long enough to see (and build) slop. You make a library and it turns into handling everything. Those kitchen junk drawer apps become the bane of so many developers existence. But its because someone didn't stop to think "hey if I take an extra day to make a new app, I'll save that much time every month forever." And that is the key with planning. Understand your tradeoffs and how they propel you to accomplishing your goal. Understand how to keep your code independent so your software is adaptable. 
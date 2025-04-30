+++
date = '2025-04-29T20:09:18-05:00'
draft = false
title = 'Review: JetBrains Junie AI Assistant'
tags = ['Ai']
categories = ['programming']
+++

I subscribe to the JetBrains all IDEs package. Recently, I learned that JetBrains released a new agentic AI named Junie via [this video](https://www.youtube.com/watch?v=95RQhqKRIeQ)(which is strangely unlisted now). I thought I would give it a try since I'm technically already paying for it and I have to say I'm quite impressed. I installed it in GoLand to help me on a project I'm learning to use Go on and overall it seems much better than other AIs I've used.

One of the main things I like about the Junie plugin is that its designed to be task based. You define a "task" for the AI to do, and off it goes. But that's not right, because it doesn't just go off and do some coding sorcery and spit out a fancy new feature. The first step it takes is to analyze the task and generate a multi-step plan that it displays. It then goes through each step, which can include looking at various files to understand the style of the code in the repository and then it starts working on the new code. Every step of the way, you can view the changes its making to various files. A second thing I like about the Junie interface is there is a toggle between coding/agentic mode and question mode that allows you to easily ask questions in the middle of tasks. 

I've been using Junie for the past two weeks and found that it does really well on the tasks I give it. Some examples include writing tests, recreating boilerplate for lambdas (in PyCharm), and to explain some concepts in Go. One particular note that I find impressive is that when writing tests, Junie will actually *run* the tests as well, then iterate on the tests until they pass. Its agentic mode has a "brave" option that allows the AI to run various terminal commands, so it can make new files, update tests, run tests, etc. Questions aren't just answered, they are answered with rich markdown files that allow conveying more information with their formatting. This can be seen as a down side as you have to *open* the markdown files, but its not that much of a hassle. It also makes the files more savable. 

So how does Junie stack up with other AIs? I've tried Junie, Amazon Q, and GitHub Copilot, and of the three, it seems Junie hallucinates the least. I like that it displays a plan of attack for a task. For some reason, it just feels more convenient, with Copilot being a close second (Q on the other hand is not a particularly enjoyable experience). I like that it is iterative in its approach. It has some trouble with terraform, but I haven't seen any AI that is up to speed on the latest terraform. An exception with Junie is it will analyze existing terraform and use patterns from that to create new files. I've even asked Junie to review code and its caught several flaws with my code as I continue learning Go. 

Now for the negatives, one negative I can say about Junie is that it saves files as UTF8 + BOM, which causes issues with reading files in GitHub actions. Second of all, its not in all the JetBrains IDEs yet, and there isn't a listed plan to bring it to Rider, so you're out of luck in C# (another language I frequently use for work). 

One last thing I want to mention on Junie is it has a guidelines system, akin to what I've seen with Cursor (though I've not used it). You enable this by creating a `.junie/guidelines.md` file, then add any guidelines you want. I commonly add guidelines such as "make sure to run git add on any new files you create" or "don't use xyz formatting for files", and generally it follows these guidelines. 

Overall, I highly suggest trying this out, especially if you use Go or Python heavily in your day to day work. The price is comparable to Copilot (or you already have it if you're like me and subscribe to the All Products package), and it provides a great AI assistant for money. 
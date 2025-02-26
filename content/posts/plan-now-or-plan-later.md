+++
date = '2025-02-26T11:21:39-06:00'
draft = false
title = 'Plan Now or Plan Later'
categories = ["project-management"]
+++

Today I want to talk about project planning and when it can occur. Typically, you want to do all your project planning that you can at the start of a project. Some things will always come up, but its best to always have as much planned as possible. For example, if you get sixty percent of the work identified and planned before staring a project, the remaining forty percent doesn't just disappear. It will usually manifest itself in odd ways and end up being more than forty percent because you've locked yourself into a path with previous decisions. Planning later always leads to stress, rushed projects, and things that don't meet the user requirements. 

## Why do we plan later?
Why do things come up later in a project? There are a few different reasons. The first reason can be attributed to two causes, which is there wasn't enough time spent at the start of the project (no duh). What I mean by this is either the project was rushed (a go live date was committed to stakeholders) or the project planning wasn't given enough priority.  Projects with predefined deadlines will almost always be rushed through the planning phase. Also if you're tasked with defining and estimating a project plan, but also "all the other things", that is another recipe for disaster. Task estimation and project planning is some of the deepest work anyone can take on and should be prioritized with large blocks of undisturbed deep work time. 

Another way that poor planning can manifest is if the project and some of its smaller complexities aren't fully understood. If someone doesn't fully understand how some things in the project fully work, then they make simplified assumptions about them. This can be compounded in projects that involve multiple teams where one engineer may not understand the black box of how another teams systems and processes work. 

## What's a "good" project plan to start with?
So how do we avoid failure? What do we consider a "good" project plan? We never have a perfect project plan, we just have a "good enough" plan. Some things can't be accounted for, such as critical personnel getting sick or needing extended leave. But other things we can make reasonable guesses about what we don't know. In the beginning of a project, there will be many things we don't know, whether we know we don't know them or not. An excellent example of this is the "Cone of Uncertainty" in [Software Estimation: Demystifying the Black Art](https://www.oreilly.com/library/view/software-estimation-demystifying/0735605351/), which I highly suggest you read. The Cone mentioned means that our estimates will have a high degree of uncertainty in the beginning of project because we haven't made decisions that will concretely affect the rest of the project. Decisions on architecture, language, etc. start at a very high level and as the project progresses, these decisions iteratively become smaller and the cone narrows to the final value of how much effort a project will take.

A more recent article on project breakdown can be found [here](https://swizec.com/blog/how-do-you-break-down-a-large-project/?ref=dailydev), where Swizec describes an iterative process to get tasks smaller enough to be measurable by referencing other stories. The core of both these literatures is that you need to use a concrete method to "count" the effort for a project and not rely on feelings. Relying on anything that isn't measurable isn't a good project plan. 

You typically need to plan a project with measurable pieces to 80%. *Software Estimation* states "a skilled project manager can navigate a project to completion if the estimate is within about 20% of the project reality.", so 80% should be your goal for a project estimation/plan. 

## Key points for a good project plan/estimate

- The project and adjacent topics need to be well understood to make educated decisions
	- Definitions, processes, etc. should be documented
- Questions need to be asked and answered iteratively and frequently. Any that can't be answered should be marked as critical risks to the project
- The project needs to be broken down iteratively until its small enough to be measurable
- The critical path has to be identified
- Any deferments of decisions need to be identified as risks to the project and planned for making said decision at the appropriate time
- Project plans/estimates need to be expressed as a probable range for the time it will take, not as a definite value
- Product requirements need to be clearly defined and translated to engineering requirements


Hopefully this post gives you some idea as to what you need to make a good project plan and provides some extra reading material to help you along in your journey to creating a good plan. 
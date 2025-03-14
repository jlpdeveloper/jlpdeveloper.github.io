+++
date = '2025-03-12T00:00:05-05:00'
draft = false
title = 'Playing Translator'
categories = [ "career-development"]
tags = ["staff+", "staff-engineer-series"]
+++
I think over the next month I'm going to start a series on what skills help make a staff engineer. Staff engineers responsibilities extend way beyond just coding expertise. Staff engineers rely heavily on many various soft skills; today we'll be discussing translating. What do I mean by translating? It can have a couple of different meanings, depending on the context. 

First we'll start with the simplest, in writing. Staff engineers are often tasked with breaking down product's vision into an actionable plan. We're handed a document that essentially states "I want service A to do X, Y, and Z" and tasked with breaking that down into a set of tasks we can either complete ourselves or delegate to others that will take someone's vision and make it reality. Depending on the complexity of the task, this can be a half hour writing a couple of tickets to several weeks worth of work for a major project. Staff engineers are expected to be able to understand the ask as defined in the design document, identify any gaps in the knowledge, and create a list of technical requirements. Once the requirements are agreed upon, the engineer can create a plan to satisfy the requirements. The technical requirements are another place that require the engineer to translate to a more abstract level for stakeholders to understand. For example, consider the following request: "We need to implement a system to store the names of pets". This can be broken down as such:


**Questions**
- Where do we currently store information about pets?
	- Should we append the name as part of this information?
- How will we access information about the pets?
- Can pets be renamed?

**Requirements**
- Create a new API with the following methods
	- `PATCH`: / Update a pets name
	- `GET`: /{:id} Get the name of a pet by id
	- `GET`: / Get all pet names

**Technical Tasks**
- Create a new database to store pet names
- Create controller for /pets calls
- Create pets service and repository
- Implement get all method
- Implement get by id method
- Implement update method
- ....


As you can see, several questions were translated out of that one sentence, as well as a high level requirement list. Furthermore a detailed list of technical tasks as partially created (I say partially because the list doesn't account for a new api or using an existing, infrastructure, CICD, documentation, testing, etc.).  Note that the requirements don't specify any technical specifics, but they do identify and break down "store pet names" into a series of api calls and methods that define how this will work technically.

The other way staff engineers translate is by identifying risks in seemingly innocuous sentences during discussions with product. For this I'll provide a real life example: the product manager said and wrote this sentence during discussion of a new feature: "persist the filters day over day". That immediately set off alarm bells in my head for two reasons. First, that sentence is a bit vague; it can't just me persist to a database, can it? Second of all, in the context of front end development, this can mean many other things. I immediately interjected and asked what was meant by that, as well as provided examples: "what does 'persist day over day mean? Do you mean in a database or like how Chrome can remember your last open tabs?". He said it was somewhat like the second example with Chrome, which set off more alarm bells. I then ask our front end expert "I don't think that functionality exists, does it?". He confirmed that no, that type of functionality didn't exist, so we needed to take additional time to break down that work and create alternatives for that functionality (we eventually agreed that cookie based was "good enough", but we should explore session and state management in the future). I think that is one of the true powers and responsibilities of a staff engineer, to have enough contextual cross team understanding to identify risks and "see around corners" as it is. This skill reminds me of [this xkcd](https://xkcd.com/1425/) in that one simple sentence is the difference between a one day story and a three month epic. 

A final way I'll mention in this post (though this list isn't exhaustive) is translating between two technical parties who can't see eye to eye. Sometimes two parties will not see things the same way, even though they are describing the exact same thing, just in a way the other doesn't understand. They are more so practicing talking "at" each other instead of "to" each other. In this scenario, its the place of the staff engineer to interject and try to explain things in a way that both parties can understand before things get heated. Bringing shared understanding to the table is a key component of "translating" in this context. 

In summary, translating is about a few different things. It's about taking non technical requirements and turning that into questions and technical requirements. It's also about recognizing when something isn't well understood and phrasing it in a way to provide clearer meaning to all. It's about being able to see things from multiple contexts and provide a shared understanding. That last sentence is truly what translating is at its core and staff engineers need to be aware of the room and understand when translation needs to happen. 
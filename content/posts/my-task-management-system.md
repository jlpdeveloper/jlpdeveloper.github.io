+++
date = '2025-01-07T19:34:54-06:00'
draft = false
title = 'My Task Management System'
+++

Over the past two years or so, I've been working on a new way of measuring work. This has evolved from a simple task list of things I need to get done for the sprint and other tasks, like reminding myself to ask someone a question or put in for time off. This concept has evolved into a daily note that houses three main areas to put tasks: Goals, Meetings, and Bonus Items. These three areas are important and hold distinct types of tasks. 

## How I Organize My Day

First, I want to deviate slightly to write about how I organize my notes. I use [Obsidian.md](https://obsidian.md/) with a host of plugins that help me keep organized and productive though the day. One of the core things I use out of Obsidian is the concept of a daily note. Daily notes allow me to:

- Plan my day
- Create links to the days meetings for note taking purposes
- Write notes, keep code snippets, etc. 
- Monitor how I feel about a day for introspective purposes
- Have a useful list of links, commands, etc. on hand

Obsidian is an incredibly powerful tool that allows my notes to be linked, searchable, and measurable (more on that measures later). It also supports templating, which is key to the daily note
## My Three Types of Work

First is Goals, which will hold any and all planned tasks for the day that don't require extended interactions with other people. Examples include progress on work items, reminding myself to send someone a file, a reminder to put in for time off, work on presentations, or any other chore. The important point of Goals is they are planned. The second major areas is Meetings; this one should be pretty self explanatory. This includes all meetings you need through the day, including standup, project planning meetings, retrospectives, and deployments. These are planned as well. The final item is Bonus Items. Bonus Items hold all tasks that come up during the day. Bonus Items represent the chaos or entropy that is inherent in your work life. So why these three? 

I chose these three because I feel they encapsulate the majority of items that happen in an average day. One could argue for a forth category for chores such as checking email or answering the phone, but I feel these are natural occurrences that don't have to be expressly documented as things that need done in a day. If a call or email becomes a lengthy investment, I keep an independent notes section under my goals, meetings, and bonus items that allows me to document things of note through the day. 

If you've read [The Phoenix Project](https://www.oreilly.com/library/view/the-phoenix-project/9781457191350/), you'll see some similarities between my categories of work and `The Four Types of Work` described in the book. The major difference is The Phoenix Project describes an enterprise wide strata of work, while my categories are focused to an individual. You could possibly use my system for a small group of individuals, such as a team of 2-4, but I think it would be very easy to start blurring the lines between the two. 

### Sample Daily Note

Below is a sample daily note for a typical day. I checkboxes for each item and mark them off as I complete them. I use the [Minimal Theme](https://minimal.guide/home) so that I can use the `/` to indicate to myself an item was partially done. I also combine task lists and bullet points to help remind me about things I wanted to bring up in standup or any other meeting that doesn't require its own page. Meetings that require notes or action items are created as links to pages that don't exist yet. Once the meeting has started I click on the link to create the page and apply my meeting template to it.  I use `-` and `>` to mark a meeting as cancelled or moved, meaning it was on my calendar but was either deleted or rescheduled.

```markdown

## Goals
- [x] Code Review ticket 1
- [ ] Ticket 2
	- [x] Review WIP code
	- [/] Run/Update Tests
	- [ ] Create PR

## Meetings
- [x] Standup
	- Ask about feature 1!
- [ ] [[Meeting with Product on new feature]]
- [-] [[Weekly Update]]

## Bonus Items
- [x] Look into performance issue
- [ ] Find documentation on legacy feature
```

## Why Categorize Work Like This?

I believe my categorization of work is useful for a few different purposes. First of all, recording all your tasks, meetings, and unplanned events allow you to *count* them. Once you do this long enough, you will get a gut feel on how many items you can get done in a day. For example, I have a range of 8-14 items I can get done in a day. I give this as a range due to the number and length of meetings in a day, but I've found I'm consistently in this range over the last year. 

Second of all, it can help you gain insight into what is *wrong* with your work day. Take the following table for example:

| Day       | Goals | Meetings | Bonus Items |
| :-------- | :---- | :------- | :---------- |
| Monday    | 2/5   | 4/4      | 3/4         |
| Tuesday   | 1/3   | 5/5      | 2/2         |
| Wednesday | 0/5   | 2/6      | 8/12        |

Looking at the days in this table, I would surmise that my week is too meeting heavy to get any deep work done. I would also guess that Wednesday was some sort of production incident that required all hands, so no planned work got done. One important note here as well is that all the unplanned work (as well as the meetings) is interfering with planned work. 

### What is this telling me?

I find this information useful in seeing how much entropy (a measure of chaos) exists in a workplace. All workplaces have some chaos, but they vary for place to place. Consistent high entropy over a large time frame can make any sort of planning near impossible. It also points to some indicators of other issues such as:

- planning on projects was poorly done
- you've become a source of knowledge to too many
- inadequate testing leading to production issues

For the average engineer, the hope is that the `Goals` list will be the highest average count. For other roles, such as triage engineer or manager, you may see the `Bonus Items` or `Meetings` items be the highest counts.
### What do I do with this Information?

 This method isn't prescriptive for saying any particular count of an item is a bad thing; it should be viewed as a tool that allows you to:

- Understand where your time is going
- Give a measurable value to the feeling that "work is slipping"
- Understand your average capacity

The method also allows you to experiment with new ways of working and allow you to measure the results of those experiments. 

If you see you are consistently adding work to the `Bonus Items` category and feel that this is distracting you from planned work that needs done, that should be a sign to you that you need to do something. This could be to start attempting to delegate unplanned work, talk to your manager about restructuring your planned work, or start telling others you can't participate in so many meetings. Putting off planned work can be disastrous for a project as what you planned to do usually contributes directly to a sprint goal, which could also be a customer commitment. Information about what happened should also be bubbled up in your standup as well. Its good for the team to know that chaos is happening and could affect something they need to complete their work. 

## An Important Final Note

To make this system work, you have to put in the discipline to add all your bonus items to your task list and check them off. This is best done when something comes up, but could also be done at the end of the day or during a break. I have a key command set that allows me to add common requests such as code reviews and a separate one that adds things to an "Inbox" that allows me to better categorize it later. The key is, as with all systems, writing things down. If you don't put the work in, a system isn't going to put in the work for you. 
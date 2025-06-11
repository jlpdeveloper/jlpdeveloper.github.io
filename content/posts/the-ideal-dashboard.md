+++
date = '2025-06-10T20:51:04-05:00'
draft = false
title = 'The Ideal Dashboard'
tags = []
categories = ['organization']
+++
I'm back after a little break last week (sorry I couldn't think of anything *good* to write for last week) and I just had a thought about 20 minutes ago. I'm winging this entire post, more than I usually do, but here goes. What is a common problem that many companies have? I think its communication. Engineers don't have an easy way to gather info about what's going on in their company. My thought was, "what would my ideal dashboard look like?" From there I came up with the following image, mocked up using obsidian's canvas feature: 

![the ideal dashboard](/ideal_dev_dashboard.png)

So why these 6? And why a dashboard at all? I had thoughts that I could had graphs, messages, etc. but it honestly seemed like overkill. Who wants to look at a graph before their morning coffee? As for the second question, a dashboard for the engineering department that allows engineers a micro and macro view of work, pertinent information, and a scratchpad system  Lets start at top left and go around the dashboard. 

### 1. Upcoming Deployments
Honestly I struggled if this should be its own "widget" or if it should be part of announcements. I finally decided it should be its own for the fact it can provide more critical information if it were integrated with a [service dependency system](https://github.com/jlpdeveloper/service-dependency-api). If you had a prioritized view of services that are direct upstreams of your own services, this view would be invaluable in being able to easily identify ripple effects in your systems. A view of upcoming deployments is also useful for seeing high risk, or other larger initiatives that you need to be aware of.

### 2. My Todos
This is your work log for the day. As you can see, my [task management system](https://blog.joshpotts.net/posts/my-task-management-system/) is bleeding into this view. I believe it is important (and rewarding!) to have a checklist of what you intend to accomplish in a day, it keeps you on track and helps you remember what you were working on the previous day.

### 3. Meetings
Meetings, the necessary evil that keeps us from coding. Having a quick view of your upcoming meetings for the day allows you to better determine what can be on your todo list for the day. Additionally, this list helps you prepare for any upcoming meetings you'll need to heavily participate in. 

### 4. Announcements
The announcements block is the one I added last, but what made me start thinking about this dashboard. Department wide announcements are usually on slack, and therefore are usually lost in a sea of other notifications. I find engineers usually have two modes for notifications, clean inbox, but not much time to ingest a message before going to the next one (this is the camp I'm in), or 200+ unread message that will probably stay unread until the end of time. Neither of these camps are going to get good information from a slack message. Announcements, in this context, are different because they are smaller, and stay in view longer (because you usually stay on your todo page). 

### 5. Scratchpad
This one is probably the most controversial on the list, due to the fact it can be easily replaced with a more robust note taking system (like Obsidian). It does it with my task management system and it can serve as a place to leave yourself notes and record unplanned work. I view it as a place to store your private notes about the day to help you better document any unexpected things throughout the day. 

### 6. Roadmap
This is the macro view for the engineer to see what the company is prioritizing currently and in the coming months. This view should show all initiatives across all teams. While it may not pertain to you, its important to keep tabs on what others are doing because you may be able to borrow a concept or component someone has already done, making your life easier. 


Now that I've explained the items, what does this give your typical engineer?
- The ability to plan their day against their meeting schedules
- A view of company priorities
- An easy way to communicate with other teams via announcements
- A way to to identify risks 

Do tools like this already exist? Of course, but I haven't seen one yet that does all of this. The closest I've seen to doing it all is [huly](https://huly.io/), but even it doesn't have a robust enough note taking system (or a roadmap if I remember correctly). Usually this information is scattered in Jira, Google Calendar, sticky notes, Confluence, etc. There's no easy, at a glance view. 

The more I look at this, the more I wonder how hard it would be to build, I could connect some tools (like Google Calendar and my own service dependency api), but others would be a net new build. I may start a github project for this. 

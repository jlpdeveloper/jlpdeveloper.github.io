+++
date = '2025-10-07T19:47:32-05:00'
draft = false
title = 'My Experience With RLS'
tags = ['sql']
categories = ['programming']
+++
I've been using [Supabase](https://supabase.com/) lately for a new project and had the opportunity to work with postgres's row level security (RLS). Its been interesting to say the least. I can see its usefulness, but it has some foot-gun properties that are kind of hard to get used to if you've never used it before.

## The Good
- Abstracts permissions down to the database layer
- Simplifies queries in the application layer
- Keeps users limited to only their data set

## The Bad
- Its really easy to forget to set up the proper policies
- Policies for complex relationships get complicated quickly
- Can cause really hard debug paths if you have an elevated login

## Conclusion
So that seems like pretty significant cons, so is it worth it? Honestly I think so. Being able to simplify your queries to something like `select content from user_posts` makes your application code so much easier. Honestly I think its best used when your users aren't sharing data (i.e. teams, organizations, etc.). RLS shines when the user is consuming or creating data exclusively for the individual. While you can implement multi user RLS, it can be complicated. On my project I found that it was doing alot of joins to the `organization_users` table to check both organization membership and permissions (as I had very light RBAC in that table). 

Overall I think its a powerful tool in the right context, like so many other tools. Use it wisely, or you'll just make your life more difficult.
+++
date = '2025-02-19T19:42:59-06:00'
draft = false
title = 'My Experience with Conventional Commits'
categories = ["programming"]
tags = ["git", "version-control"]
+++

Do you ever look at a commit message and think "this is just awful"? I'm sure you have, especially when doing a code review. `git commit -m "stuff"` might work for personal projects or when you're frustrated, but you should work towards a standard way of doing your commit messages. Different places have various standards, but one open source standard I've adopted is [conventional commits](https://www.conventionalcommits.org/en/v1.0.0/). It's taken several months to get into the habit of using conventional commits, but now that I've gotten used to it, I can't imagine not using this commit style. 

I won't rehash the work in the link above, but I will give a quick example of a commit message in the manner I've started using it. In this example, you're working on modifying the front end so that the hover text on a button is different. The commit would like like:

```
chore: updates hover message

Update the hover message for the cancel button to better describe the cancellation process

ticket: JIRA-1234
```

In this example, you see the first line is the type of commit and a quick blurb. The second line (the body) is a more detailed description of the change. The final line, the footer, is a customization I use that allows me to reference the ticket in the commit message (to keep with company standards). I do one to speak to one deviation I find myself making from the standard; I like using a work in progress (`wip`) type commit when I want to save my work on a branch but I'm not ready to formally finish the work needed for the branch. I use this tag to know that this code is highly experimental and is likely to change when I review my commit history. 
## Why Conventional Commits?
So what makes conventional commits so useful? First of all it provides an agreed upon standard that many people use and provides information in a concise manner.  From the example above you can easily see if a commit is a new feature, a bug fix, or otherwise. It can also carry more information, such as using the `!` symbol to indicate a breaking change. It also gives you a quick description of the commit. I find this especially useful for squash merge commits. I craft my squash commit message into a conventional commit message that has all the important information about a change, a detailed description, and a reference to a Jira.  Secondly, a standardized format allows for automation. We can use scripts in GitHub Actions or other CICD software that can parse the information the commit message and do tasks like update the version, send a warning announcement on slack of a breaking change, etc. Additionally the standardized format becomes something reviewers, etc. begin to expect. Finally, it makes you stop and think about your commits. Instead of one commit for "fixed bug" that's 30 files and 500 lines added, you have to stop and think about what's in the commit and how that relates to a message. That one commit then becomes a `fix` commit, a `tests` commit, a `docs` commit, and finally a `chore` commit to increment a version. This adds value to your commits for many reasons, such as readability in a pull request, reversibility, and the ability to easily target to show as an example for others. 

In summary, I highly recommend adopting the conventional commits standard. It takes a bit to get used to, but once you fall into the habit, it will change the way you separate your work in git commits. 

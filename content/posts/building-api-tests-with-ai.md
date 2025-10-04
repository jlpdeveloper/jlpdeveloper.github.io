+++
date = '2025-10-04T15:05:28-05:00'
draft = false
title = 'Building Api Tests With Ai'
tags = ['ai', 'testing']
categories = ['programming']
+++
So lately I found a new pattern to increase my productivity. I work on APIs pretty extensively, and have adopted using [Bruno](https://www.usebruno.com/) to test with and store my test calls in my repo with the api. Since Bruno calls are basic text files, I found I can do the following:

- use a swagger page to collect curls for all the calls I make for setup and testing
- feed those calls into copilot, telling it to use them to set up the pre and post script runs
- then tell copilot what specifically to test for and have it create a bruno file for that call (or update one that has the bare bones for the call I'm making)
- additionally, I will tell copilot to update the docs section with how to manually run the test in case QA wants to review manually

I've found that this process greatly speeds up how I test and has completely replaced integration tests in some instances. Being able to quickly validate how the code behaves in an environment (instead of contriving an example) and then be able to repeat and share it at will is a very powerful ability. Do I have pretty coverage reports? No, but I have confidence in my code. And I'm building that confidence faster than ever.
+++
date = '2025-10-21T19:45:35-05:00'
draft = false
title = 'My Take on the Aws Outage'
tags = ["aws"]
categories = []
+++

Monday, 2025-10-20, was one hell of a day. The AWS outage started somewhere between the previous evening into the early morning. I was up at 4am trying to figure out how to get data out of Dynamodb. Then I spent the rest of the day babysitting services, desperately waiting for ENIs to become available. 

Supposedly the problem came from DNS records to DynamoDb. Honestly that seems very strange to me. Why would a rollback of DNS cause us to not have ENIs available? We couldn't create EC2s, ECS, or any other types of services that require direct interface into the VPC.  They say there was a backlog of serverless instances queued up, but who knows until the official post mortem comes out. It seems strange to me they couldn't purge the queues of serverless invocations, but I've seen stranger things happen (such as once a drive disconnect request finishing after a year in queue). I also found it very odd that us-east-1c came up first and many things were asymmetrically balanced into that AZ. 

Anyway, this week has already been a long month, so just wanted to put out my experiences with the AWS outage of '25. Hopefully we know more soon and more processes are put in place to prevent stuff like this from happening in the first place
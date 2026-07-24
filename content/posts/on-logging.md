+++
date = '2026-07-21T19:49:05-05:00'
draft = false
title = 'On Logging'
tags = ['logging']
categories = ['programming']
+++

I wanted to write today about seeing how a team can effectively turn around a bad logging situation and how nice it is to see good logs when debugging an issue. Several months ago I stumbled across [logging sucks](https://loggingsucks.com/), which introduces the concept of a wide log that encapsulates and the key logs about a specific event. I shared this at work and even wrote a rough POC on a generic wide logging system in C#. This was done because while Serilog is an effective C# logger, the implementation that's been inherited is interesting to say the least. The idea of the POC is that a thread safe logging object is instantiated with a `using` statement in C# that creates something akin to Odin's `context` object, only scoped towards logging. A log will have steps, warnings, errors, and key metrics about the event its logging (be it an api call or event processing). The team was also excited about it, but sadly we had to put the POC on the shelf for the time being.

Fast forward several months and I've moved to working with another team, but I get pinged on a tricky bug in the old application. I know my old team is swamped and there's money on the line with this bug, so I jump in. I was honestly dreading it a bit, this application's logs are notoriously unstructured and hard to read (lines like `Prop: List<Object>` are very common). I get to the logs and what do I see? Wide logs that detail the event! I knew they had been doing a bit on it, but it was so nice to see a log that actually made sense instead of the pile of garbage I was expecting.

I'm very proud that the team was able to take time to prioritize the technical issues that they had with the older logging setup. The new wide logs are already paying dividends; my investigation went from an hour to ~10 minutes since I had a *good* log to work from. Additionally the wide log structure has greatly reduced the volume of logs published by the app, reducing our cloudwatch spend while making it so much easier to understand an alarm on key errors. The team is now positioned to be able to proactively know about and take action on issues where before it was usually a customer complaint that was the first sign of issue. 

It's so easy to take good logs and good logging mechanisms for granted. A good log needs to have some key factors. First and foremost, it has to tell you something you need to know. In JavaScript we've all done the `console.log('got here!')` , but in the long run that gives us no value. To be a "good" log, I think a log needs a few key characteristics: 
- correlation id: what does this link to
- timestamp
- error information
- contextual information

`Error: cannot insert to order database` isn't helpful. It has the error information, but its missing the context. I have no idea what was trying to be inserted or why that data could fail. We've been creating logs like the following:

```json
{
	"event": "create_order",
	"status": "failure",
	"error": "cannot insert into order database",
	"timestamp": "2026-07-05T00:12:34.234Z",
	"ref": "ordersService.createorder",
	"correlation_id": "1234",
	"context": {
		"object": {
			"id": 🦆,
			"customer_id": 1234,
			...
		},
		"http_request_id": "1234"
	}
}
```

this log tells you exactly where the error came from, what correlates it to other non wide logs (logging isn't an either/or, its a what's valuable decision), and what data produced the error. 

I think that's all to this post, I mainly wanted to call out the value of wide logging and that logs must be thought through, they can't just be slapped in anywhere. 
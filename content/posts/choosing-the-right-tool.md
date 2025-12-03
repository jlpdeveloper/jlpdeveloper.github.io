+++
date = '2025-12-02T19:27:34-06:00'
draft = false
title = 'Choosing the Right Tool'
tags = ['ai']
categories = ['programming']
+++
I've been working on an MCP server for my service atlas api. My original idea was to do this in Golang, but I gave up on that path. I wanted to talk a bit more about the why and the alternative in this post.

## Go vs Python?

Golang offers a very robust library for MCP server development. A library I really, really wanted to take advantage of. But as I got past `HelloWorld`, I found a major problem: the library was really clunky to use. I found myself writing ALOT of ceremonial code, something I've found I absolutely despise with C#. The code worked, and it worked well, but it just didn't feel like the right tool for the job. 

So what did I do? I started a new MCP server project using FastMCP, and the difference was night and day. I was able to re-create four hours of work in Golang in about 20 minutes in python. FastMCP has clearly won the war for building MCP servers, its night and day how much better it is to work with. After I verified my python version, I deleted my Go MCP server and I haven't looked back. I want to show a quick comparison of what the Go code looks vs the python version

```go
func helloWorld(_ context.Context, _ *mcp.GetPromptRequest) (*mcp.GetPromptResult, error) {
	return &mcp.GetPromptResult{
		Description: "Hi prompt",
		Messages: []*mcp.PromptMessage{
			{
				Role: "user",
				Content: &mcp.TextContent{Text: "To say hello to a user, use the `hello_world` tool, passing in a required 'name' parameter." +
					"It will return a greeting message."},
			},
		},
	}, nil
}


type Input struct {
	Name string `json:"name" jsonschema:"the name of the person to greet"`
}

type Output struct {
	Greeting string `json:"greeting" jsonschema:"the greeting to tell to the user"`
}

func HelloWorld(_ context.Context, _ *mcp.CallToolRequest, input Input) (
	*mcp.CallToolResult,
	Output,
	error,
) {
	return nil, Output{Greeting: "Hi " + input.Name}, nil
}


func main() {
	// Create a server with a single tool.
	server := mcp.NewServer(&mcp.Implementation{Name: "Service Dependency API", Version: "v1.0.0"}, nil)
	mcp.AddTool(server, &mcp.Tool{Name: "hello_world", Description: "say hi"}, HelloWorld)
	prompts.SetupPrompts(server)
	// Run the server over stdin/stdout, until the client disconnects.
	if err := server.Run(context.Background(), &mcp.StdioTransport{}); err != nil {
		log.Fatal(err)
	}
}
```

Note how much work is in this code versus the python implementation:

```python

mcp = FastMCP("Service Map MCP")

@mcp.prompt('get_services_by_team')
def prompt_hello_world(name: str) -> str:
    """
    Prompt for telling the AI how to get services if it has a team id
    :param team_id:
    :return:
    """
    return f"""
	   To say hello to a user, use the `hello_world` tool, passing in a required 'name' 
	   parameter. It will return a greeting message.
	"""
	
@mcp.tool()
def hello_world(name: str):
    """
    Gets a list of teams that own a service based on id
    :param service_id: the guid for the service
    :return: a list of teams objects
    """
    return f"Hi {name}"
    
# Run the FastMCP server with STDIO transport
mcp.run()

```

## Lessons Learned

The important lessons here I want to highlight is that you have to choose the right tool for the job. This means the right language, the right technology, the right front end. Different languages have different strengths and weaknesses. Can you do anything in any language? Mostly yes. But will it be more work for you? Also mostly yes. 

You also shouldn't be afraid to change when you realize you're going in the wrong direction. Being able to admit you're wrong is a key element of being a senior+ engineer. Don't fall into a sunk cost fallacy. If you find yourself fighting your code with `HelloWorld`, its not going to get any better. 
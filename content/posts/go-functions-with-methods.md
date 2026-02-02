+++
date = '2026-02-01T20:21:55-06:00'
draft = false
title = 'Go Functions With Methods'
tags = ['go']
categories = ['programming']
+++
I was reading [this article]([https://rednafi.com/go/mocking-libraries-bleh/?ref=dailydev](https://rednafi.com/go/mocking-libraries-bleh/?ref=dailydev#function-type-as-interface))'s section on "Function type as an interface" and thought this was a wild concept to see in any programming language. I created a different example [here](https://go.dev/play/p/D-W9mWx_ORh), that highlights the concept. Essentially, you create a type for a function signature, then add methods to that type. So a function....now has methods. Coming from any other language, this sounds absolutely insane. Hell even in go, this sounds insane when its first presented. But I didn't dismiss it as just a strange side effect of go. Could it have use?

After some thinking about it, it does have practical use. The primary use case I can see is having a way to invoke and sanitize function inputs safely.  Below is a contrived example where the function will fail 50% of the time. As you can see in the invoke, several things are taken care of:
- a context timeout window is setup
- the input is forced to lower case
- the input is checked to be less than 100 characters

```go
package main  
  
import (  
    "context"  
    "errors"    
    "log"    
    "strings"    
    "time"
    )  
  
type FlakeyFunc func(string) (string, error)  
  
func (f FlakeyFunc) Invoke(ctx context.Context, s string) (string, error) {  
    ctx, cancel := context.WithTimeout(ctx, 100*time.Millisecond)  
    defer cancel()  
    if len(s) > 100 {  
       return "", errors.New("input string too long")  
    }  
    return f(strings.ToLower(s))  
}  
  
func main() {  
    useFlakeyFunc(func(s string) (string, error) {  
       now := time.Now().UnixMilli()  
       if now%2 == 0 {  
          return "", errors.New("flakey function failed")  
       }  
       return s, nil  
    })  
}  
  
func useFlakeyFunc(f FlakeyFunc) {  
    _, err := f.Invoke(context.Background(), "Hello World!")  
    if err != nil {  
       log.Fatal(err)  
    }  
}
```

"Ok, so what?" you're probably thinking. All of this could be in the function that's invoking the `FlakeyFunc`. And that's true. The power of this shines when the type is exposed and can be used in other types. It also shines when this function may be invoked in many places. Instead of copy/pasting (as those who hate Golang are woe to do when decrying `if err != nil`), this encapsulates your safety checks into one easy to access spot. If someone writes a new `FlakeyFunc`, it can be called safely as well. 

This pattern also allows you to use simpler types (i.e. functions) to satisfy interfaces. As shown in the original article, this is incredibly useful for testing as you don't *need* a struct to test with. It can also be used to better explain intent. In the following code `Validator` makes much more sense than passing a function that returns a bool everywhere, while simultaneously not requiring a full struct.

```go
type Validator func(string) bool

func (v Validator) Validate(s string) bool {
    return v(s)
}
```

In conclusion, is this just a weird side effect of go concepts? I think not. While not super apparent, this behavior has many benefits in the correct situations. The key is knowing of its existence and knowing when to use it. 
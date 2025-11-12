+++
date = '2025-11-11T19:34:26-06:00'
draft = false
title = 'C# Extension Methods'
tags = ['c#', 'go']
categories = ['programming']
+++

Its officially time for a new [.Net LTS Release](https://learn.microsoft.com/en-us/dotnet/core/whats-new/dotnet-10/overview), and with it comes C# 14, a new iteration with quite a few fancy new features. One such is covered in [this video](https://www.youtube.com/watch?v=VSGeoxPszHU), which shows the use of extension methods. I wanted to share my initial reaction of this video. 

First of all, this doesn't read like old school C# anymore. This reads like golang. Take the below example

```csharp
record User(Guid id, String username)

public static class UserCreation{
	extension(User){
		New(string username) => {
			return string.IsNullOrWhiteSpace(username) ? throw new ArgumentException("username is required") : User(Guid.NewGuid(), username); 
		}
	}

}
//in another file/class/method
var user = User.New("john.doe");


```

is almost the exact same as 

```go

package user  
  
import (  
    "errors"  
  
    "github.com/google/uuid")  
  
type User struct {  
    Id       uuid.UUID  
    Username string  
}  
  
func New(username string) (User, error) {  
    if username == "" {  
       return User{}, errors.New("username is required")  
    }  
    return User{  
       Id:       uuid.New(),  
       Username: username,  
    }, nil  
}  
// in another package
myUser, err := user.New("john.doe")
```

I find it incredibly interesting that they read so similarly now. Older C# devs will be more familiar with something like this:

```csharp
public class User {
	public Guid Id {get;set;}
	public string Username {get;set;}
	
	public User(string username){
		if string.IsNullOrEmpty(username){
			throw new ArgumentException("username is invalid");
		}
		Id = Guid.NewGuid();
		Username = username;
	}
}


var myUser = new User("john.doe");

```

Is Microsoft trying to make language switching easier? Or are they copying out off Google's proverbial test with language efficiency? I'm not sure, but its a welcome change for someone like me that still works heavily in C#, but enjoys dabbling in Go. Its much more idiomatic, as the Gophers say. 

The second realization about extension methods was discomfort. Being able to define customizable logic that only exists in certain contexts feels like a recipe for disaster if you're not careful. For example:

```csharp

record Temperature(float celsius)
public static class Temp1 {

	extension(Temperature t){
		GetTemp => {
			return t.celsius;
		}
	}

}

public static class Temp2 {
	extension(Temperature t){
		GetTemp => {
			return (t.celsius * (9/5)) + 32;
		}
	}
}

```

Which is "correct"? Do you need temps in a single scale? If so, code like this will make your life absolute hell. Or worse, you'll have a catastrophe. While yes, I can see a lot of potential upsides to not having to add to a class/record (or write a method that inputs the record) for specific scenarios, this seems like a very powerful footgun, especially if you have junior engineers wanting to prove themselves. 

Overall I'm excited by what we can do with C# 14 and how similar it is becoming to go. I won't claim to be an expert or power user of C#, and honestly I may not ever have need for some of the features offered, but I can tell you as someone who looks at C# 7.0 code occasionally, the language has come a long way and its good to see.   
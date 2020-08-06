---
layout: post
title:      "What is Async/Await"
date:       2020-08-06 22:08:48 +0000
permalink:  what_is_async_await
---


 One of the harder topics for me to understand when going through the JavaScript section at Flatiron was how to handle promises. Any time I tried to handle asynchronous actions, I would get confused as to what I was getting back, and how I could use that data. It would typically look something like this:

```
function doSomethingAsynchronous() {
  return fetch('goGetSomeData')
	           .then(response => response.json())
			   .then(data => console.log(data))
		       .catch(error => console.log(error))
}
```

In my opinion, using the async/await syntax is more readable. We could do something similar to the above like:

```
async function doSomethingAsynchronous() {
  const response = await fetch('goGetSomeData')

  console.log(response)
}
```

`async` is a special keyword in JavaScript that can be placed before a function, and can be used with either function declarations, or function expressions. What this does, is make the function return a promise. 

When we use the `async` keyword, we can also use the `await` keyword inside of that function. So what we're doing in the example above with the `await/async` syntax is telling JavaScript to give us a variable called response. The value of response will be whatever the value of the promise is once it resolves. 

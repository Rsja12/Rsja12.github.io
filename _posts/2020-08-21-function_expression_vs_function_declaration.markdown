---
layout: post
title:      "Function Expression vs. Function Declaration"
date:       2020-08-21 19:43:20 +0000
permalink:  function_expression_vs_function_declaration
---


I would get confused any time I heard either function expression or function declaration. I didn't know which was which, or how they differed. So here is an example of what they might look like.

Function expression:
```
let doSomething = function() {
  return something
}

let doSomething = () => {
  return something
}

let doSomething = function name(){
  return something
}
```

As you can see, we are creating a variable and assigning a function as its value. Function declarations look a little bit different. 

Function declaration:
```
function doSomething() {
  return something
}
```

One of the biggest differences, and most important things to keep in mind when working with either of these, is how they can, and can't be used in your program. 

With function declarations, you could do something like this:
```
doSomething(); // --> something

function doSomething(){
  return something
}
 ```
 
Function declarations are hoisted. If you tried to do this:

```
doSomething()

let doSomething = function() {
  return something
}
```

It just would not work. Happy Coding!



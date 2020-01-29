---
layout: post
title:      "VAR, LET, & CONST"
date:       2020-01-29 18:46:46 +0000
permalink:  var_let_and_const
---


In the beginning there was var. Before ES6, the only way to create variables in JavaScript was with the var keyword. Var has either global or function scope depending on where it is declared. Variables declared with var also allow us to re-declare them meaning we can do :

```
var a = “Hello”
var a = “Goodbye”
```

And we will not get an error. This can cause unexpected bugs in our code. If we have the following code:

```
var a = “Hello”
	If ( 2 > 1 ) {
		var a = “Goodbye”
	}
console.log(a)
```

Our output will be `Goodbye`.

Let and const are the new ways of declaring variables. Let allows us to re-assign variable values, but not redeclare them, so for example:

```
let b = “Hi”
 let b = “Bye”
```
Throws an error because we already declared b. So what we would have to do to re-assign is simply:

```
let b = “Hi”
b = “Bye”
```

With let, our variables become block scoped, meaning they are only visible and accessible from within the entire block but not outside of it. So with our previous example:

```
let a = “Hello”
	if ( 2 > 1 ) {
		let a = “Goodbye”
	}
console.log(a)
```

Our output becomes `Hello` because our console.log is outside of the block so it only has access to the variable declared in the global scope. 

When it comes to const, our scope is the same as with let. 

```
const a = “Hello”
	if ( 2 > 1 ) {
		const a = “Goodbye”
	}
console.log(a)
```

The output is `Hello` for the same reason. The difference between let and const is that variables declared with const are not meant to be changed. So if we do:
```
const a = “Hi”
  a = “Bye”
```

 We get an error saying we can’t re-assign a constant variable. With const we also have to do variable declaration and assignment at the same time.


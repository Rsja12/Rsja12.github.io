---
layout: post
title:      "Type Coercion"
date:       2020-07-17 14:43:14 +0000
permalink:  type_coercion
---


What is Type Coercion? According to the MDN web docs, type coercion is: 
> the automatic or implicit conversion of values from one data type to another (such as strings to numbers).

In JavaScript, type coercion can happen implicitly or explicitly. 

Explicit coercion is when you see some code that looks like:
```
let num = '100'
parseInt(num)
```
In this case, it is being explicitly shown that the intent is to convert the value of num from a string to a number. 

Implicit coercion is a bit different. An example would be:
```
let num = '10'

if (num) console.log(num)

```
In the example above, the expression evaluates to true, so the value of num would be logged to the console. 


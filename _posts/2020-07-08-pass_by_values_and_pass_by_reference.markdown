---
layout: post
title:      "Pass By Values and Pass By Reference"
date:       2020-07-08 23:13:43 +0000
permalink:  pass_by_values_and_pass_by_reference
---


```
let a = 10
let b = a
console.log(a, b)
```

What do you think will be output to the console?

The result is `//--> 10 10`

What if we do the following:
```
let a = 10
let b = a
a = 5
console.log(a, b)
```

Now, the result is `// --> 5 10`.

In JavaScript, when a data type is a primitive (String, Number, Boolean, Undefined, Null), like in the examples above, all we're doing when we say `let b = a`  is saying 'Hey JS, I want a variable named `b` whose value is a copy of the value held by `a`'.

Then, when we reassign the value of `a`, nothing in `b` changes. They're separate variables.

This is what pass by value means.


On the other hand, pass by reference affects variables whose values are js objects (Object, Function, Array). 

If I say:

```
let arr = [1, 2, 3]
```

There will be an array created in memory. Then, when I say:
```
let c = arr
```

What `c` is pointing to is the spot in memory where that array is stored. This is what pass by reference means. Now, since both variables are pointing to the same spot in memory, if I alter `arr` by doing something like:
```
arr.push(4)
```
and I console.log both arrays:
```
console.log(arr, c)
```
My result will be `//--> [1, 2, 3, 4] [1, 2, 3, 4]`







---
layout: post
title:      "JavaScript Math"
date:       2020-07-02 00:24:04 +0000
permalink:  javascript_math
---


Disclaimer: This is only a basic explanation

In JavaScript, if you want to do mathematical operations, it's important to make sure that the values you want to use are actual numbers. 

If we say `'hello ' + 'world'` what we are doing is joining these two strings into one where the result would be `'hello world'`. Similarly, if we say `3 + '3'`, the result is `'33'`. So instead of getting the number 6, what JavaScript does, is convert the first number into a string, and then concatenate the two strings. 

Now that we know why it's important to make sure that the values are actual numbers let's look at some other operators inside of simple functions to see how they work.

**Addition ** 
```
function add(a, b) {
    return a + b 
}
```
 Function call:
```
add(2, 2) // => 4
```

**Subtraction **
```
function subtract(a, b) {
    return a - b 
}
```
Function call:
```
subtract(4, 2) //=> 2
```

**Multiplication **
```
function multiply(a, b) {
    return a * b 
}
```
Function call:
```
multiply(4, 2) //=> 8
```

**Division **
```
function divide(a, b) {
    return a / b 
}
```
Function call:
```
divide(4, 2) //=> 2
```

**Remainder **
```
function modulo(a, b) {
    return a % b 
}
```
Function call:
```
modulo(4, 2) //=> 0
```

**Exponent **
```
function exponent(a, b) {
    return a ** b 
}
```
Function call:
```
exponent(4, 2) //=> 16
```





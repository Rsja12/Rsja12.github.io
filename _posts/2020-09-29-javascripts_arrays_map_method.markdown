---
layout: post
title:      "JavaScript's Array's .map() Method"
date:       2020-09-29 15:47:31 +0000
permalink:  javascripts_arrays_map_method
---


This is a very commonly used method when working with arrays. The MDN web docs describe the `.map()` method as:

> a method that creates a new array populated with the results of calling a provided a provided function on every element in the calling array.

So what does this mean and how does it work? This method has a few parameters; a callback function, the current element in the array, and optionally, the index of the current element, the array that called the .map method, and `thisArg`, which is a value that refers to `this` in the callback. Let's not worry about the optional parameters for the moment. Using the .map method could look like this:

```
const numbers = [1, 2, 3, 4, 5]

numbers.map(function(currentNumber) {
  ...do something with currentNumber...
})
```

The return value will be a NEW array where the elements are whatever we decide to do to each `currentNumber`. We can use arrow syntax and make the code above look a little cleaner:

```
numbers.map((currentNumber) => {
  ...do something with currentNumber...
})
```

And since there's only one parameter in the callback function we can remove the parenthesis. So now our code looks like this:

```
numbers.map(currentNumber => {
  ...do something with currentNumber...
})
```

If we're using the .map method, it's because we want to capture the return value. Let's say we needed an array where each element was double each number in the `numbers` array. To capture that new array we can create a variable that holds the return value from calling the .map method. 

```
const doubleNumbers = numbers.map(currentNumber => {
  return currentNumber * 2
})
```

Now, if we `console.log(doubleNumbers)` we get `//  [2, 4, 6, 8, 10]`, but we haven't changed our original `numbers` array. 
`console.log(numbers) // [1, 2, 3, 4, 5]`

This allows us to create separate values without mutating our original data, so if we needed to, we could easily create a `const tripleNumbers` where we map over the `numbers` array, and instead of multiplying each value by 2 we instead multiply each value by 3!

---
layout: post
title:      "JavaScript's .forEach() method"
date:       2020-10-05 14:02:30 +0000
permalink:  javascripts_foreach_method
---


Last week I wrote about the .map() method and how it worked. One of the things that confused me a little when I was starting to learn JavaScript, was when to use .map vs .forEach. All I understood at that point that we were visiting each element with either method. One key distinction between .forEach and .map, is that .forEach does not make a copy of the array. 

The definition given by MDN is:

> forEach() calls a provided callback function once for each element in an array in ascending order. It is not invoked for index properties that have been deleted or are uninitialized.
>

The .forEach method takes in a callback that accepts anywhere from one to three items. The only mandatory parameter that has to be passed is the currentElement. Additionally, you can also pass in the index of the currentElement, the array you're iterating over, and `thisArg`, which is the value that refers to `this` when the callback is being executed.

The .forEach method can be thought of as a very general way of iterating through an array. Unlike the .map method, we're not creating a copy. If we try to implement the same functionality that we did last week, but instead we used .forEach, our return value will be `undefined`.

```
const numbers = [1, 2, 3, 4, 5]

const doubleNumbers = numbers.forEach(currentNumber => currentNumber * 2)

console.log(doubleNumbers) // undefined
```

Unlike .map, the value of doubleNumbers will be undefined, whereas if we had used .map, the value of doubleNumbers would have been an array where every number would have been multiplied by two and our original numbers array would have stayed intact. 

.forEach can be useful when we don't need to create a copy of the array so that we can operate on it. Instead, maybe all we want to do is take each value and use it for something. We might need to iterate over an array and pass each of its values to another function somewhere in our code:

```
numbers.forEach(number => {
  funcThatNeedsANumToDoSomethingUseful(number)
})
```

Maybe the numbers of your array each represent a song id and you want to fetch a list of songs. 












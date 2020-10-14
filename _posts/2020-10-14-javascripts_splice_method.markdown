---
layout: post
title:      "JavaScript's .splice() method"
date:       2020-10-14 15:17:47 +0000
permalink:  javascripts_splice_method
---


The splice method is an incredibly useful tool that every JavaScript developer should be familiar with. 
Here's the official definition according to MDN:

> The `.splice()` method changes the contents of an array by removing or replacing existing elements and/or adding new elements in place.
> 

It's important to keep in mind that since this method removes or replaces elements *in place*, the original data the method is called on, is destructively updated. 

You must provide at least one parameter to the method which will be the index where you want to begin the change. The second parameter is optional, and its purpose is to let you specify how many elements you want to remove. Any parameters after those two are optional and adding these parameters will add the arguments to the structure you're working with.

Here's an example. Let's say we have an array of odd numbers:

```
const numbers = [1, 3, 5, 7]
```

Let's also say that for whatever reason, we need to insert the number 2 into `numbers` so that it is changed to:

```
numbers = [1, 2, 3, 5, 7]
```

Splice let's us easily perform that insertion:

```
numbers.splice(1, 0, 2)

numbers // --> [1, 2, 3, 5, 7]
```

What we're saying in the code above is, on the `numbers` array, at index 1 (value of first argument), remove 0 elements (value of second argument), and insert 2 (value of third argument).

It's important to understand what the return value of the splice method is because it depends on how you implement it. Here's how it works. If we don't remove any elements in our implementation of `.slice()`, the return value is actually an empty array. So if we were to say `const sliceReturnValue = numbers.splice(1, 0, 2)`, the value that `sliceReturnValue` holds is actually an empty array. 

If we only remove one element using the splice method, then our return value is an array containing one element and the element will be the element at whatever position we specify in our first argument to splice. For example: 
`const oneElement = numbers.splice(1, 1)`, the value of oneElement is `[2]`. 

Lastly, if we remove more than one element, then the return value will be an array containing all of the elements that we removed. 












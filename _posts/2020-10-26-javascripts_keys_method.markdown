---
layout: post
title:      "JavaScript's .keys() method"
date:       2020-10-26 13:05:25 +0000
permalink:  javascripts_keys_method
---


A method that I find handy when working with objects is the `.keys()` method. Here's the MDN definition:

> Object.keys() returns an array whose elements are strings corresponding to the enumerable properties found directly upon object. The ordering of the properties is the same as that given by looping over the properties of the object manually
> 

I find this method to be extremely useful and very easy to implement. Although you can call this method on arrays, I've used it mostly on objects. Basically, all you have to do is call `Object.keys()` and pass in the object you want to iterate over.  Then, the return value is an array consisting of the keys of the object. One thing that's important to keep in mind is that the elements in your returned array will be strings weather that was their data type in the object or not. Here's what a simple implementation might look like:

```
let randomObject = {
  1: 'Hello',
  2: 'World',
  3: '!'
}

let arrayOfRandomObjectKeys = Object.keys(randomObject)
```

If we look at the value of `arrayOfRandomObjectKeys`, we see that we get `['1', '2', '3']`. Even though the keys in `randomObject` are integers, the array that gets returned has those numbers as values, but they are now strings. Also, as the definition states, the order of the elements in our new array corresponds to the order of the keys in the object. If instead our object looked like this:

```
let randomObject = {
  b: 'Hello',
  a: 'World',
  c: '!'
}
```

And we performed the same operation:

```
let arrayOfRandomObjectKeys = Object.keys(randomObject)
```

Our new array would be `['b', 'a', 'c']`

However, something interesting happens if we keep our keys as numbers:

```
let randomObject = {
  2: 'Hello',
  1: 'World',
  3: '!'
}
```

When we do `Object.keys(randomObject)` what we get is actually `['1', '2', '3']`. Since our keys are integers, JS sorts the numbers in ascending order. Something similar happens if our keys are strings that can be converted to integers:

```
let randomObject = {
  2: 'Hello',
  '1': 'World',
  3: '!'
}
```

What `Object.keys(randomObject)` returns is is still `['1', '2', '3']`


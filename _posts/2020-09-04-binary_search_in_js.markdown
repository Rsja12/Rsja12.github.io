---
layout: post
title:      "Binary Search in JS"
date:       2020-09-04 13:20:35 -0400
permalink:  binary_search_in_js
---


Over the past few days I've been trying to learn more about different algorithms, and when one type of algorithm might be a better choice than another one. Depending on the problem you're trying to solve, implementing binary search might be a great choice if you're looking for a certain element in a **sorted** array. It is imperative that the data is sorted in some way, otherwise this algorithm won't work.

Let's say we have the following inputs,

```
const numbers = [1, 2, 3, 4, 5, 6, 10, 15, 17, 25, 27, 35]
let itemToFind = 5
```

and we have to figure out if `itemToFind` is present in numbers, and if it is, return its index in the array. 

We could search the array in a linear fashion, meaning we iterate through the array starting at index 0, and at every iteration check if `numbers[i] === itemToFind`, and if it is, return `i`. In code that would look something like this:

```
function searchNumbers(arr, n) {
  for (let i = 0; i < arr.length; i++) {
	  if (arr[i] === n) return i;
	}
	
	return "item not found"
}

searchNumbers(numbers, itemToFind) //--> 4
```

This works well and solves the problem, but we could take advantage of the fact that we are searching an array that's already sorted for us, and optimize our code so that it runs faster! 

Implementing a binary search allows us to basically cut the size of the data in half at each iteration. To start, we need where our "search area" starts, and where it ends.

```
function searchNumbersFaster(arr, n) {
  let startIndex = 0;
  let endIndex = arr.length - 1;
	
	...
```
 So now on our first iteration our "search area" is the entire array, and we can add more logic to our function:
 
```
function searchNumbersFaster(arr, n) {

  let startIndex = 0;
  let endIndex = arr.length - 1;

  while (startIndex <= endIndex) {
	
	let midIndex = Math.floor((startIndex + endIndex) / 2)
	
	if (arr[midIndex] === n) {
	  return midIndex
	} else if (arr[midIndex] < n) {
	  startIndex = midIndex + 1
	} else {
	  endIndex = midIndex - 1
	}
	
  }
  return "item not found"
}
```

Now our function can find the answer a lot faster, because at each iteration we're cutting down the "search area" by half!





---
layout: post
title:      "Selection Sort"
date:       2020-09-18 23:18:23 +0000
permalink:  selection_sort
---


I was recently telling a more experienced developer about how I was trying to learn and understand data structures and algorithms better, and one of his suggestions was to start learning about sorting algorithms and how those work. 

In this post I'm going to be walking through selection sort and how I learned it. Selection sort is not the most optimized way of sorting data, but it was relatively easy to understand the logic and what was happening at each step. I'm going to implement selection sort to sort the data from smallest to largest.

Let's say for example we have an unsorted array of numbers:

```
const numbers = [3, 5, 4, 8, 2, 9, 6, 1, 7]
```

and we want our output to be:

```
[1, 2, 3, 4, 5, 6, 7, 8, 9] // --> same array, but sorted from smallest to largest
```

This is an in-place algorithm meaning we'll be destroying our original data. Basically, what we want to do is go through our unsorted array and find the index of the minimum value. In our example above that would be index 7 because the minimum value in the array is 1. We can write the first part of our function to do this:

```
function sortNumbers(arr) {
  let currentLowest;
  for (let i = 0; i < arr.length; i++) {
	  currentLowest = i;
		...
```

So we declare a variable `currentLowest`. This is the variable that's going to keep track of the index of the minimum value. Then we begin iterating over our array starting at position 0. Inside this loop, we assign `i` as the value of `currentLowest` because on our first iteration we've only seen the first value so that is our current lowest value. 

The next thing we want to do is a nested loop so that we can compare the next value in our array with `arr[currentLowest]`. What we're checking for, is if the next value in the array is less than `arr[currentLowest]`. If it is, we want to update the value of lowest to be the index of the next value:

```
function sortNumbers(arr) {
  let currentLowest;
  for (let i = 0; i < arr.length; i++) {
	  currentLowest = i;
		
		for (let j = i+1; j < arr.length; j++) {
		  if (arr[j] < arr[currentLowest]) {
			  currentLowest = j;
		}
```

At this point, our function is iterating through our array and `i` is counting those iterations. In our nested loop we declare a variable `j` that's equal to one number greater than whatever `i` is. So on our second outer loop - `i` will be equal to 1 and `j` will be equal to 2. Inside our nested loop we have our check to update `currentLowest` accordingly. `j` will iterate up through the rest of our array and our check will only evaluate to true once `arr[j] = 2` and then again when `arr[j] = 1`. 

Now we can add our final check:

```
function sortNumbers(arr) {
  let currentLowest;
  for (let i = 0; i < arr.length; i++) {
    currentLowest = i;

    for (let j = i+1; j < arr.length; j++) {
      if (arr[j] < arr[currentLowest]) {
          currentLowest = j;
      }
    }

    if (i != currentLowest) {
      let temp = arr[i]
      arr[i] = arr[currentLowest]
      arr[currentLowest] = temp
    }
  }
  return arr
}
```



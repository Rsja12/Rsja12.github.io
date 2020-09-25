---
layout: post
title:      "Bubble Sort"
date:       2020-09-25 17:23:06 +0000
permalink:  bubble_sort
---


Last week's blog was about Selection sort, and I thought this week I'd talk about another sorting algorithm I learned about called Bubble sort. 

I'm going to be using the same sample input for this example:

```
const numbers = [3, 5, 4, 8, 2, 9, 6, 1, 7]
```

We want our final array to look like this:

```
const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9]
```

On a high level, the way this algorithm works, is by going through each element and comparing it to the next element in the array. If the value of the current element is greater than the value of the next element in the array, then we swap those two elements. This process is repeated until the largerst element is in the last position of the array. Then, we start iterating again and comparing elements up until the index before the last element we correctly sorted.

The first thing we have to do is begin iterating through our array backwards:

```
function bubbleSortAlgo(arr) {
  for (let i = arr.length; i > 0; i--) {
	  ...
  }
}
```

Our function takes an array as a parameter and we begin by iterating through that array backwards. Then we're going to have a nested loop that iterates over our array starting at index 0 and ending at `i - 1`. We only have to iterate until `i - 1` because after each iteration of the outer loop, we know that the element at position `i` is correctly sorted. So that inner loop looks like this:

```
function bubbleSortAlgo(arr) {
  for (let i = arr.length; i > 0; i--) {
	  for (let j = 0; j < i - 1; j++) {
		  ...
	  }
  }
}
```

Now our function is iterating correctly both ways through our array. This is what allows us to compare the correct elements. All we have left to do is compare the current element ( `arr[j]` ) with the next element in the array ( `arr[j + 1]` ), and check if the current element is greater than the next element in the array. If that expression evaluates as true, we swap those elements in the array:

```
function bubbleSortAlgo(arr) {
  for (let i = arr.length; i > 0; i--) {
	  for (let j = 0; j < i - 1; j++) {
		  if (arr[j] > arr[j + 1]) {
			let temp = arr[j]
			arr[j] = arr[j + 1]
			arr[j + 1] = temp
	      }
	  }
  }
	
	return arr
}
```

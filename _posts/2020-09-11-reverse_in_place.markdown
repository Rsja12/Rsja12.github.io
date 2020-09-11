---
layout: post
title:      "Reverse In Place"
date:       2020-09-11 13:19:17 +0000
permalink:  reverse_in_place
---


I recently had a coding challenge question that when I first glanced at it, I thought I knew how to implement it immediately. What I read when I quickly glanced at it was: Write a function that takes an array of characters and returns them in reverse order. We couldn't use the .reverse() method because that would be too easy. What I immediately started to do was to create a new empty array, iterate through my input array backwards, and at each iteration push the current element into the new array. Finally, return the new array. However, that wasn't what the problem was asking for at all. In my solution I had created a new array and that was what I returned, but what the question really wanted, was to have us return the same array with the characters in reverse order. This small detail completely changes the implementation.

To reverse an array of characters in place, my approach was the following:

```
function reverseInPlace(arr) {
    let left = 0
	let right = arr.length - 1
}
```

What I did here was declare two variables that act as pointers to two positions in my array. I would use `left` to keep track of the current element starting from the beginning of the array, and `right` to keep track of the current element starting at the end of the array.

Now that I have these two pointers I can add in the logic to start reversing the characters:

```
function reverseInPlace(arr) {
    let left = 0
	let right = arr.length - 1
	
	let currentElement
	while (left < right) {
	    currentElement = arr[left]
			
		arr[left] = arr[right]
		arr[right] = currentElement
		
		left++
		right--
	}
	
	return arr
}
```

This is one way to solve the problem. I defined a variable `currentElement` which was going to hold the current value of `arr[left]` before I started swapping elements. Then, I swapped my left value with my right value, which in the first iteration would be `arr[0]` and `arr[arr.length - 1]`. The last swap is the value at `arr[right]` and the value at `currentElement`, which was the value of `arr[left]` BEFORE we swapped it. Finally I moved my left pointer up one element in the array, and my right pointer down one element in the array to repeat the process.

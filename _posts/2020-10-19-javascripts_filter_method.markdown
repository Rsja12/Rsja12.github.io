---
layout: post
title:      "JavaScript's .filter() method"
date:       2020-10-19 13:01:01 +0000
permalink:  javascripts_filter_method
---


This week I thought I'd talk about another method that I use very often in my projects, and that's the `.filter()` method. Here's the official definition according to MDN:

> The `.filter()` method creates a new array with all elements that pass the test implemented by the provided function.
> 

It's important to note that this method does not destroy the original data we're working with. The required parameter for this method is the currentElement that we're working with, and additionally, we can pass in three optional parameters: `index` which is the index of the current element being processed in the array, `array`, which is simply the same array that we originally called `.filter()` on, and `thisArg`, which is an argument that we can use in the callback function's body to refer to `this`.

We can use this method any time we want to filter our data according to a specific condition. Here's a simple example:

```
const numbers = [1, 2, 3, 4, 5]

const numbersGreaterThanOrEqualTo3 = numbers.filter(num => num >= 3)

numbersGreaterThanOrEqualTo3 // --> [3, 4, 5]
```

I find myself using this method a lot when working with React and Redux. Let's say we have an app that let's users keep a list of movies they've watched. If our user really loves movies, and they watch a lot of them, their list of movies can get quite long fairly quickly. To improve the user's experience, we could build in a feature that allows them to mark their favorite movies. To do this, we can add a simple star icon to each movie item in our UI that keeps track of the state of each movie. The state can be either marked as favorite or not. In our state object, that might look like this:

```
state = {
  isFavorite: false
}
```

We can attach an onClick handler to our star icon so that each time the user clicks on the icon we call `setState` to update our `isFavorite` property. Now that we're keeping track of which movies the user marks as their favorites, we can use the `.filter()` method to update our UI, and give the user the ability to only see their favorite movies. We can do this by adding a button (or other element), at the top of our list of movies. To this element, we attach a listener so that when the user interacts with the button, we fire off an action called `ONLY_FAVORITES`. This action takes in our current state and passes it along to our reducers. Then, our reducers checks the `action.type`, and in our `ONLY_FAVORITES` case, we use the filter method by iterating through all of our movies, and checking if the current movie's `isFavorite` property is set to true. That check might look something like this: 

```
return movies.filter( movie => movie.isFavorite)
```

All this does is iterate through our `movies` collection and return a new collection containing only the movies that the user marked as favorite. This will update our state and render only the user's favorite movies!



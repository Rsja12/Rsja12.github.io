---
layout: post
title:      "What Is A Callback Function in JS"
date:       2020-08-28 23:55:40 +0000
permalink:  what_is_a_callback_function_in_js
---


The MDN web docs define a callback function as 

> a function passed into another function as an argument, which is then invoked inside the outer function to complete some kind of routine or action.
> 

So what does that mean exactly? Simply that we're waiting for some action to happen before our callback function gets called. 

Let's say we have a button with an event listener:
```
const button = document.createElement('BUTTON')

button.addEventListener()
```

In this case, we have a button and we attached the addEventListener method to it. The addEventListener method can take three parameters which are the `event`, `function`, and `useCapture`. The `event` is the type of event that we're listening for. There are many `events` that the DOM can handle. I recommend searching for the full list to get an idea. The next parameter is `function`. This is our callback function that we want to call when the `event` that we passed in actually happens. We can pass in the function of our choosing here so that we can control what will happen when a user interacts with our button in the way we specified. The last parameter is an optional boolean value that controls when the event should be executed. 

A simple example of using a callback function when the user interacts with our button could be the following:

```
button.addEventListener('click', function(){
  alert('You clicked the button')
})
```

And that's it! When the user clicks the button (since that's the type of event we passed in), the function will get called, and the user will get the alert


---
layout: post
title:      "How To Use useState"
date:       2020-07-28 00:44:43 +0000
permalink:  how_to_use_usestate
---


I've been curious about React Hooks for a while now so I decided to go through the docs to try to understand what they were all about. If you haven't yet, I highly recommend going through the React documentation. They did a great job presenting the information in a way that is easy for anyone to understand. There are different hooks that allow you to do different things. Today, I'm just going over the useState hook.

The useState hook allows you to, like its name implies, use state. However, now we don't have to write a class component. Previously we would do something like:

```
import React, { Component } from 'react'

class App extends Component {

  state = {
    likes: 0
  }
	
  render() {
    return (
		<div>
		<button onClick={() => this.setState({ likes: this.state.likes + 1 })}>Like</button>
      <div>{ this.state.likes }</div>
		</div>
    )
  }
}

export default App
```

This component, when rendered, would display a button and the number 0 at first. After each time the user clicks the button, the state would be updated and the number on the screen would increment by one.

With the useState hook we can do all of this in a functional component. 

First, we import the useState hook from React:
```
import React, { useState } from 'react'
```

Then, we can write our functional component.
```
import React, { useState } from 'react'

export default const App = () => {
  
  const [likes, setLikes] = useState(0)
	
	return (
	 <div>
	     <button onClick={() => setLikes(likes + 1)}>Like</button>
       <div>{ likes }</div>
	</div>
	)
	
}
```

All we are doing is using array destructuring to create two variables from useState; likes and setLikes. Then, what we pass to our useState function is our initial state. In this case we want to start at 0 so that's what I passed, but I could've just as easily passed 100 to start from 100. We can also pass in an object if that's what we want the initial state to be. In the example above we have a variable `likes` that stores our number of likes, and `setLikes` is our function that updates our number, so every time the user clicks on that button, `setLikes` gets called and the value in `likes` gets updated. Simple as that!


---
layout: post
title:      "What are props?"
date:       2020-02-28 00:11:52 +0000
permalink:  what_are_props
---


Props are kind of like attributes that can be passed down to child components in React. They can be passed down like this: 

```
const App = () => {
    return (
        <div>
            <Greeting greet="Hello World" />
        </div>
    )
}
```

In this example, our Greeting component will have `greet` props whose value is "Hello World".
Our greeting can now use those props this way:

```
const Greeting = (props) => {
    return (
        <div>
            {props.greet}
        </div>
    )
}
```

The Greeting component takes in props (which stands for properties) as an argument. Now, this prop and whatever other props are passed down from a parent component can be used inside of this component. 

Props are read-only, which means they are immutable. So if you try to do :

```
const Greeting = (props) => {
    return (
        <div>
            {props.greet = 'Hi'}
        </div>
    )
}
```

You will get an error page. 



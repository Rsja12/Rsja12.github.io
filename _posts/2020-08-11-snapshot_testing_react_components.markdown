---
layout: post
title:      "Snapshot Testing React Components"
date:       2020-08-12 00:57:57 +0000
permalink:  snapshot_testing_react_components
---


I don't know why, but, until very recently, I dreaded the idea of having to write tests for my code. It was something I kept telling myself that I would learn how to do later on. Over the last few days I decided to look into how I could add some tests to one of my apps built with React, and so far, I've been pleasently surprised with how simple it's been. 

This post is only about a specific type of test that you can implement quickly and easily on React components. Jest comes included with create-react-app so there's not much to do as far as setup goes. If you haven't already, I highly recommend checking out the Jest docs on testing [here](https://create-react-app.dev/docs/running-tests/). They're very easy to understand and follow along with. To test components in isolation, and not worry about the behavior of child components we can install enzyme to use the shallow() function. 

Setting up enzyme is very easy. All you have to do is open your terminal and cd into your project. Once there run:
```
npm i --save-dev enzyme enzyme-adapter-react-16
```

Then, in your src directory, create a file called setupTests.js and paste in:
```
import Enzyme from 'enzyme';
import Adapter from 'enzyme-adapter-react-16';

Enzyme.configure({ adapter: new Adapter() });
```
That's it! That's all of the set up that's needed.

Now we can start writing tests using Jest and enzyme. If we wanted to test our <App /> component we could create a file called App.test.js. That file could look like this:

```
import React from 'react';
import { shallow } from 'enzyme;

import App from './App';

it ('renders without crashing', () => {
  expect(shallow(<App />)).toMatchSnapshot();
})


```

So basically what we're doing is creating a test called `renders without crashing`. We can name the test whatever we want but it's good to have names that describe the functionality we're testing. On the next line, we call Jest's expect method. This method takes in a value of what we want to test. In our case above, what we're testing is a shallow copy of our <App /> component. The `.toMatchSnapshot()` method is a matcher. When we run our test, which we can do by running `npm test` in terminal, this method creates a snapshot file. This file is what the test runner uses to compare the component in subsequent renders. The test fails if our <App /> component were to render something different than what the snapshot file holds. 

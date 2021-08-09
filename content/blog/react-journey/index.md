---
title: React in a nutshell
date: "2021-08-04T22:12:03.284Z"
description: "A guide for beginners on how to learn reactjs."
---

Hello👋 Everyone,

This blog is about getting started with ReactJS which is indeed a very popular library for creating UI. React is developed by Jordan Walke ex-employee of Facebook company. React allows developers to create large applications which can change the data without reloading the webpage. It is fast, scalable and simple. It's a view library and can be integrated with different applications as Angular.

I started learning React last year and faced lot of difficulties. TBH, coming from a Testing background I faced so many challenges while learning development but now I love it. I've really come very far from where I began. So without wasting any more minute I'll start with how anyone should get started learning React.

## JSX (JavaScript XML)

Anyone who wants to learn React should be familiar with HTML as they would be spending more time creating layouts. React uses JSX which is similar to HTML but JSX is a mixture of HTML and JavaScript which forms a component. JSX gets translated into JavaScript at runtime with the help of Babel.

```
// Normal HTML
<div>
    <p>This is a React Blog</p>
</div>

// JSX
<>
    <Hello />
    <p>This is a React Blog</p>
</>
```

**Hello** is a component, it would've been made you confused that when this type of HTML element have been created but trust me that's not the case here. This is a React Component which needs to be imported in **_App.js_** file to be rendered on UI. **<></>** is a React Fragment which is used to wrap the components when we don't require an extra node in DOM tree. You can search more on this later.

After getting transpiled with the help of Babel, JSX gets converted as-

```
// JSX code
<h1>This is a React Blog</h1>

// Transpiled code into JS
React.createElement('h1', {}, 'This is a React Blog');
```

FYI, we can write the JavaScript code directly in our file rather than writing JSX but that would take enormous amount of time, that's why JSX code is there for our facility. So, use that kindly 👨‍💻.

## Hooks vs Class Component

I would recommend everyone to learn Hooks instead of Class Component as Facebook says😜.
But IMO, Hooks has made React easier to learn. When I started learning React I learned class component first and got messed up while learning so many lifecycle methods and few got deprecated till I finished and then I started learning Hooks. Hooks is just as amazing, you can get your work done just with **useEffect** in the place of _componentDidMount()_, _componentDidUpdate()_, _componentWillUnmount()_ methods. **useState** hook can be used for mutating state. No need of using **this** keyword every time while mutating state or calling any functions unlike **class components**.
Example-

```javascript
// Hooks
import React, { useState, useEffect } from "react"

function Example() {
  const [count, setCount] = useState(0)

  // Similar to componentDidMount and componentDidUpdate:
  useEffect(() => {
    // Update the document title using the browser API
    document.title = `You clicked ${count} times`
  })

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>Click me</button>
    </div>
  )
}

// Class Component
class Example extends React.Component {
  constructor(props) {
    super(props)
    this.state = {
      count: 0,
    }
  }

  componentDidMount() {
    document.title = `You clicked ${this.state.count} times`
  }
  componentDidUpdate() {
    document.title = `You clicked ${this.state.count} times`
  }

  render() {
    return (
      <div>
        <p>You clicked {this.state.count} times</p>
        <button onClick={() => this.setState({ count: this.state.count + 1 })}>
          Click me
        </button>
      </div>
    )
  }
}
```

## JavaScript

Not to mention, without knowing JavaScript learning React would be a very bad idea as React is based on JavaScript only. One has to use the same way of variable declaration and method writing. But as this is a library, certain rules needs to be followed, Camel notation is used everywhere in React when calling event listener. E.g. **_onclick_** is used in vanilla JS but in React the same event would be called as **_onClick_**. Other examples are onChange, onDrag, onDrop etc.
For more info related to React events you can visit [here](https://reactjs.org/docs/events.html)

## State and Props

**State** plays a very vital role in UI development. In React also it's used to handle the behavior of UI. In fact, whenever any state change happens, react only updates the changed attributes rather than rebuilding the new DOM tree which increases the efficiency. This process is called **Reconciliation**.

**Props** is an object which stores the value of attributes of a tag and work similar to the HTML attributes. It gives a way to pass data from one component to other components. It is similar to function arguments. Props are passed to the component in the same way as arguments passed in a function.

Eg.

```javascript
// Parent Component
import React, { useState, useEffect } from 'react';
import Child from './child';

function Parent() {
  const [count, setCount] = useState(0);

  useEffect(() => {
    document.title = `You clicked ${count} times`;
  });

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
      <Child counter={count} />
    </div>
  );
}

// Child Component
import React from 'react';

export default const Child = (props) => {

  return (
  <>
    <p>{props.counter}</p>
  </>
  )
}
```

You can see in the code, **Parent** component has state called count which mutates when **_Click Me_** button gets clicked. And the **Child** component is imported inside the **Parent** component, **<Child />** has the counter value which is accessible in **Child** component via _props_.

## CSS Modules

CSS Modules let you use the same CSS class name in different files without worrying about naming clashes. Normally, CSS is imported as

```
import './style.css';

<Button className="main-btn"></Button>
```

but when using CSS modules then

```
import styles from './style.module.css';

<Button className={styles.mainBtn}></Button>
```

## SPA

SPA stands for **Single Page Application**. You do know how our mobile application is fast, on a single click it navigates to different pages. The same way Web application also works nowadays and React is one of the widely used library to create SPA.

## Libraries and Framework support

Several libraries and frameworks are out there which can be easily integrated into React application. Few like **_React Router, Redux, MaterialUI_** you should learn. It'll make your life easier.

### 1. React Router

_React is well known for its declarative programming model. If you are creating an application with React, it will be great to have some components that you can compose declaratively in your app. React router is a collection of such components. Suppose you want to add some URLs which you can bookmark. Or, what if you want a composable way to navigate in React native? We have a React Router for the solution._

_React Router is one of the best component libraries that makes it effortless for the developer to handle navigation in a single-page app. Not only that, but the library also offers smooth screen-to-screen transition, server-side rendering and vivid support for nesting._

### 2. Redux

_When it comes to state management libraries, the one that comes to our mind is Redux. Redux also comes under the category of best component libraries with 20.9k GitHub stars and 3k forks. Although it is meant to be used with the library components of React UI, you can also use it with Vue, Angular, Ember, and other JS frameworks._

_Redux helps to connect React components to pieces of state by decreasing the need for props or callbacks. The library is often termed as a developer’s best friend. It helps you to write consistent codes and is environment-friendly. You can also edit the code while your app is live._

### 3. Material UI

_If you are not much of a designer, no issues. Material UI gives you a collection of themes that you can choose for your site. There is extensive documentation so that you can find whatever you need whenever you feel stuck._

When you're done learning these things, get ready to dirty your hands with **Creating Custom Hooks, Unit Testing, Server Side Rendering using NextJS, etc.** which will help you to evolve as a great developer.

Last but not least, by learning React you can develop Web Applications, Mobile Applications and Desktop Applications as well. There are hell lot of demand for React developers. So, start learning it today.

So that was it from this article😇.

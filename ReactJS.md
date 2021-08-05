# React JS Interview Questions

## What is React?
React is an open-source frontend JavaScript library which is used for building user interfaces especially for single page applications. It is used for handling view layer for web and mobile apps. React was created by Jordan Walke, a software engineer working for Facebook. React was first deployed on Facebook's News Feed in 2011 and on Instagram in 2012.

## Advantages of React?
The major features of React are:
- It uses **VirtualDOM** instead of RealDOM considering that RealDOM manipulations are expensive.
- Supports **server-side rendering**.
- Follows **Unidirectional** data flow or data binding.
- Uses **reusable/composable** UI components to develop the view.

## Disadvantages of React?
- JSX syntax.
- Fast development pace.
- Somewhat slow documentation.

## What is JSX?
*JSX* is a XML-like syntax extension to ECMAScript (the acronym stands for *JavaScript XML*). Basically it just provides syntactic sugar for the `React.createElement()` function, giving us expressiveness of JavaScript along with HTML like template syntax.

In the example below text inside `<h1>` tag is returned as JavaScript function to the render function.

```jsx
class App extends React.Component {
  render() {
    return(
      <div>
        <h1>{'Welcome to React world!'}</h1>
      </div>
    )
  }
}
```

## How to pass data between components?
- Use props to pass data from parent to child.
- Use callbacks to pass data from child to parent.
- Use any of the following methods to pass data among siblings: 
  - Integrating the methods mentioned above.
  - Using Redux.
  - Utilizing React’s Context API.

## Virtual DOM
The Virtual DOM (VDOM) is a lightweight JavaScript object and it contains a copy of the real DOM.
<img width="691" alt="Screen Shot 2021-08-05 at 12 07 03 AM" src="https://user-images.githubusercontent.com/30380214/128224016-33513f3c-7f3c-42b0-8dc5-2ecf65990723.png">

## What is React Fiber
Fiber is the new reconciliation engine in React 16.

Its headline feature is incremental rendering: the ability to split rendering work into chunks and spread it out over multiple frames.

## How State differ from Props
Both props and state are plain JavaScript objects.

Props (short for “properties”) is an object of arbitrary inputs that are passed to a component by its parent component.

State are variables that are initialized and managed by the component and change over the lifetime of a specific instance of this component.

## Controlled component and Un-controlled component
The value of an input element in a controlled React component is controlled by React.

The value of an input element in an uncontrolled React component is controlled by the DOM.

## How can you improve your React app
- Use `React.PureComponent` which is a base class like `React.Component` but it provides in some cases a performance boost if its `render()` function renders the same result given the same props and state.
- Use `useMemo` Hook to memoize functions that perform expensive calculations on every render. It will only recompute the memoized value if one of the dependencies (that are passed to the Hook) has changed.
- State `colocation` is a process that moves the state as close to where you need it. Some React applications have a lot of unnecessary state in their parent component which makes the code harder to maintain and leads to a lot of unnecessary re-renders.
- Lazy load your components to reduce the load time of your application. `React Suspense` can be used to lazy load components.

## What are keys in React?
React needs `keys` to be able to identify which elements were changed, added, or removed. Each item in an array needs to have a key that provides a stable identity.

It’s not recommended to use indexes for keys if the order of items may change as it can have a negative impact on the performance and may cause state issues. React will use indexes as keys if you do not assign an explicit key to list items.

## What are error boundaries?
React 16 introduced a new concept of an “error boundary”.

Error boundaries are React components that catch JavaScript errors anywhere in their child component tree, log those errors, and display a fallback UI instead of the component tree that crashed. Error boundaries catch errors during rendering, in lifecycle methods, and in constructors of the whole tree below them.

## Pure component
`React.PureComponent` is similar to `React.Component`. The difference between them is that `React.Component` doesn’t implement `shouldComponentUpdate()`, but `React.PureComponent` implements it with a shallow prop and state comparison.

If your React component’s `render()` function renders the same result given the same props and state, you can use `React.PureComponent` for a performance boost in some cases.

## Higher Order Components
A higher-order component (HOC) is an advanced technique in React for reusing component logic. HOCs are not part of the React API, per se. They are a pattern that emerges from React’s compositional nature.
Concretely, a higher-order component is a function that takes a component and returns a new component.
```
const EnhancedComponent = higherOrderComponent(WrappedComponent);
```

Whereas a component transforms props into UI, a higher-order component transforms a component into another component.

HOCs are common in third-party React libraries, such as Redux’s `connect` and Relay’s` createFragmentContainer`.

## Why hooks were introduced
Hooks solve a wide variety of seemingly unconnected problems in React that were encountered by Facebook over five years of writing and maintaining tens of thousands of components:
- Hooks allow you to reuse stateful logic without changing your component hierarchy.
- Hooks let you split one component into smaller functions based on what pieces are related (such as setting up a subscription or fetching data).
- Hooks let you use more of React’s features without classes.
- It removed the complexity of dealing with the `this` keyword inside class components.

## React Refs
## Compare Redux and Context API
## Redux flow - diagram
## Flux and Redux
## Compare React Class component and React Functional component
Hooks were introduced in React 16.8. In previous versions, functional components were called stateless components and did not provide the same features as class components (e.g., accessing state). Hooks enable functional components to have the same features as class components. There are no plans to remove class components from React.
So let’s take a look at the differences:
### Declaration & Props
#### Functional Component
Functional components are JavaScript functions and therefore can be declared using an arrow function or the function keyword. Props are simply function arguments and can be directly used inside JSX:
```jsx
const Card = (props) => {
 return(
 	<h2>Title: {props.title}</h2>
 )
}

function Card(props){
 return(
	<h2>Title: {props.title}</h2>
 )
}
```
#### Class component
Class components are declared using the ES6 `class` keyword. Props need to be accessed using the `this` keyword:
```jsx
class Card extends React.Component{
 constructor(props){
   super(props);
 }

 render(){
   return(
	<h2>Title: {this.props.title}</h2>
   )
 }
}
```
### Handling state
#### Functional components
In functional components we need to use the `useState` hook to be able to handle state:
```jsx
const Counter = (props) => {
	const [counter, setCounter] = useState(0);
	
	const increment = () => {
		setCounter(++counter);
	}
	
	return (
		<div>
			<p>Count: {counter}</p>
			<button onClick={increment}>Increment Counter</button>
		</div>
	)
}
```
#### Class components
It’s not possible to use React Hooks inside class components, therefore state handling is done differently in a class component:
```jsx
class Counter extends React.Component {
	constructor(props){
    	super(props);
        this.state = {counter : 0};
        this.increment = this.increment.bind(this);
    }
	
	increment() {
		this.setState((prevState) => {
			return {counter: prevState.counter + 1};
		});
	}
	
	render() {
	return (
			<div>
			<p>Count: {this.state.counter}</p>
			<button onClick={this.increment}>Increment Counter</button>
		</div>
		)
	}
}
```
## Why hooks was introduced
First, to understand why hooks was introduced, we need to understand what is the problem before React hooks, especially is React Component.
#### constructor
With Class components, you initialize the state of the component inside of the `constructor` method as a `state` property on the instance (`this`). 
However, according to the ECMAScript spec, if you’re extending a subclass (in this case, `React.Component`), you must first invoke `super` before you can use `this`. Specifically, when using React, you also have to remember to pass props to `super`.
```jsx
  constructor (props) {
    super(props) // 🤮

    ...
  }
```
#### Autobinding
React developers everywhere realized they didn’t know how the `this` keyword worked. Instead of having method invocations that “just worked”, you had to remember to `.bind` methods in the class’s `constructor`. If you didn’t, you’d get the popular `“Cannot read property setState of undefined”` error.
```jsx
  constructor (props) {
    ...

    this.updateRepos = this.updateRepos.bind(this) // 😭
  }
```
#### Duplicate Logic
We need three separate methods (`componentDidMount`, `componentDidUpdate`, and `updateRepos`) to accomplish the same thing
```jsx
  componentDidMount () {
    this.updateRepos(this.props.id)
  }
  componentDidUpdate (prevProps) {
    if (prevProps.id !== this.props.id) {
      this.updateRepos(this.props.id)
    }
  }
  updateRepos = (id) => {
    this.setState({ loading: true })

    fetchRepos(id)
      .then((repos) => this.setState({
        repos,
        loading: false
      }))
  }
  ```
#### Sharing Non-visual Logic
In React work, not only we need to render views, but it's common to build a logic function only. But React doesn't support it.
So, in the old days, we handle this by implement HOCs or using Props drilling
So it can lead to HOCs hell - wrapper hell
```jsx
export default withHover(
  withTheme(
    withAuth(
      withRepos(Profile)
    )
  )
)
```
=> That is a few problems with React components => React hooks was introduced.

## Lifecycle in React
![Screen Shot 2021-08-05 at 12 59 53 PM](https://user-images.githubusercontent.com/30380214/128299098-7016b957-bb78-4a45-9d7e-39580f53d995.png)

## useEffect hook
The Effect Hook lets you perform side effects in function components:
```jsx
import React, { useState, useEffect } from 'react';

function Example() {
  const [count, setCount] = useState(0);

  // Similar to componentDidMount and componentDidUpdate:
  useEffect(() => {
    // Update the document title using the browser API
    document.title = `You clicked ${count} times`;
  });

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}
```
useEffect can perform cleaning up (componentWillMount) by return a function inside useEffect().
useEffect also receive an array of dependencies.

## useState hook
Help us able to use state inside functional component.

## useMemo hook
```jsx
const memoizedValue = useMemo(() => computeExpensiveValue(a, b), [a, b]);
```
Returns a memoized value.

Pass a “create” function and an array of dependencies. useMemo will only recompute the memoized value when one of the dependencies has changed. This optimization helps to avoid expensive calculations on every render.
**You may rely on useMemo as a performance optimization, not as a semantic guarantee.**

## useCallback hook
```jsx
const memoizedCallback = useCallback(
  () => {
    doSomething(a, b);
  },
  [a, b],
);
```
Returns a memoized callback.

Pass an inline callback and an array of dependencies. useCallback will return a memoized version of the callback that only changes if one of the dependencies has changed. This is useful when passing callbacks to optimized child components that rely on reference equality to prevent unnecessary renders (e.g. shouldComponentUpdate).

`useCallback(fn, deps)` is equivalent to `useMemo(() => fn, deps)`.

## useReducer hook
```jsx
const [state, dispatch] = useReducer(reducer, initialArg, init);
```
An alternative to `useState`. Accepts a reducer of type `(state, action) => newState`, and returns the current state paired with a dispatch method. (If you’re familiar with Redux, you already know how this works.)

## custom hook in FC
## Why and when Redux

## Middleware in Redux

## Redux flow
![image](https://redux.js.org/assets/images/ReduxDataFlowDiagram-49fa8c3968371d9ef6f2a1486bd40a26.gif)

## Direct mutate states/objects?
For objects, this objects can be using somewhere else, because object is passed down by reference. If somewhere else using it, it can lead to odd bugs, and hard to debug.

For state of React:
- NEVER mutate `this.state` directly, as calling `setState()` afterwards may replace the mutation you made. Treat `this.state` as if it were immutable.
- `setState()` does not immediately mutate `this.state` but creates a pending state transition. Accessing `this.state` after calling this method can potentially return the existing value.
- There is no guarantee of synchronous operation of calls to `setState` and calls may be batched for performance gains.
- `setState()` will always trigger a re-render unless conditional rendering logic is implemented in `shouldComponentUpdate()`. If mutable objects are being used and the logic cannot be implemented in `shouldComponentUpdate()`, calling `setState()` only when the new state differs from the previous state will avoid unnecessary re-renders.

## What are reducers in redux?
The reducer is a pure function that takes the previous state and an action, and returns the next state.
```jsx
(previousState, action) => newState
```
It's very important that the reducer stays pure. Things you should never do inside a reducer:
- Mutate its arguments;
- Perform side effects like API calls and routing transitions;
- Call non-pure functions, e.g. `Date.now()` or `Math.random()`

## How is state changed in redux?
The only way to change the state is to emit an action, an object describing what happened. This ensures that neither the views nor the network callbacks will ever write directly to the state. Instead, they express an intent to transform the state. Because all changes are centralized and happen one by one in a strict order, there are no subtle race conditions to watch out for. As actions are just plain objects, they can be logged, serialized, stored, and later replayed for debugging or testing purposes.

## What is Redux Thunk?
**Redux Thunk** middleware allows you to write action creators that return a function instead of an action. The thunk can be used to delay the dispatch of an action, or to dispatch only if a certain condition is met. The inner function receives the store methods `dispatch` and `getState()` as parameters.

## What is the difference between `mapStateToProps()` and `mapDispatchToProps()`?
`mapStateToProps()` is a utility which helps your component get updated state (which is updated by some other components):
```jsx
const mapStateToProps = (state) => {
  return {
    todos: getVisibleTodos(state.todos, state.visibilityFilter),
  };
};
```

`mapDispatchToProps()` is a utility which will help your component to fire an action event (dispatching action which may cause change of application state):
```jsx
const mapDispatchToProps = (dispatch) => {
  return {
    onTodoClick: (id) => {
      dispatch(toggleTodo(id));
    },
  };
};
```
Recommend always using the "object shorthand" form for the `mapDispatchToProps`

Redux wrap it in another function that looks like `(…args) => dispatch(onTodoClick(…args))`, and pass that wrapper function as a prop to your component.
```jsx
const mapDispatchToProps = {
  onTodoClick,
};
```

## How to add multiple middlewares to Redux?
You can use `applyMiddleware` where you can pass each piece of middleware as a new argument. So you just need to pass each piece of middleware you'd like. For example, you can add Redux Thunk and logger middlewares as an argument as below:
```jsx
import { createStore, applyMiddleware } from 'redux'
const createStoreWithMiddleware = applyMiddleware(ReduxThunk, logger)(createStore);
```

## What is React context vs React Redux?
You can use Context in your application directly and is going to be great for passing down data to deeply nested components which what it was designed for. Whereas Redux is much more powerful and provides a large number of features that the Context Api doesn't provide.

Also, React Redux uses context internally but it doesn’t expose this fact in the public API. So you should feel much safer using Context via React Redux than directly because if it changes, the burden of updating the code will be on React Redux instead developer responsibility.

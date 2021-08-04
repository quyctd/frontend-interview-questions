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

## Lifecycle in React
## useEffect hook
## useState hook
## useMemo hook
## useCallback hook
## useReducer hook
## custom hook in FC
## Why and when Redux
## Middleware in Redux
## Direct mutate states?

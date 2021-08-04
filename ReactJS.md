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
## What is React Fiber
## How State differ from Props
## Controlled component and Un-controlled component
## Pure component
## Higher Order Components
## Errors Boundaries
## Why hooks were introduced
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

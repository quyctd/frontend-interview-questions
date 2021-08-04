# React JS Interview Questions

### What is React?
React is an open-source frontend JavaScript library which is used for building user interfaces especially for single page applications. It is used for handling view layer for web and mobile apps. React was created by Jordan Walke, a software engineer working for Facebook. React was first deployed on Facebook's News Feed in 2011 and on Instagram in 2012.

### Advantages of React?
The major features of React are:
- It uses **VirtualDOM** instead of RealDOM considering that RealDOM manipulations are expensive.
- Supports **server-side rendering**.
- Follows **Unidirectional** data flow or data binding.
- Uses **reusable/composable** UI components to develop the view.

### Disadvantages of React?
### What is JSX?
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

### How to pass data between components?
### Virtual DOM
### What is React Fiber
### How State differ from Props
### Controlled component and Un-controlled component
### Pure component
### Higher Order Components
### Errors Boundaries
### Why hooks were introduced
### React Refs
### Compare Redux and Context API
### Redux flow - diagram
### Flux and Redux
### Compare React Class component and React Functional component
### Lifecycle in React
### useEffect hook
### useState hook
### useMemo hook
### useCallback hook
### useReducer hook
### custom hook in FC
### Why and when Redux
### Middleware in Redux
### Direct mutate states?

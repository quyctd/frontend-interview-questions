# Frontend Interview Questions

This is the list of questions I get asked over time when I applied to some companies. The list doesn't sort in anyways. I write it down randomly as I remember, or I come up with...
---
## Vanilla JS
1. ### What are JS Data types?
    - Number
    - Boolean
    - String
    - Object
    - Null
    - Undifined
    - Symbol
    - BigInt?
2. ### Hoisting in JS?
    Hoisting is a default behavior of JS where all the variable and function declarations are moved on top.
    ![image](https://user-images.githubusercontent.com/30380214/127508500-88d81b68-54ec-43ef-9426-b6552fbac6cd.png)
    Example:
    ```js
    hoistedVariable = 3;
    console.log(hoistedVariable); // outputs 3 even when the variable is declared after it is initialized	
    var hoistedVariable;
    ```
    
    ```js
    hoistedFunction();  // Outputs " Hello world! " even when the function is declared after calling

    function hoistedFunction(){ 
      console.log(" Hello world! ");
    }
    ```
    
    ```js
    var x;
    console.log(x); // Outputs "undefined" since the initialization of "x" is not hoisted
    x = 23;
    ```
 
3. ### Scope and the Scope chain
6. ### Temporal Dead Zone for Let and Const
7. ### The JS Engine and Runtime
8. ### Execution Contexts and The Call Stack
9. ### The `this` keyword
10. ### The Eventloop
11. ### Promise
12. ### Async/Await, compare with Promise
13. ### Currying function in JS
14. ### Implement Infinite Scroll using IntersectionObserver API 


---
## React JS
1. ### What is React?
2. ### Advantages of React?
3. ### Disadvantages of React?
4. ### What is JSX?
5. ### How to pass data between components?
6. ### Virtual DOM
7. ### What is React Fiber
8. ### How State differ from Props
9. ### Controlled component and Un-controlled component
10. ### Pure component
11. ### Higher Order Components
12. ### Errors Boundaries
13. ### Why hooks were introduced
14. ### React Refs
15. ### Compare Redux and Context API
16. ### Redux flow - diagram
17. ### Flux and Redux
18. ### Compare React Class component and React Functional component
19. ### Lifecycle in React
20. ### useEffect hook
21. ### useState hook
22. ### useMemo hook
23. ### useCallback hook
24. ### useReducer hook
25. ### custom hook in FC
26. ### Why and when Redux
27. ### Middleware in Redux
28. ### Direct mutate states?


---
## TypeScript
1. ### What Typescript
2. ### Why Typescript
3. ### Compare Interface with Type
4. ### Compare Unknown vs Any


---
## NextJS
1. ### Why Next.JS?


---
## General Knowlegde
1. ### Test Driven Development
2. ### Micro Frontend
3. ### List of design pattern in FE
4. ### Compare GraphQL vs Rest API
5. ### Testing: Jest & React Testing Library
6. ### Animation: GSAP, react-transition-group
7. ### RxJS - Observable
8. ### style - SaSS, SCSS


---
## Computer Sience
1. ### List of Data structure
2. ### Some sorting algorithm
3. ### List of Algorithms


---
## Behavior/Project Questions
1. ### Your role at last company
2. ### Why do you leave your last company
3. ### Why do you change from Back-end to Front-end
4. ### Tell me about your last project
5. ### Problem on your project - Image grid
6. ### Problem on your project - Speed optimization

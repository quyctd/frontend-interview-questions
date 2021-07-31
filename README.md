# Frontend Interview Questions

This is the list of questions I get asked over time when I applied to some companies. The list doesn't sort in anyways. I write it down randomly as I remember, or I come up with...
## Vanilla JS

#### What are JS Data types?
- Number
- Boolean
- String
- Object
- Null
- Undifined
- Symbol
- BigInt?

### Hoisting in JS?
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
 
### Scope and the Scope chain
Scope in JS, determines the accessibility of variables and functions at various parts in one’s code.

In general terms, the scope will let us know at a given part of code, what are the variables and functions that we can or cannot access.

![image](https://user-images.githubusercontent.com/30380214/127509531-a6ddd4bb-b9ec-496e-a6ef-b83751aed0b4.png)

There are three types of scopes in JS:
- Global Scope
- Local or Function Scope
- Block Scope

![image](https://user-images.githubusercontent.com/30380214/127509594-a0951896-9290-4075-8dd4-ef00e9b43104.png)

JavaScript engine also uses Scope to find variables.

![image](https://user-images.githubusercontent.com/30380214/127509653-18b67c6d-bc88-4f29-b3f4-e0701dd46e53.png)

**As you can see in the code above, if the javascript engine does not find the variable in local scope, it tries to check for the variable in the outer scope.      If the variable does not exist in the outer scope, it tries to find the variable in the global scope.**

If the variable is not found in the global space as well, reference error is thrown.

![image](https://user-images.githubusercontent.com/30380214/127509731-34c8b11b-d25f-40eb-bec0-38f671b2630e.png)
![image](https://user-images.githubusercontent.com/30380214/127509792-2548bcea-0345-43da-b544-b4f384b2d16d.png)
![image](https://user-images.githubusercontent.com/30380214/127509861-c61b4d26-7df6-4359-8800-21af8c9f66cb.png)
    
### Temporal Dead Zone for Let and Const
Temporal Dead Zone is a behavior that occurs with variables declared using let and const keywords.

It is a behavior where we try to access a variable before it is initialized.

![image](https://user-images.githubusercontent.com/30380214/127511171-391e46ee-fd96-4fed-b619-1bb5cda3a7a3.png)
![image](https://user-images.githubusercontent.com/30380214/127511209-0ba1df83-b5f2-4c79-955d-3d5423604bfb.png)

### The JS Engine and Runtime
![image](https://user-images.githubusercontent.com/30380214/127511658-0a364a29-67b4-4272-abe6-d334b1f872d8.png)
![image](https://user-images.githubusercontent.com/30380214/127511952-86a26e9c-20b4-4589-b543-d467430ccdf6.png)
![image](https://user-images.githubusercontent.com/30380214/127511964-ba4d0740-ec0e-4d9d-9120-dde674b1cc04.png)

### Execution Contexts and The Call Stack
![image](https://user-images.githubusercontent.com/30380214/127512479-ca556960-c588-4e70-aacf-ddaeab27d755.png)
![image](https://user-images.githubusercontent.com/30380214/127512521-58d24684-92b9-460d-b1fb-4941d86e7be7.png)
![image](https://user-images.githubusercontent.com/30380214/127512564-30932808-f4c3-48c1-b54a-2365795d9154.png)

### The `this` keyword
**The “this” keyword refers to the object that the function is a property of.**

**The value of “this” keyword will always depend on the object that is invoking the function.**
![image](https://user-images.githubusercontent.com/30380214/127512815-cd7f6b03-cf5e-44f0-91bb-4c77d83867a8.png)

10. ### The Eventloop
11. ### Promise
12. ### Async/Await, compare with Promise
13. ### Currying function in JS
14. ### Implement Infinite Scroll using IntersectionObserver API 
15. ### JS slice and splice
16. ### JS array reduce


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
9. ### CSS: Grid
10. ### CSS: Flexbox
11. ### CSS: Em vs Rem vs Pixel


---
## Computer Sience
1. ### List of Data structure
2. ### Some sorting algorithm
3. ### List of Algorithms



## 🤫 Behavior/Project Questions

### Your role at last company
My last company I worked for is Pixta Vietnam. At Pixta Vietnam, I joined it as Backend Developer, working mainly on Ruby, Rails and AWS. 
After about 1 year, Pixta have a new project, and also open a new position so I take that oppoturnity and changed my role to Front-end Developer.
As a FE developer, I working mainly on ReactJS, and NextJS. The more I work with FE, the more I interested on it. After 1 year, this project came to adverstizing state, where the workload is not much. Also, the environment of Pixta don't have much FE engineers, mostly is BE engineers, so my learning curve/speed on FE start going down. That why I'm looking for another oppoturnity.

---
### Why do you change from Back-end to Front-end
There are few reasons that made this decision. Personally, I always looking for challenges, to develop myself and growth at a faster pace. Also, I love the felling when you can solved challenging problem. So, at that time, changing to new fields is the most challenging challenge for me. Plus, FE in the last few years growing super fast, it have many new technologies, tools, frameworks, and it still growing. Compare to FE, BE is quite mature now, you can pickup any framework and then make a same product with that framework.

So, with all these reasons, I decided to take the challenge to become a FE developer.
And yeah, I'm happy because I take up that challenge. Learning FE and do the work in FE is very enjoyable and give me a lot of new knowledge. The more I work in FE, the more I interested on it.

---
### What I learn by transaction from Back-end to Front-end
> How I switched from building products for frontend developers to building products for users.

Transitioning from Back-End to Front-End development is not easy. I got used to the structure of back-end stuff where you usually build the data structures, writing tests, database tables, and creating API endpoints for Front-End consumption.

To date, these are my experiences while I transition from Back-End to Front-End developer:
- It’s all about User Interface and User Experience
- It makes you think of “UI-first” and how your app flows when starting your project 
- It lets you think of how to improve UI reusability
- It’s all about Browser-side performance and client-side optimizations
- You learn how to build Responsive Web Pages
- You learn how to look at SEO as well
- You learn to be good at CSS
- You want to be a designer

---
### Tell me about your last project

### Problem on your project - Image grid

### Problem on your project - Speed optimization

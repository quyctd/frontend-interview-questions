# Vanillia JS Interview Questions

## What are JS Data types?
- Number
- Boolean
- String
- Object
- Null
- Undifined
- Symbol
- BigInt?

## Hoisting in JS?
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
 
## Scope and the Scope chain
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
    
## Temporal Dead Zone for Let and Const
Temporal Dead Zone is a behavior that occurs with variables declared using let and const keywords.

It is a behavior where we try to access a variable before it is initialized.

![image](https://user-images.githubusercontent.com/30380214/127511171-391e46ee-fd96-4fed-b619-1bb5cda3a7a3.png)
![image](https://user-images.githubusercontent.com/30380214/127511209-0ba1df83-b5f2-4c79-955d-3d5423604bfb.png)

## The JS Engine and Runtime
![image](https://user-images.githubusercontent.com/30380214/127511658-0a364a29-67b4-4272-abe6-d334b1f872d8.png)
![image](https://user-images.githubusercontent.com/30380214/127511952-86a26e9c-20b4-4589-b543-d467430ccdf6.png)
![image](https://user-images.githubusercontent.com/30380214/127511964-ba4d0740-ec0e-4d9d-9120-dde674b1cc04.png)

## Execution Contexts and The Call Stack
![image](https://user-images.githubusercontent.com/30380214/127512479-ca556960-c588-4e70-aacf-ddaeab27d755.png)
![image](https://user-images.githubusercontent.com/30380214/127512521-58d24684-92b9-460d-b1fb-4941d86e7be7.png)
![image](https://user-images.githubusercontent.com/30380214/127512564-30932808-f4c3-48c1-b54a-2365795d9154.png)

## The `this` keyword
**The “this” keyword refers to the object that the function is a property of.**

**The value of “this” keyword will always depend on the object that is invoking the function.**
![image](https://user-images.githubusercontent.com/30380214/127512815-cd7f6b03-cf5e-44f0-91bb-4c77d83867a8.png)

## Primitive types and Reference types
![image](https://user-images.githubusercontent.com/30380214/127741744-7c544403-cc89-469c-9949-a56888f10dc6.png)

## First-class vs High-order functions
In computer science, a programming language is said to have **first-class functions** if it treats functions as **first-class citizens**. This means the language supports **passing functions as arguments** to other functions, **returning them as the values** from other functions, and **assigning them to variables** or **storing them in data structures**.

High-order function is a function that **receives** another functions **as a arguments**, or **returns a new function**, or **both** 

![image](https://user-images.githubusercontent.com/30380214/127742630-a322c1e2-5b7c-4480-b90d-65de45d2a37f.png)

## The `apply`, `call`, `bind` methods

**call()**

It’s a predefined method in javascript.
This method invokes a method (function) by specifying the owner object.

Example 1:
```jsx
function sayHello(){
  return "Hello " + this.name;
}
        
var obj = {name: "Sandy"};
        
sayHello.call(obj);
        
// Returns "Hello Sandy"
```

call() method allows an object to use the method (function) of another object.

Example 2:
```jsx
var person = {
  age: 23,
  getAge: function(){
    return this.age;
  }
}
        
var person2 = {age:  54};
person.getAge.call(person2);
        
// Returns 54
```
call() accepts arguments:
```jsx
function saySomething(message){
  return this.name + " is " + message;
}
        
var person4 = {name:  "John"};
        
saySomething.call(person4, "awesome");
// Returns "John is awesome"
```
**apply()**

The apply method is similar to the call() method. The only difference is that,

**call() method takes arguments separately whereas, apply() method takes arguments as an array.**

```jsx
function saySomething(message){
  return this.name + " is " + message;
}
 
var person4 = {name:  "John"};
        
saySomething.apply(person4, ["awesome"]);
```

**bind()**

This method returns a new function, where the value of “this” keyword will be bound to the owner object, which is provided as a parameter.
Example with arguments:
```jsx
var bikeDetails = {
    displayDetails: function(registrationNumber,brandName){
    return this.name+ " , "+ "bike details: "+ registrationNumber + " , " + brandName;
  }
}
        
var person1 = {name:  "Vivek"};
        
var detailsOfPerson1 = bikeDetails.displayDetails.bind(person1, "TS0122", "Bullet");
        
// Binds the displayDetails function to the person1 object
detailsOfPerson1();
// Returns Vivek, bike details: TS0452, Thunderbird
```

## Immediately invoked Function Expressions

An Immediately Invoked Function ( known as IIFE and pronounced as IIFY) is a function that runs as soon as it is defined.

Syntax of IIFE:
```jsx
(function(){ 
  // Do something;
})();
```
To understand IIFE, we need to understand the two sets of parentheses which are added while creating an IIFE:
First set of parenthesis:
```jsx
(function (){
   //Do something;
})
```
While executing javascript code, whenever the compiler sees the word “function”, it assumes that we are declaring a function in the code. Therefore, if we do not use the first set of parentheses, the compiler throws an error because it thinks we are declaring a function, and by the syntax of declaring a function, a function should always have a name.
```jsx
function() {
  //Do something;
}
// Compiler gives an error since the syntax of declaring a function is wrong in the code above.
```
To remove this error, we add the first set of parenthesis that tells the compiler that the function is not a function declaration, instead, it’s a function expression.
Second set of parenthesis:
```jsx
(function (){
  //Do something;
})();
```
From the definition of an IIFE, we know that our code should run as soon as it is defined. A function runs only when it is invoked. If we do not invoke the function, the function declaration is returned:
```jsx
(function (){
  // Do something;
})

// Returns the function declaration
```
**Therefore to invoke the function, we use the second set of parenthesis.**

## Closure
Closure makes the function remember all the variables that existed at the function's birthplace.
> Closures are nothing but FUNCTIONS WITH PRESERVED DATA

![image](https://user-images.githubusercontent.com/30380214/127747670-dc88668d-00d0-4fce-86fc-d3a3fc53f8a7.png)

**A function always has access to the variable environment(VE) of the execution context in which it was created, even after that execution context was gone.**

**Closure:  VE attached to the function, exactly as it was at the time and place the function was created**

![image](https://user-images.githubusercontent.com/30380214/127747700-a0b67238-0d06-4c7a-a7b5-747a0c547e88.png)

**Summary**
![image](https://user-images.githubusercontent.com/30380214/127747704-81c1be17-2e07-44bf-a3fe-1fb81c888dd7.png)

**This ability of a function to store a variable for further reference even after it is executed, is called Closure.**

## The Eventloop
## Promise
## Why do we need async/await/promise
## Async/Await, compare with Promise
## Currying function in JS
## Implement Infinite Scroll using IntersectionObserver API 
## JS slice and splice
## JS array reduce

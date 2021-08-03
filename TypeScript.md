# TypeScript Interview Questions

### What Typescript
TypeScript is an open-source language developed by Microsoft. It’s a **statically-typed superset** of JavaScript that compiles to plain JavaScript. It runs on any browser, host, and operating system. That means **all valid JavaScript code is also TypeScript code**. It offers advanced features such as IntelliSense, code completion, safe refactorings, etc.

### Why Typescript
There are different reasons why a JavaScript developer should consider using TypeScript. Some of them include:
- **Using new features of ECMAScript**

  TypeScript supports new ECMAScript standards and transpile them to ECMAScript targets of your choice. So, you can use features of ES2015 and beyond, like modules, lambda functions, classes, the spread operator, de-structuring, today.

- **Static typing**

  JavaScript is dynamically typed and does not know what type a variable is until it is actually instantiated at run-time. TypeScript adds type support to JavaScript.

- **Type Inference**

  TypeScript makes typing a bit easier and a lot less explicit by the usage of type inference. Even if you don’t explicitly type the types, they are still there to save you from doing something which otherwise would result in a run-time error.

- **Better IDE support**

  The development experience with TypeScript is a great improvement over JavaScript. There is a wide range of IDEs that have excellent support for TypeScript, like Visual Studio & VS code, Atom, Sublime, and IntelliJ/WebStorm.

- **Strict Null Checking**

  Errors, like cannot read property ‘x’ of undefined, is common in JavaScript programming. You can avoid most of these kinds of errors since one cannot use a variable that is not known to the TypeScript compiler.

- **Interoperability**

  TypeScript is closely related to JavaScript so it has great interoperability capabilities, but some extra work is required to work with JavaScript libraries in TypeScript.

### Compare Types vs Interfaces
**Interfaces are basically a way to describe data shapes, for example, an object.**
**Type is a definition of a type of data, for example, a union, primitive, intersection, tuple, or any other type.**

Type aliases and interfaces are very similar, and in many cases you can choose between them freely. Almost all features of an interface are available in type, the key distinction is that a type cannot be re-opened to add new properties vs an interface which is always extendable.

![Image](https://user-images.githubusercontent.com/30380214/128041806-ec4fc9c9-a0d1-44cc-8986-2f217491393d.png)

### Extends and implements
In TypeScript, we can easily extend and implement interfaces. This is not possible with types though.

Interfaces in TypeScript can extend classes, this is a very awesome concept that helps a lot in a more object-oriented way of programming. We can also create classes implementing interfaces.

For example, let’s imagine that we have a class called Car and an interface called NewCar, we can easily extend this class using an interface:
```jsx
class Car {
  printCar = () => {
    console.log("this is my car")
  }
};

interface NewCar extends Car {
  name: string;
};

class NewestCar implements NewCar {
  name: "Car";
  constructor(engine:string) {
    this.name = name
  }
  printCar = () => {
    console.log("this is my car")
  }
};
```

### Intersection
Intersection allows us to combine multiple types into a single one type. To create an intersection type, we have to use the `&` keyword:
```jsx
type Name = {
  name: “string”
};

type Age = {
  age: number
};

type Person = Name & Age;
```

The nice thing here is that we can create a new intersection type combining two interfaces, for example, but not the other way around. We cannot create an interface combining two types, because it doesn’t work:
```jsx
interface Name {
  name: “string”
};

interface Age {
  age: number
};

type Person = Name & Age;
```

### Unions
Union types allow us to create a new type that can have a value of one or a few more types. To create a union type, we have to use the `|` keyword.
```jsx
type Man = {
  name: “string”
};

type Woman = {
  name: “string”
};

type Person = Man | Woman;
```

Similar to intersections, we can create a new union type combining two interfaces, for example, but not the other way around:
```jsx
interface Man {
  name: "string"
};

interface Woman {
  name: "string"
};

type Person = Man | Woman;
```

### Tuples
Tuples are a very helpful concept in TypeScript, it brought to us this new data type that includes two sets of values of different data types.
```jsx
type Reponse = [string, number]
```
But, in TypeScript, we can only declare tuples using types and not interfaces. There’s no way we can declare a tuple in TypeScript using an interface, but you still are able to use a tuple inside an interface, like this:
```jsx
interface Response {
  value: [string, number]
}
```

### What should I use: Types and Interfaces
Interfaces are better when you need to define a new object or method of an object. For example, in React applications, when you need to define the props that a specific component is going to receive, it’s ideal to use interface over types:
```jsx
interface TodoProps {
  name: string;
  isCompleted: boolean
};

const Todo: React.FC<TodoProps> = ({ name, isCompleted }) => {
  ...
};
```
Types are better when you need to create functions, for example. Let’s imagine that we have a function that’s going to return an object called, type alias is more recommended for this approach:
```jsx
type Person = {
  name: string,
  age: number
};

type ReturnPerson = (
  person: Person
) => Person;

const returnPerson: ReturnPerson = (person) => {
  return person;
};
```
Interface work better with objects and method objects, and types are better to work with functions, complex types, etc.

### Compare Unknown vs Any

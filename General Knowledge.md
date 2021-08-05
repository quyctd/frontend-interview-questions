# General Knowledge Questions

## Test Driven Development

## Micro Frontend

## List of design pattern in FE
#### Constructor / Builder Pattern - Creational Design
Separate the construction of a complex object from its representation, allowing the same construction process to create various representations.
**Basically, Class in JS already is a design pattern**

#### Factory Pattern - Creational Design
Define an interface for creating a single object, but let subclasses decide which class to instantiate. Factory Method lets a class defer instantiation to subclasses.
```js
function animalFactory() {
  this.createAnimal = function(animalType) {
    let animal;

    switch(animalType) {
      case 'dog':
        animal = new Dog();
        break;
      case 'cat':
        animal = new Cat();
        break;
      case 'horse':
        animal = new Horse();
        break;
      default:
        animal = new Monkey();
        break;
    }

    return animal;
  }
}
```
#### Prototype Pattern - Creational Design
Specify the kinds of objects to create using a prototypical instance, and create new objects from the 'skeleton' of an existing object, thus boosting performance and keeping memory footprints to a minimum.
```jsx
const macBook = {
  color: 'silver',
  turnOn() {
    console.log('turning on...');
  },
  turnOff() {
    console.log('turning off...');
  }
}

// Proper prototype cloning
const myComputer = Object.create(macBook, { owner: { value: 'Tim'} });
console.log(myComputer.__proto__ === macBook);

// Not a prototype copy
const newComputer = {...macBook, owner: 'John'};
console.log(newComputer.__proto__ === macBook);

macBook.power = 'USB-C';

// The protoype gets the new value for 'power'
console.log(myComputer.power);
// But the non-prototype doesn't
console.log(newComputer.power);
```
#### Singleton Pattern / Strict Pattern - Creational Design
Ensure a class has only one instance, and provide a global point of access to it.
```jsx
const Database = (function () {
  let instance;

  function createDatabaseInstance() {
    return new Object('Database Instance');
  }

  function getDatabaseInstance() {
    if (!instance) {
      instance = createDatabaseInstance();
    }

    return instance;
  }

  return { getDatabaseInstance }
})();

const databaseInstance1 = Database.getDatabaseInstance();
const databaseInstance2 = Database.getDatabaseInstance();

console.log(databaseInstance1 === databaseInstance2);
```

#### Decorator Pattern - Structural Design
Attach additional responsibilities to an object dynamically keeping the same interface. Decorators provide a flexible alternative to subclassing for extending functionality.
```jsx
const Animal = function(type) {
  this.type = type || 'dog';
}

const dog = new Animal('dog');
const cat = new Animal('cat');

dog.bark = function() {
  console.log('woof woof!');
  return this;
}

cat.meow = function() {
  console.log('meow meooooooow!');
  return this;
}

dog.bark();
cat.meow();
```

## Compare GraphQL vs Rest API
A REST API is an architectural concept for network-based software. GraphQL, on the other hand, is a query language, a specification, and a set of tools that operates over a single endpoint using HTTP. In addition, over the last few years, REST has been used to make new APIs, while the focus of GraphQL has been to optimize for performance and flexibility.

With REST, you have to make three requests to different endpoints to fetch the required data. You’re also overfetching since the endpoints return additional information that’s not needed.
![image](https://user-images.githubusercontent.com/30380214/128300926-013e0485-dd5e-4557-a6d8-a0443685c52d.png)

Using GraphQL, the client can specify exactly the data it needs in a query. Notice that the structure of the server’s response follows precisely the nested structure defined in the query.
![image](https://user-images.githubusercontent.com/30380214/128300963-afb85640-44c3-4724-97aa-6551dce17864.png)
=> No more Over- and Underfetching

![Screen Shot 2021-08-05 at 1 20 35 PM](https://user-images.githubusercontent.com/30380214/128301153-450c0e25-6fe6-4d63-9a8d-173400e6a45b.png)

## Testing: Jest & React Testing Library

## Animation: GSAP, react-transition-group

## RxJS - Observable

## style - SaSS, SCSS

## CSS: Grid

## CSS: Flexbox

## CSS: Em vs Rem vs Pixel

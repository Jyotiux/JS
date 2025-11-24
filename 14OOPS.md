
---

# 1. Introduction to OOP in JavaScript

Object-Oriented Programming (OOP) organizes code around **objects**—real-world entities that have:

* **Properties** (data)
* **Methods** (behaviors)

JavaScript supports OOP through:

* Object literals
* Functions (constructor functions, prototypes)
* ES6 classes

OOP pillars:

1. Encapsulation
2. Abstraction
3. Inheritance
4. Polymorphism

---

# 2. Objects

An object is a collection of key–value pairs.

### Object literal example

```js
const car = {
  brand: "Toyota",
  model: "Corolla",
  start() {
    console.log("Car started");
  }
};

console.log(car.brand);
car.start();
```

### Accessing properties

```js
car.brand;
car["model"];
```

### Adding properties

```js
car.year = 2020;
```

### Deleting properties

```js
delete car.model;
```

---

# Quiz: Objects (sample)

1. How do you access an object's property using bracket notation?
2. How do you add a new method to an object?
3. What is the difference between dot and bracket notation?

---

# 3. Classes

Classes are blueprints for creating objects.

### Example

```js
class Car {
  start() {
    console.log("Car started");
  }
}

const c = new Car();
c.start();
```

Classes are **syntactic sugar** over prototypes.

---

# 4. Constructor Method

The constructor runs automatically when creating an object.

```js
class Car {
  constructor(brand, model) {
    this.brand = brand;
    this.model = model;
  }
}

const c1 = new Car("Toyota", "Camry");
console.log(c1.brand);
```

---

# 5. this Keyword

`this` refers to the object that is currently using the method.

### Example

```js
class Car {
  constructor(brand) {
    this.brand = brand;
  }
  show() {
    console.log(this.brand);
  }
}

const c = new Car("BMW");
c.show();   // this refers to c
```

### `this` depends on call context, not function location.

---

# 6. Prototype

Every JavaScript object has a hidden internal property `[[Prototype]]`.

Methods shared by all instances are stored on the prototype.

### Example using constructor function

```js
function Person(name) {
  this.name = name;
}

Person.prototype.sayHi = function() {
  console.log("Hi, I am " + this.name);
};

const p = new Person("John");
p.sayHi();
```

### Prototype chain

If a property is not found → JavaScript searches in its prototype.

---

# 7. Static Methods

Static methods belong to the **class itself**, not to instances.

### Example

```js
class MathTools {
  static add(a, b) {
    return a + b;
  }
}

MathTools.add(5, 3); // Works
const m = new MathTools();
// m.add(5,3);   // Error
```

Used for utility functions.

---

# 8. Inheritance

Inheritance allows one class to inherit another.

### Example

```js
class Animal {
  eat() {
    console.log("Eating");
  }
}

class Dog extends Animal {
  bark() {
    console.log("Barking");
  }
}

const d = new Dog();
d.eat();
d.bark();
```

`Dog` inherits the `eat()` method from `Animal`.

### Using super()

```js
class Animal {
  constructor(name) {
    this.name = name;
  }
}

class Dog extends Animal {
  constructor(name, breed) {
    super(name);
    this.breed = breed;
  }
}
```

---

# Quiz: Classes and Inheritance (sample)

1. What does `extends` do?
2. How do you call the parent constructor?
3. Why are static methods not accessible on object instances?

---

# 9. Encapsulation

Encapsulation hides internal details and restricts access.

### Private fields with

```js
class User {
  #password;

  constructor(name, password) {
    this.name = name;
    this.#password = password;
  }

  checkPassword(pw) {
    return pw === this.#password;
  }
}

const u = new User("John", "123");
console.log(u.checkPassword("123")); // true
```

Private fields cannot be accessed directly:

```js
u.#password; // Error
```

---

# 10. Abstraction

Abstraction hides complexity and exposes essentials.

### Example

```js
class CoffeeMachine {
  start() { this.#boilWater(); }
  #boilWater() { console.log("Heating water"); }
}

const c = new CoffeeMachine();
c.start();   // Works
// c.#boilWater();  // Error (hidden)
```

Users interact with simple interfaces, not inner workings.

---

# 11. Polymorphism

Same method name, different behavior.

### Example with method overriding

```js
class Animal {
  speak() {
    console.log("Animal sound");
  }
}

class Dog extends Animal {
  speak() {
    console.log("Bark");
  }
}

class Cat extends Animal {
  speak() {
    console.log("Meow");
  }
}

new Dog().speak();
new Cat().speak();
```

---

# 12. Getters and Setters

Used to control access to properties.

### Example

```js
class Person {
  constructor(name) {
    this._name = name;
  }

  get name() {
    return this._name.toUpperCase();
  }

  set name(val) {
    if (val.length < 3) {
      console.log("Name too short");
      return;
    }
    this._name = val;
  }
}

const p = new Person("John");
console.log(p.name);

p.name = "Al";
```

---

# Quiz: OOP (sample)

1. What is encapsulation?
2. What is polymorphism?
3. What is the difference between a class and an object?
4. What is the purpose of getters and setters?
5. What does `super()` do inside a subclass?

---


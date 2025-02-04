
---


### **📌 6-Day JavaScript & TypeScript Learning Schedule**

| **Day**  | **Concepts Covered** | **JS / TS** |
|----------|----------------------|-------------|
| **Day 1** | ✅ Variables (`var`, `let`, `const`) <br> ✅ Data Types (`string`, `number`, `boolean`, `object`, `array`) <br> ✅ Operators (`+`, `-`, `*`, `/`, `==`, `===`, `&&`, `||`) | Common (JS & TS) |
| **Day 2** | ✅ Functions (`function`, arrow functions) <br> ✅ Loops (`for`, `while`, `do-while`) <br> ✅ Conditionals (`if`, `else`, `switch`) | Common (JS & TS) |
| **Day 3** | ✅ Arrays & Methods (`push`, `pop`, `map`, `filter`, `reduce`) <br> ✅ Objects & Object Methods <br> ✅ ES6 Features (`spread`, `destructuring`) | Common (JS & TS) |
| **Day 4** | ✅ JavaScript Classes & OOP Concepts <br> ✅ Prototypes, `this`, and Closures <br> ✅ Async JS (`Promises`, `async/await`) | JavaScript (JS) |
| **Day 5** | ✅ TypeScript Basics: Type Annotations (`number`, `string`, `boolean`) <br> ✅ Type Inference & Type Assertions <br> ✅ Optional & Default Parameters | TypeScript (TS) |
| **Day 6** | ✅ TypeScript Interfaces & Enums <br> ✅ Generics & Utility Types <br> ✅ Tuples & Advanced Object Types <br> ✅ TypeScript Classes & OOP with Access Modifiers | TypeScript (TS) |

---
Sure! Below are examples for each concept covered in the **6-Day JavaScript & TypeScript Learning Schedule**.

---

### **Day 1: Core JavaScript & TypeScript Fundamentals (Common Concepts)**

#### **1. Variables (`var`, `let`, `const`)**
```js
// JavaScript
var x = 10;   // Function scoped
let y = 20;   // Block scoped
const z = 30; // Block scoped, cannot be reassigned

console.log(x, y, z);
```

#### **2. Data Types**
```js
// JavaScript
let name = "John";          // string
let age = 30;               // number
let isAdult = true;         // boolean
let person = {name, age};   // object
let numbers = [1, 2, 3];    // array
```

#### **3. Operators**
```js
// JavaScript
let a = 10;
let b = 5;

console.log(a + b); // Arithmetic
console.log(a == b); // Comparison
console.log(a === 10 && b > 3); // Logical
```
https://github.com/Academix1/JavaScript/blob/main/Day1.md
---
### **Day 2: Functions, Loops, and Conditionals (Common Concepts)**

#### **1. Functions**
```js
// JavaScript
function greet(name) {
  return `Hello, ${name}!`;
}

const greetArrow = (name) => `Hello, ${name}!`;

console.log(greet("John"));
console.log(greetArrow("John"));
```

#### **2. Loops**
```js
// JavaScript
// For loop
for (let i = 0; i < 5; i++) {
  console.log(i);
}

// While loop
let count = 0;
while (count < 3) {
  console.log(count);
  count++;
}
```

#### **3. Conditionals**
```js
// JavaScript
let x = 10;

if (x > 5) {
  console.log("x is greater than 5");
} else {
  console.log("x is less than or equal to 5");
}
```

https://github.com/Academix1/JavaScript/blob/main/Day3.md
---

### **Day 3: Arrays, Methods, and ES6 Features (Common Concepts)**

#### **1. Arrays and Methods**
```js
// JavaScript
let arr = [1, 2, 3, 4, 5];

// Array Methods
arr.push(6);         // Add to end
arr.pop();           // Remove from end
let doubled = arr.map((num) => num * 2);  // map
let evens = arr.filter((num) => num % 2 === 0);  // filter
let sum = arr.reduce((total, num) => total + num, 0); // reduce

console.log(doubled, evens, sum);
```

#### **2. Objects and Object Methods**
```js
// JavaScript
let person = {
  name: "John",
  age: 30,
  greet: function() {
    console.log(`Hello, my name is ${this.name}`);
  }
};

person.greet();
```

#### **3. ES6 Features**
```js
// JavaScript
// Destructuring
const person = { name: "John", age: 30 };
const { name, age } = person;
console.log(name, age);

// Spread operator
const arr1 = [1, 2];
const arr2 = [...arr1, 3, 4];
console.log(arr2);
```

https://github.com/Academix1/JavaScript/blob/main/Day4.md
---

https://github.com/Academix1/JavaScript/blob/main/Day3.md

### **Day 4: JavaScript-specific Concepts**

#### **1. Classes & OOP Concepts**
```js
// JavaScript
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  greet() {
    console.log(`Hello, my name is ${this.name}`);
  }
}

const john = new Person("John", 30);
john.greet();
```

#### **2. Prototypes, `this`, and Closures**
```js
// JavaScript

// Prototypes
function Animal(name) {
  this.name = name;
}
Animal.prototype.sayHello = function() {
  console.log(`Hello, I'm ${this.name}`);
};

const dog = new Animal("Dog");
dog.sayHello(); // Inherited from prototype

// `this`
function showName() {
  console.log(this.name); // `this` refers to the object it's called on
}
const obj = { name: "John" };
showName.call(obj); // Explicitly setting `this` with .call()

// Closure
function outer() {
  let count = 0;
  return function inner() {
    count++;
    console.log(count);
  };
}
const counter = outer();
counter(); // 1
counter(); // 2
```

#### **3. Async JavaScript**
```js
// JavaScript - Promises
const fetchData = new Promise((resolve, reject) => {
  setTimeout(() => resolve("Data fetched!"), 2000);
});

fetchData.then((data) => console.log(data));

// Async/Await
async function fetchDataAsync() {
  const data = await fetchData;
  console.log(data);
}

fetchDataAsync();
```

---

### **Day 5: TypeScript Basics**

#### **1. Type Annotations**
```ts
// TypeScript
let age: number = 30;
let name: string = "John";
let isAdult: boolean = true;

let person: { name: string; age: number } = {
  name: "John",
  age: 30,
};
```

#### **2. Type Inference & Type Assertions**
```ts
// Type Inference
let city = "New York"; // Inferred as string

// Type Assertion
let value: any = "Hello";
let strLength: number = (value as string).length; // Asserting type to string
```

#### **3. Optional & Default Parameters**
```ts
// TypeScript
function greet(name: string, age: number = 30): string {
  return `Hello, ${name}. You are ${age} years old.`;
}

console.log(greet("John")); // Default age used
console.log(greet("John", 25)); // Passed age used
```

---

### **Day 6: Advanced TypeScript Features**

#### **1. Interfaces & Enums**
```ts
// TypeScript
interface Person {
  name: string;
  age: number;
}

let john: Person = {
  name: "John",
  age: 30,
};

enum Color {
  Red,
  Green,
  Blue,
}

let myColor: Color = Color.Green;
console.log(myColor);
```

#### **2. Generics & Utility Types**
```ts
// TypeScript
function identity<T>(value: T): T {
  return value;
}

console.log(identity("Hello"));
console.log(identity(42));

// Utility Type - Partial
interface Person {
  name: string;
  age: number;
}

const partialPerson: Partial<Person> = { name: "John" }; // Only name is required
```

#### **3. Tuples & Advanced Object Types**
```ts
// TypeScript
let tuple: [string, number] = ["John", 30];  // Tuple type
let user: { name: string; age: number; readonly id: string } = { name: "John", age: 30, id: "123" }; // readonly property
```

#### **4. Classes & OOP with Access Modifiers**
```ts
// TypeScript
class Person {
  public name: string; // Accessible from anywhere
  private age: number; // Accessible only inside the class
  protected id: number; // Accessible in this class and subclasses

  constructor(name: string, age: number, id: number) {
    this.name = name;
    this.age = age;
    this.id = id;
  }

  greet() {
    console.log(`Hello, my name is ${this.name}`);
  }
}

const person = new Person("John", 30, 123);
person.greet();
```

---

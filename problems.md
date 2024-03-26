## JAVASCRIPT INTERVIEW QUESTIONS

### Problem 1:
  let a = [1, 2, 3, 4, 5];
  let b = a;
  b[0] = 0;
  console.log(a); 

Answer: [0, 2, 3, 4, 5]
Explanation: In JavaScript, arrays are reference types. When you assign an array to another variable, you are assigning a reference to the array. So, when you modify the array using variable b, the array that variable a is referencing is also modified.

### Problem 2:
  console.log(1 + '2' + '2');
  console.log(1 + +'2' + '2');
  console.log(1 + -'1' + '2');
  console.log(+'1' + '1' + '2');
  console.log('A' - 'B' + '2');
  console.log('A' - 'B' + 2);

Answer:
  122
  32
  02
  112
  NaN2
  NaN
Explanation: The + operator is used for both addition and concatenation. When you use the + operator on numbers and strings, JavaScript converts the numbers to strings. The - operator only works for numbers, so it converts strings to numbers. If you try to subtract a string from another string, you will get NaN (Not a Number).

### Problem 3:
  console.log(1 < 2 < 3);
  console.log(3 > 2 > 1);

Answer:
  true
  false
Explanation: The < and > operators are left-associative, which means they are evaluated from left to right. In the first expression, 1 < 2 is true, which is converted to 1, so the expression becomes 1 < 3, which is true. In the second expression, 3 > 2 is true, which is converted to 1, so the expression becomes 1 > 1, which is false.

### Problem 4:
  console.log(0.1 + 0.2);
  console.log(0.1 + 0.2 == 0.3);

Answer:
  0.30000000000000004
  false
Explanation: In JavaScript, numbers are represented in binary floating-point format, which can lead to precision errors. When you add 0.1 and 0.2, the result is not exactly 0.3 due to the way floating-point numbers are stored. This is why the equality check returns false.

### Problem 5: var 
  var a = 1;
  function foo() {
    var a = 2;
    console.log(a);
  }
  foo();
  console.log(a);

Answer:
  2
  1
Explanation: The var keyword is function-scoped, which means that variables declared with var are only accessible within the function they are declared in. In this case, the variable a inside the foo function is separate from the variable a outside the function. When you call the foo function, it logs the value of the inner variable a (2), and when you log the value of a outside the function, it logs the value of the outer variable a (1).

### Problem 6: let
  let a = 1;
  function foo() {
    let a = 2;
    console.log(a);
  }
  foo();
  console.log(a);

Answer:
  2
  1
Explanation: The let keyword is block-scoped, which means that variables declared with let are only accessible within the block they are declared in. In this case, the variable a inside the foo function is separate from the variable a outside the function. When you call the foo function, it logs the value of the inner variable a (2), and when you log the value of a outside the function, it logs the value of the outer variable a (1).

### Problem 7: const
  const a = 1;
  a = 2;
  console.log(a);

Answer:
  TypeError: Assignment to constant variable.

Explanation: Variables declared with const are read-only, which means they cannot be reassigned. If you try to reassign a value to a const variable, you will get a TypeError.

### Problem 8: Hoisting
  console.log(a);
  var a = 1;

Answer:
  undefined
Explanation: In JavaScript, variable declarations are hoisted to the top of their scope, but not their initializations. This means that the variable a is hoisted to the top of the script, but its value is not assigned until the line where it is declared. So, when you try to log the value of a before it is assigned, you get undefined.

### Problem 9: Hoisting
  console.log(a);
  let a = 1;

Answer:
  ReferenceError: Cannot access 'a' before initialization.

Explanation: Variables declared with let and const are hoisted to the top of their block, but they are not initialized until the line where they are declared. This means that you cannot access the value of a let or const variable before it is assigned, which results in a ReferenceError.

### Problem 10: 
  for (var i = 0; i < 5; i++) {
    setTimeout(function() {
      console.log(i);
    }, 1000);
  }

Answer:
  5
  5
  5
  5
  5

Explanation: The setTimeout function is asynchronous, which means that the callback function is executed after the loop has finished. By the time the callback function is executed, the value of i is 5, which is why it logs 5 five times.

### Problem 11: 
  for (let i = 0; i < 5; i++) {
    setTimeout(function() {
      console.log(i);
    }, 1000);
  }

Answer:
  0
  1
  2
  3
  4

Explanation: When you use let to declare the variable i in the for loop, a new variable i is created for each iteration of the loop. This means that each callback function captures the value of i at the time it was created, resulting in the expected output.

### Problem 12: 
  const person = {
    name: 'John',
    age: 30
  };
  person.name = 'Jane';
  person.age = 25;
  console.log(person);

Answer:
  { name: 'Jane', age: 25 }

Explanation: While you cannot reassign a const variable, you can mutate the properties of an object declared with const. In this case, you are changing the values of the name and age properties of the person object, which is allowed.

### Problem 13: 
  const person = {
    name: 'John',
    age: 30
  };
  person = {
    name: 'Jane',
    age: 25
  };
  console.log(person);

Answer:
  TypeError: Assignment to constant variable.

Explanation: When you declare a variable with const, you cannot reassign it to a new value. In this case, you are trying to reassign the person variable to a new object, which is not allowed and results in a TypeError.

### Problem 14: 
  const person = {
    name: 'John',
    age: 30
  };
  Object.freeze(person);
  person.name = 'Jane';
  person.age = 25;
  console.log(person);

Answer:
  { name: 'John', age: 30 }

Explanation: The Object.freeze method is used to make an object immutable, which means you cannot add, remove, or modify properties of the object. When you try to change the name and age properties of the person object after freezing it, the changes are ignored, and the object remains the same.

### Problem 15: 
  const person = {
    name: 'John',
    age: 30
  };
  Object.seal(person);
  person.name = 'Jane';
  person.age = 25;
  console.log(person);

Answer:
  { name: 'Jane', age: 25 }

Explanation: The Object.seal method is used to make an object non-extensible, which means you cannot add or remove properties from the object, but you can modify existing properties. When you try to change the name and age properties of the person object after sealing it, the changes are allowed, and the object is updated.

### Problem 16: 
  const person = {
    name: 'John',
    age: 30
  };
  Object.preventExtensions(person);
  person.name = 'Jane';
  person.age = 25;
  console.log(person);

Answer:
  { name: 'Jane', age: 25 }

Explanation: The Object.preventExtensions method is used to make an object non-extensible, which means you cannot add new properties to the object, but you can modify existing properties. When you try to change the name and age properties of the person object after preventing extensions, the changes are allowed, and the object is updated.

### Problem 17: 
  const person = {
    name: 'John',
    age: 30
  };
  Object.defineProperty(person, 'name', { writable: false });
  person.name = 'Jane';
  console.log(person);

Answer:
  { name: 'John', age: 30 }

Explanation: The Object.defineProperty method is used to define or modify a property on an object. In this case, you are setting the name property of the person object to be non-writable, which means you cannot change its value. When you try to change the name property after defining it as non-writable, the change is ignored, and the object remains the same.

### Problem 18: 
  const person = {
    name: 'John',
    age: 30
  };
  Object.defineProperty(person, 'name', { configurable: false });
  delete person.name;
  console.log(person);

Answer:
  { age: 30 }

Explanation: The Object.defineProperty method is used to define or modify a property on an object. In this case, you are setting the name property of the person object to be non-configurable, which means you cannot delete the property. When you try to delete the name property after defining it as non-configurable, the property is not deleted, and the object remains the same.

### Problem 19: 
  const person = {
    name: 'John',
    age: 30
  };
  Object.defineProperty(person, 'name', { enumerable: false });
  for (let key in person) {
    console.log(key);
  }

Answer:
  age

Explanation: The Object.defineProperty method is used to define or modify a property on an object. In this case, you are setting the name property of the person object to be non-enumerable, which means it will not be included in for...in loops. When you loop over the keys of the person object using a for...in loop, only the age property is logged, as the name property is not enumerable.

### Problem 20: 
  const person = {
    name: 'John',
    age: 30
  };
  Object.defineProperty(person, 'name', { get: function() { return 'Jane'; } });
  console.log(person.name);

Answer:
  Jane

Explanation: The Object.defineProperty method is used to define or modify a property on an object. In this case, you are setting the name property of the person object to be a getter function that returns the value 'Jane'. When you access the name property of the person object, the getter function is called, and 'Jane' is returned.

### TOPIC: CLOSURES

### Problem 21: 
  function outer() {
    let a = 1;
    function inner() {
      console.log(a);
    }
    return inner;
  }
  const foo = outer();
  foo();

Answer:
  1

Explanation: A closure is a function that has access to its own scope, the outer function's scope, and the global scope. In this case, the inner function has access to the variable a in the outer function's scope, even after the outer function has returned. When you call the inner function, it logs the value of the variable a (1).

### Problem 22: 
  function outer() {
    let a = 1;
    function inner() {
      let b = 2;
      console.log(a + b);
    }
    return inner;
  }
  const foo = outer();
  foo();

Answer:
  3

Explanation: A closure is a function that has access to its own scope, the outer function's scope, and the global scope. In this case, the inner function has access to the variables a and b in the outer function's scope, even after the outer function has returned. When you call the inner function, it logs the sum of the variables a and b (3).

### Problem 23: 
  function outer() {
    let a = 1;
    function inner() {
      let b = 2;
      function nested() {
        let c = 3;
        console.log(a + b + c);
      }
      return nested;
    }
    return inner;
  }
  const foo = outer()();
  foo();

Answer:
  6

Explanation: A closure is a function that has access to its own scope, the outer function's scope, and the global scope. In this case, the nested function has access to the variables a, b, and c in the outer and inner functions' scopes, even after the outer function has returned. When you call the nested function, it logs the sum of the variables a, b, and c (6).

### Problem 24: 
  function outer() {
    let a = 1;
    function inner() {
      let b = 2;
      function nested() {
        let c = 3;
        console.log(a + b + c);
      }
      return nested;
    }
    return inner;
  }
  const foo = outer();
  const bar = foo();
  bar();

Answer:
  6

Explanation: A closure is a function that has access to its own scope, the outer function's scope, and the global scope. In this case, the nested function has access to the variables a, b, and c in the outer and inner functions' scopes, even after the outer function has returned. When you call the nested function, it logs the sum of the variables a, b, and c (6).

### Problem 25: 
  function outer() {
    let a = 1;
    function inner() {
      let b = 2;
      function nested() {
        let c = 3;
        console.log(a + b + c);
      }
      return nested;
    }
    return inner;
  }
  const foo = outer();
  const bar = foo();
  bar();

Answer:
  6

Explanation: A closure is a function that has access to its own scope, the outer function's scope, and the global scope. In this case, the nested function has access to the variables a, b, and c in the outer and inner functions' scopes, even after the outer function has returned. When you call the nested function, it logs the sum of the variables a, b, and c (6).

### Problem 26: 
  function outer() {
    let a = 1;
    function inner() {
      let b = 2;
      function nested() {
        let c = 3;
        console.log(a + b + c);
      }
      return nested;
    }
    return inner;
  }
  const foo = outer();
  const bar = foo();
  bar();

Answer:
  6


### Problem 27:
  function outer() {
    let a = 1;
    function inner() {
      let b = 2;
      function nested() {
        let c = 3;
        console.log(a + b + c);
      }
      return nested;
    }
    return inner;
  }
  const foo = outer();
  const bar = foo();
  bar();

Answer:
  6

Explanation: A closure is a function that has access to its own scope, the outer function's scope, and the global scope. In this case, the nested function has access to the variables a, b, and c in the outer and inner functions' scopes, even after the outer function has returned. When you call the nested function, it logs the sum of the variables a, b, and c (6).

### TOPIC: PROMISES

### Problem 28: 
  const promise = new Promise((resolve, reject) => {
    resolve('Resolved');
  });
  promise.then((value) => {
    console.log(value);
  });

Answer:
  Resolved

Explanation: A Promise is an object that represents the eventual completion (or failure) of an asynchronous operation and its resulting value. In this case, the promise is resolved with the value 'Resolved', and the then method is used to handle the resolved value and log it to the console.

### Problem 29: 
  const promise = new Promise((resolve, reject) => {
    reject('Rejected');
  });
  promise.catch((value) => {
    console.log(value);
  });

Answer:
  Rejected

Explanation: A Promise is an object that represents the eventual completion (or failure) of an asynchronous operation and its resulting value. In this case, the promise is rejected with the value 'Rejected', and the catch method is used to handle the rejected value and log it to the console.

### Problem 30: 
  const promise = new Promise((resolve, reject) => {
    resolve('Resolved');
  });
  promise.then((value) => {
    throw new Error('Error');
  }).catch((error) => {
    console.log(error.message);
  });

Answer:
  Error

Explanation: A Promise is an object that represents the eventual completion (or failure) of an asynchronous operation and its resulting value. In this case, the promise is resolved with the value 'Resolved', and the then method is used to throw an error. The catch method is then used to handle the error and log its message to the console.

### Problem 31: 
  const promise = new Promise((resolve, reject) => {
    reject('Rejected');
  });
  promise.then((value) => {
    console.log(value);
  }).catch((error) => {
    console.log(error);
  });

Answer:
  Rejected

Explanation: A Promise is an object that represents the eventual completion (or failure) of an asynchronous operation and its resulting value. In this case, the promise is rejected with the value 'Rejected', and the then method is used to handle the resolved value, which is not called. The catch method is then used to handle the rejected value and log it to the console.

### Problem 32: 
  const promise = new Promise((resolve, reject) => {
    resolve('Resolved');
  });
  promise.then((value) => {
    return 'New Value';
  }).then((value) => {
    console.log(value);
  });

Answer:
  New Value

Explanation: A Promise is an object that represents the eventual completion (or failure) of an asynchronous operation and its resulting value. In this case, the promise is resolved with the value 'Resolved', and the then method is used to return a new value. The next then method is then used to handle the new value and log it to the console.

### Problem 33: 
  const promise = new Promise((resolve, reject) => {
    resolve('Resolved');
  });
  promise.then((value) => {
    throw new Error('Error');
  }).then((value) => {
    console.log(value);
  }).catch((error) => {
    console.log(error.message);
  });

Answer:
  Error

Explanation: A Promise is an object that represents the eventual completion (or failure) of an asynchronous operation and its resulting value. In this case, the promise is resolved with the value 'Resolved', and the first then method is used to throw an error. The second then method is not called, and the catch method is used to handle the error and log its message to the console.

### TOPIC: ASYNC/AWAIT

### Problem 34: 
  async function foo() {
    return 'Hello';
  }
  foo().then((value) => {
    console.log(value);
  });

Answer:
  Hello

Explanation: The async function declaration defines an asynchronous function, which returns a Promise. In this case, the foo function returns the value 'Hello', which is then handled by the then method to log it to the console.

### Problem 35: 
  async function foo() {
    throw new Error('Error');
  }
  foo().catch((error) => {
    console.log(error.message);
  });

Answer:
  Error

Explanation: The async function declaration defines an asynchronous function, which returns a Promise. In this case, the foo function throws an error, which is then caught by the catch method and its message is logged to the console.

### Problem 36: 
  async function foo() {
    return Promise.resolve('Hello');
  }
  foo().then((value) => {
    console.log(value);
  }); 

Answer:
  Hello

Explanation: The async function declaration defines an asynchronous function, which returns a Promise. In this case, the foo function returns a resolved Promise with the value 'Hello', which is then handled by the then method to log it to the console.

### Problem 37: 
  async function foo() {
    const promise = new Promise((resolve, reject) => {
      resolve('Hello');
    });
    const value = await promise;
    console.log(value);
  }
  foo();

Answer:
  Hello
  
Explanation: The async function declaration defines an asynchronous function, which returns a Promise. In this case, the foo function creates a Promise that resolves with the value 'Hello', and the await keyword is used to wait for the Promise to resolve. The resolved value is then logged to the console.


### Problem 38: 
  async function foo() {
    const promise = new Promise((resolve, reject) => {
      reject('Error');
    });
    try {
      const value = await promise;
      console.log(value);
    } catch (error) {
      console.log(error);
    }
  }
  foo();

Answer:
  Error

Explanation: The async function declaration defines an asynchronous function, which returns a Promise. In this case, the foo function creates a Promise that is rejected with the value 'Error', and the await keyword is used to wait for the Promise to reject. The rejected value is then caught by the catch block and logged to the console.

### Problem 39: 
  async function foo() {
    const promise1 = new Promise((resolve, reject) => {
      resolve('Hello');
    });
    const promise2 = new Promise((resolve, reject) => {
      resolve('World');
    });
    const value1 = await promise1;
    const value2 = await promise2;
    console.log(value1 + ' ' + value2);
  }
  foo();

Answer:
  Hello World

Explanation: The async function declaration defines an asynchronous function, which returns a Promise. In this case, the foo function creates two Promises that resolve with the values 'Hello' and 'World', and the await keyword is used to wait for each Promise to resolve. The resolved values are then concatenated and logged to the console.

### Problem 40: 
  async function foo() {
    const promise1 = new Promise((resolve, reject) => {
      resolve('Hello');
    });
    const promise2 = new Promise((resolve, reject) => {
      reject('Error');
    });
    const value1 = await promise1;
    const value2 = await promise2;
    console.log(value1 + ' ' + value2);
  }
  foo();

Answer:
  Uncaught (in promise) Error

Explanation: The async function declaration defines an asynchronous function, which returns a Promise. In this case, the foo function creates two Promises, one that resolves with the value 'Hello' and one that rejects with the value 'Error'. When the second Promise is rejected, an uncaught error is thrown, as there is no catch block to handle the rejection.

### Problem 41: 
  async function foo() {
    const promise1 = new Promise((resolve, reject) => {
      resolve('Hello');
    });
    const promise2 = new Promise((resolve, reject) => {
      reject('Error');
    });
    try {
      const value1 = await promise1;
      const value2 = await promise2;
      console.log(value1 + ' ' + value2);
    } catch (error) {
      console.log(error);
    }
  }
  foo();

Answer:
  Error

Explanation: The async function declaration defines an asynchronous function, which returns a Promise. In this case, the foo function creates two Promises, one that resolves with the value 'Hello' and one that rejects with the value 'Error'. The try block is used to await each Promise and log the resolved values, and the catch block is used to catch any errors and log them to the console.

### Problem 42: 
  async function foo() {
    const promise1 = new Promise((resolve, reject) => {
      resolve('Hello');
    });
    const promise2 = new Promise((resolve, reject) => {
      reject('Error');
    });
    const values = await Promise.all([promise1, promise2]);
    console.log(values[0] + ' ' + values[1]);
  }
  foo();

Answer:
  Uncaught (in promise) Error

Explanation: The async function declaration defines an asynchronous function, which returns a Promise. In this case, the foo function creates two Promises, one that resolves with the value 'Hello' and one that rejects with the value 'Error'. When the Promise.all method is used to await both Promises, an uncaught error is thrown, as there is no catch block to handle the rejection.

### Problem 43: 
  async function foo() {
    const promise1 = new Promise((resolve, reject) => {
      resolve('Hello');
    });
    const promise2 = new Promise((resolve, reject) => {
      reject('Error');
    });
    try {
      const values = await Promise.all([promise1, promise2]);
      console.log(values[0] + ' ' + values[1]);
    } catch (error) {
      console.log(error);
    }
  }
  foo();

Answer:
  Error

### TOPIC: CLASSES

### Problem 44: 
  class Person {
    constructor(name, age) {
      this.name = name;
      this.age = age;
    }
    greet() {
      console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
    }
  }
  const person = new Person('John', 30);
  person.greet();

Answer:
  Hello, my name is John and I am 30 years old.

Explanation: Classes in JavaScript are a way to create objects with a blueprint for their properties and methods. In this case, the Person class defines a constructor that sets the name and age properties of a person object, and a greet method that logs a greeting message using those properties. When you create a new person object and call the greet method, the greeting message is logged to the console.

### Problem 45: 
  class Person {
    constructor(name, age) {
      this.name = name;
      this.age = age;
    }
    greet() {
      console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
    }
  }
  class Student extends Person {
    constructor(name, age, grade) {
      super(name, age);
      this.grade = grade;
    }
    study() {
      console.log(`${this.name} is studying in grade ${this.grade}.`);
    }
  }
  const student = new Student('Jane', 25, 10);
  student.greet();
  student.study();

Answer:
  Hello, my name is Jane and I am 25 years old.
  Jane is studying in grade 10.

Explanation: Classes in JavaScript can inherit from other classes using the extends keyword. In this case, the Student class extends the Person class, which means it inherits the properties and methods of the Person class. The Student class defines a constructor that sets the grade property of a student object, and a study method that logs a message about the student studying. When you create a new student object and call the greet and study methods, the greeting and study messages are logged to the console.

### Problem 46: 
  class Person {
    constructor(name, age) {
      this.name = name;
      this.age = age;
    }
    greet() {
      console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
    }
  }
  class Student extends Person {
    constructor(name, age, grade) {
      super(name, age);
      this.grade = grade;
    }
    study() {
      console.log(`${this.name} is studying in grade ${this.grade}.`);
    }
  }
  const person = new Person('John', 30);
  person.greet();
  person.study();


Answer:
  TypeError: person.study is not a function

Explanation: Classes in JavaScript can inherit from other classes using the extends keyword. In this case, the Student class extends the Person class, which means it inherits the properties and methods of the Person class. When you create a new person object using the Person class and try to call the study method, you get a TypeError because the study method is not defined in the Person class.

### Problem 47: 
  class Person {
    constructor(name, age) {
      this.name = name;
      this.age = age;
    }
    greet() {
      console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
    }
  }
  class Student extends Person {
    constructor(name, age, grade) {
      super(name, age);
      this.grade = grade;
    }
    study() {
      console.log(`${this.name} is studying in grade ${this.grade}.`);
    }
  }
  const student = new Student('Jane', 25, 10);
  student.greet();
  student.study();

Answer:
  Hello, my name is Jane and I am 25 years old.
  Jane is studying in grade 10.

Explanation: Classes in JavaScript can inherit from other classes using the extends keyword. In this case, the Student class extends the Person class, which means it inherits the properties and methods of the Person class. The Student class defines a constructor that sets the grade property of a student object, and a study method that logs a message about the student studying. When you create a new student object and call the greet and study methods, the greeting and study messages are logged to the console.

### Problem 48: 
  class Person {
    constructor(name, age) {
      this.name = name;
      this.age = age;
    }
    greet() {
      console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
    }
  }
  class Student extends Person {
    constructor(name, age, grade) {
      super(name, age);
      this.grade = grade;
    }
    greet() {
      console.log(`Hello, my name is ${this.name}, I am ${this.age} years old, and I am studying in grade ${this.grade}.`);
    }
  }
  const student = new Student('Jane', 25, 10);
  student.greet();

Answer:
  Hello, my name is Jane, I am 25 years old, and I am studying in grade 10.

Explanation: Classes in JavaScript can inherit from other classes using the extends keyword. In this case, the Student class extends the Person class, which means it inherits the properties and methods of the Person class. The Student class defines a constructor that sets the grade property of a student object, and a greet method that overrides the greet method of the Person class. When you create a new student object and call the greet method, the overridden greeting message is logged to the console.

### Problem 49: 
  class Person {
    constructor(name, age) {
      this.name = name;
      this.age = age;
    }
    greet() {
      console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
    }
  }
  class Student extends Person {
    constructor(name, age, grade) {
      super(name, age);
      this.grade = grade;
    }
    study() {
      console.log(`${this.name} is studying in grade ${this.grade}.`);
    }
  }
  const person = new Person('John', 30);
  person.greet();
  person.study(); 

Answer:
  TypeError: person.study is not a function

Explanation: Classes in JavaScript can inherit from other classes using the extends keyword. In this case, the Student class extends the Person class, which means it inherits the properties and methods of the Person class. When you create a new person object using the Person class and try to call the study method, you get a TypeError because the study method is not defined in the Person class.

### Problem 50: 
  class Person {
    constructor(name, age) {
      this.name = name;
      this.age = age;
    }
    greet() {
      console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
    }
  }
  class Student extends Person {
    constructor(name, age, grade) {
      super(name, age);
      this.grade = grade;
    }
    study() {
      console.log(`${this.name} is studying in grade ${this.grade}.`);
    }
  }
  const student = new Student('Jane', 25, 10);
  student.greet();
  student.study();

Answer:
  Hello, my name is Jane and I am 25 years old.
  Jane is studying in grade 10.

Explanation: Classes in JavaScript can inherit from other classes using the extends keyword. In this case, the Student class extends the Person class, which means it inherits the properties and methods of the Person class. The Student class defines a constructor that sets the grade property of a student object, and a study method that logs a message about the student studying. When you create a new student object and call the greet and study methods, the greeting and study messages are logged to the console.

### Problem 51: 
  class Person {
    constructor(name, age) {
      this.name = name;
      this.age = age;
    }
    greet() {
      console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
    }
  }
  class Student extends Person {
    constructor(name, age, grade) {
      super(name, age);
      this.grade = grade;
    }
    study() {
      console.log(`${this.name} is studying in grade ${this.grade}.`);
    }
  }
  const student = new Student('Jane', 25, 10);
  student.greet();
  student.study();

Answer:
  Hello, my name is Jane and I am 25 years old.
  Jane is studying in grade 10.

Explanation: Classes in JavaScript can inherit from other classes using the extends keyword. In this case, the Student class extends the Person class, which means it inherits the properties and methods of the Person class. The Student class defines a constructor that sets the grade property of a student object, and a study method that logs a message about the student studying. When you create a new student object and call the greet and study methods, the greeting and study messages are logged to the console.

### Problem 52: 
  class Person {
    constructor(name, age) {
      this.name = name;
      this.age = age;
    }
    greet() {
      console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
    }
  }
  class Student extends Person {
    constructor(name, age, grade) {
      super(name, age);
      this.grade = grade;
    }
    greet() {
      console.log(`Hello, my name is ${this.name}, I am ${this.age} years old, and I am studying in grade ${this.grade}.`);
    }
  }
  const student = new Student('Jane', 25, 10);
  student.greet();

Answer:
  Hello, my name is Jane, I am 25 years old, and I am studying in grade 10.

Explanation: Classes in JavaScript can inherit from other classes using the extends keyword. In this case, the Student class extends the Person class, which means it inherits the properties and methods of the Person class. The Student class defines a constructor that sets the grade property of a student object, and a greet method that overrides the greet method of the Person class. When you create a new student object and call the greet method, the overridden greeting message is logged to the console.


## TOPIC: OBJECTS

### Problem 53: 
  const person = {
    name: 'John',
    age: 30,
    greet: function() {
      console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
    }
  };
  person.greet();

Answer:
  Hello, my name is John and I am 30 years old.

Explanation: Objects in JavaScript can have properties and methods. In this case, the person object has name and age properties, and a greet method that logs a greeting message using those properties. When you call the greet method on the person object, the greeting message is logged to the console.


### Problem 54: 
  const person = {
    name: 'John',
    age: 30,
    greet: function() {
      console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
    }
  };
  person.greet = function() {
    console.log(`Hi, my name is ${this.name} and I am ${this.age} years old.`);
  };
  person.greet();

Answer:
  Hi, my name is John and I am 30 years old.

Explanation: Objects in JavaScript can have properties and methods. In this case, the person object has name and age properties, and a greet method that logs a greeting message using those properties. When you reassign the greet method on the person object with a new function, and then call the greet method, the new greeting message is logged to the console.

### Problem 55: 
  const person = {
    name: 'John',
    age: 30,
    greet: function() {
      console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
    }
  };
  delete person.age;
  person.greet();

Answer:
  Hello, my name is John and I am undefined years old.

Explanation: Objects in JavaScript can have properties and methods. In this case, the person object has name and age properties, and a greet method that logs a greeting message using those properties. When you delete the age property from the person object, the age property becomes undefined, and when you call the greet method, the greeting message is logged with the age property as undefined.

### Problem 56: 
  const person = {
    name: 'John',
    age: 30,
    greet: function() {
      console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
    }
  };
  person.location = 'New York';
  person.greet();

Answer:
  Hello, my name is John and I am 30 years old.

Explanation: Objects in JavaScript can have properties and methods. In this case, the person object has name and age properties, and a greet method that logs a greeting message using those properties. When you add a location property to the person object, and then call the greet method, the greeting message is logged to the console without including the location property.

### Problem 57: 
  const person = {
    name: 'John',
    age: 30,
    greet: function() {
      console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
    }
  };
  Object.defineProperty(person, 'age', { writable: false });
  person.age = 25;
  person.greet();

Answer:
  Hello, my name is John and I am 30 years old.

Explanation: Objects in JavaScript can have properties and methods. In this case, the person object has name and age properties, and a greet method that logs a greeting message using those properties. When you define the age property of the person object as non-writable, you cannot change its value, and when you try to change the age property, the change is ignored, and the greeting message is logged with the original age value.

### Problem 58: 
  const person = {
    name: 'John',
    age: 30,
    greet: function() {
      console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
    }
  };
  Object.defineProperty(person, 'age', { configurable: false });
  delete person.age;
  person.greet();

Answer:
  TypeError: Cannot delete property 'age' of #<Object>

Explanation: Objects in JavaScript can have properties and methods. In this case, the person object has name and age properties, and a greet method that logs a greeting message using those properties. When you define the age property of the person object as non-configurable, you cannot delete the property, and when you try to delete the age property, a TypeError is thrown.

### Problem 59: 
  const person = {
    name: 'John',
    age: 30,
    greet: function() {
      console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
    }
  };
  Object.defineProperty(person, 'age', { enumerable: false });
  for (let key in person) {
    console.log(key);
  }

Answer:
  name

Explanation: Objects in JavaScript can have properties and methods. In this case, the person object has name and age properties, and a greet method that logs a greeting message using those properties. When you define the age property of the person object as non-enumerable, it will not be included in for...in loops. When you loop over the keys of the person object using a for...in loop, only the name property is logged, as the age property is not enumerable.

### Problem 60: 
  const person = {
    name: 'John',
    age: 30,
    greet: function() {
      console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
    }
  };
  Object.defineProperty(person, 'age', { get: function() { return 25; } });
  console.log(person.age);

Answer:
  25

Explanation: Objects in JavaScript can have properties and methods. In this case, the person object has name and age properties, and a greet method that logs a greeting message using those properties. When you define the age property of the person object as a getter function that returns the value 25, and then access the age property, the getter function is called, and 25 is returned.



## TOPIC: ARRAYS

### Problem 61: 
  const numbers = [1, 2, 3, 4, 5];
  console.log(numbers[0]);

Answer:
  1

Explanation: Arrays in JavaScript are zero-indexed, which means the first element of an array has an index of 0. In this case, the numbers array contains the elements [1, 2, 3, 4, 5], and when you access the element at index 0, the value 1 is logged to the console.

### Problem 62: 
  const numbers = [1, 2, 3, 4, 5];
  console.log(numbers[5]);

Answer:
  undefined

Explanation: Arrays in JavaScript are zero-indexed, which means the first element of an array has an index of 0. In this case, the numbers array contains the elements [1, 2, 3, 4, 5], and when you try to access the element at index 5, which is beyond the length of the array, the value undefined is returned.

### Problem 63: 
  const numbers = [1, 2, 3, 4, 5];
  numbers[0] = 10;
  console.log(numbers);

Answer:
  [10, 2, 3, 4, 5]

Explanation: Arrays in JavaScript are mutable, which means you can change the elements of an array after it has been created. In this case, the numbers array contains the elements [1, 2, 3, 4, 5], and when you assign the value 10 to the element at index 0, the array is updated to [10, 2, 3, 4, 5].

### Problem 64: 
  const numbers = [1, 2, 3, 4, 5];
  numbers.push(6);
  console.log(numbers);

Answer:
  [1, 2, 3, 4, 5, 6]

Explanation: Arrays in JavaScript have built-in methods that allow you to add elements to the end of an array. In this case, the numbers array contains the elements [1, 2, 3, 4, 5], and when you use the push method to add the value 6 to the end of the array, the array is updated to [1, 2, 3, 4, 5, 6].

### Problem 65: 
  const numbers = [1, 2, 3, 4, 5];
  numbers.pop();
  console.log(numbers);

Answer:
  [1, 2, 3, 4]

Explanation: Arrays in JavaScript have built-in methods that allow you to remove elements from the end of an array. In this case, the numbers array contains the elements [1, 2, 3, 4, 5], and when you use the pop method to remove the last element from the array, the array is updated to [1, 2, 3, 4].

### Problem 66: 
  const numbers = [1, 2, 3, 4, 5];
  numbers.shift();
  console.log(numbers);

Answer:
  [2, 3, 4, 5]

Explanation: Arrays in JavaScript have built-in methods that allow you to remove elements from the beginning of an array. In this case, the numbers array contains the elements [1, 2, 3, 4, 5], and when you use the shift method to remove the first element from the array, the array is updated to [2, 3, 4, 5].

### Problem 67: 
  const numbers = [1, 2, 3, 4, 5];
  numbers.unshift(0);
  console.log(numbers);

Answer:
  [0, 1, 2, 3, 4, 5]

Explanation: Arrays in JavaScript have built-in methods that allow you to add elements to the beginning of an array. In this case, the numbers array contains the elements [1, 2, 3, 4, 5], and when you use the unshift method to add the value 0 to the beginning of the array, the array is updated to [0, 1, 2, 3, 4, 5].

### Problem 68: 
  const numbers = [1, 2, 3, 4, 5];
  numbers.splice(2, 0, 6);
  console.log(numbers);

Answer:
  [1, 2, 6, 3, 4, 5]

Explanation: Arrays in JavaScript have a splice method that allows you to add or remove elements from an array at a specific index. In this case, the numbers array contains the elements [1, 2, 3, 4, 5], and when you use the splice method to add the value 6 at index 2 (without removing any elements), the array is updated to [1, 2, 6, 3, 4, 5].

### Problem 69: 
  const numbers = [1, 2, 3, 4, 5];
  numbers.splice(2, 1);
  console.log(numbers);

Answer:
  [1, 2, 4, 5]

Explanation: Arrays in JavaScript have a splice method that allows you to add or remove elements from an array at a specific index. In this case, the numbers array contains the elements [1, 2, 3, 4, 5], and when you use the splice method to remove 1 element at index 2, the array is updated to [1, 2, 4, 5].

### Problem 70: 
  const numbers = [1, 2, 3, 4, 5];
  numbers.splice(2, 1, 6);
  console.log(numbers);

Answer:
  [1, 2, 6, 4, 5]

Explanation: Arrays in JavaScript have a splice method that allows you to add or remove elements from an array at a specific index. In this case, the numbers array contains the elements [1, 2, 3, 4, 5], and when you use the splice method to remove 1 element at index 2 and add the value 6, the array is updated to [1, 2, 6, 4, 5].

### Problem 71: 
  const numbers = [1, 2, 3, 4, 5];
  const reversedNumbers = numbers.reverse();
  console.log(reversedNumbers);

Answer:
  [5, 4, 3, 2, 1]

Explanation: Arrays in JavaScript have a reverse method that allows you to reverse the order of elements in an array. In this case, the numbers array contains the elements [1, 2, 3, 4, 5], and when you use the reverse method to reverse the order of the elements, a new array with the reversed elements is returned.

### Problem 72: 
  const numbers = [1, 2, 3, 4, 5];
  const slicedNumbers = numbers.slice(1, 4);
  console.log(slicedNumbers);

Answer:
  [2, 3, 4]

Explanation: Arrays in JavaScript have a slice method that allows you to extract a portion of an array into a new array. In this case, the numbers array contains the elements [1, 2, 3, 4, 5], and when you use the slice method to extract the elements from index 1 to index 4 (not including index 4), a new array with the extracted elements is returned.

### Problem 73: 
  const numbers = [1, 2, 3, 4, 5];
  const sortedNumbers = numbers.sort();
  console.log(sortedNumbers);

Answer:
  [1, 2, 3, 4, 5]

Explanation: Arrays in JavaScript have a sort method that allows you to sort the elements of an array. In this case, the numbers array contains the elements [1, 2, 3, 4, 5], and when you use the sort method to sort the elements, the array is updated to [1, 2, 3, 4, 5].

### Problem 74: 
  const numbers = [1, 2, 3, 4, 5];
  const sortedNumbers = numbers.sort((a, b) => b - a);
  console.log(sortedNumbers);

Answer:
  [5, 4, 3, 2, 1]

Explanation: Arrays in JavaScript have a sort method that allows you to sort the elements of an array. By default, the sort method sorts elements as strings. In this case, the numbers array contains the elements [1, 2, 3, 4, 5], and when you use the sort method with a custom comparison function that sorts the elements in descending order, the array is updated to [5, 4, 3, 2, 1].

### Problem 75: 
  const numbers = [1, 2, 3, 4, 5];
  const sum = numbers.reduce((acc, curr) => acc + curr, 0);
  console.log(sum);

Answer:
  15

Explanation: Arrays in JavaScript have a reduce method that allows you to reduce an array to a single value. In this case, the numbers array contains the elements [1, 2, 3, 4, 5], and when you use the reduce method with an accumulator that sums the elements, the sum of the elements is returned.

### Problem 76: 
  const numbers = [1, 2, 3, 4, 5];
  const doubledNumbers = numbers.map((num) => num * 2);
  console.log(doubledNumbers);

Answer:
  [2, 4, 6, 8, 10]

Explanation: Arrays in JavaScript have a map method that allows you to transform each element of an array. In this case, the numbers array contains the elements [1, 2, 3, 4, 5], and when you use the map method to double each element, a new array with the doubled elements is returned.

### Problem 77: 
  const numbers = [1, 2, 3, 4, 5];
  const filteredNumbers = numbers.filter((num) => num % 2 === 0);
  console.log(filteredNumbers);

Answer:
  [2, 4]

Explanation: Arrays in JavaScript have a filter method that allows you to filter elements of an array based on a condition. In this case, the numbers array contains the elements [1, 2, 3, 4, 5], and when you use the filter method to filter out the even elements, a new array with the filtered elements is returned.

### Problem 78: 
  const numbers = [1, 2, 3, 4, 5];
  const includesThree = numbers.includes(3);
  console.log(includesThree);

Answer:
  true

Explanation: Arrays in JavaScript have an includes method that allows you to check if an array includes a specific element. In this case, the numbers array contains the elements [1, 2, 3, 4, 5], and when you use the includes method to check if the array includes the element 3, the value true is returned.

### Problem 79: 
  const numbers = [1, 2, 3, 4, 5];
  const indexOfThree = numbers.indexOf(3);
  console.log(indexOfThree);

Answer:
  2

Explanation: Arrays in JavaScript have an indexOf method that allows you to find the index of a specific element in an array. In this case, the numbers array contains the elements [1, 2, 3, 4, 5], and when you use the indexOf method to find the index of the element 3, the index 2 is returned.

### Problem 80: 
  const numbers = [1, 2, 3, 4, 5];
  const joinedNumbers = numbers.join('-');
  console.log(joinedNumbers);

Answer:
  1-2-3-4-5

Explanation: Arrays in JavaScript have a join method that allows you to join the elements of an array into a string. In this case, the numbers array contains the elements [1, 2, 3, 4, 5], and when you use the join method to join the elements with a hyphen separator, a string with the joined elements is returned.

### Problem 81: 
  const numbers = [1, 2, 3, 4, 5];
  const reversedNumbers = numbers.reverse();
  console.log(reversedNumbers);

Answer:
  [5, 4, 3, 2, 1]

Explanation: Arrays in JavaScript have a reverse method that allows you to reverse the order of elements in an array. In this case, the numbers array contains the elements [1, 2, 3, 4, 5], and when you use the reverse method to reverse the order of the elements, a new array with the reversed elements is returned.

### Problem 82: 
  const numbers = [1, 2, 3, 4, 5];
  const slicedNumbers = numbers.slice(1, 4);
  console.log(slicedNumbers);

Answer:
  [2, 3, 4]

Explanation: Arrays in JavaScript have a slice method that allows you to extract a portion of an array into a new array. In this case, the numbers array contains the elements [1, 2, 3, 4, 5], and when you use the slice method to extract the elements from index 1 to index 4 (not including index 4), a new array with the extracted elements is returned.

### Problem 83: 
  const numbers = [1, 2, 3, 4, 5];
  const sortedNumbers = numbers.sort();
  console.log(sortedNumbers);

Answer:
  [1, 2, 3, 4, 5]

Explanation: Arrays in JavaScript have a sort method that allows you to sort the elements of an array. In this case, the numbers array contains the elements [1, 2, 3, 4, 5], and when you use the sort method to sort the elements, the array is updated to [1, 2, 3, 4, 5].

### Problem 84: 
  const numbers = [1, 2, 3, 4, 5];
  const sortedNumbers = numbers.sort((a, b) => b - a);
  console.log(sortedNumbers);

Answer:
  [5, 4, 3, 2, 1]

Explanation: Arrays in JavaScript have a sort method that allows you to sort the elements of an array. By default, the sort method sorts elements as strings. In this case, the numbers array contains the elements [1, 2, 3, 4, 5], and when you use the sort method with a custom comparison function that sorts the elements in descending order, the array is updated to [5, 4, 3, 2, 1].

### Problem 85: 
  const numbers = [1, 2, 3, 4, 5];
  const sum = numbers.reduce((acc, curr) => acc + curr, 0);
  console.log(sum);

Answer:
  15

Explanation: Arrays in JavaScript have a reduce method that allows you to reduce an array to a single value. In this case, the numbers array contains the elements [1, 2, 3, 4, 5], and when you use the reduce method with an accumulator that sums the elements, the sum of the elements is returned.

### Problem 86: 
  const numbers = [1, 2, 3, 4, 5];
  const doubledNumbers = numbers.map((num) => num * 2);
  console.log(doubledNumbers);

Answer:
  [2, 4, 6, 8, 10]

Explanation: Arrays in JavaScript have a map method that allows you to transform each element of an array. In this case, the numbers array contains the elements [1, 2, 3, 4, 5], and when you use the map method to double each element, a new array with the doubled elements is returned.

### Problem 87: 
  const numbers = [1, 2, 3, 4, 5];
  const filteredNumbers = numbers.filter((num) => num % 2 === 0);
  console.log(filteredNumbers);

Answer:
  [2, 4]

Explanation: Arrays in JavaScript have a filter method that allows you to filter elements of an array based on a condition. In this case, the numbers array contains the elements [1, 2, 3, 4, 5], and when you use the filter method to filter out the even elements, a new array with the filtered elements is returned.

### Problem 88: 
  const numbers = [1, 2, 3, 4, 5];
  const includesThree = numbers.includes(3);
  console.log(includesThree);

Answer:
  true

Explanation: Arrays in JavaScript have an includes method that allows you to check if an array includes a specific element. In this case, the numbers array contains the elements [1, 2, 3, 4, 5], and when you use the includes method to check if the array includes the element 3, the value true is returned.

### Problem 89: 
  const numbers = [1, 2, 3, 4, 5];
  const indexOfThree = numbers.indexOf(3);
  console.log(indexOfThree);

Answer:
  2

Explanation: Arrays in JavaScript have an indexOf method that allows you to find the index of a specific element in an array. In this case, the numbers array contains the elements [1, 2, 3, 4, 5], and when you use the indexOf method to find the index of the element 3, the index 2 is returned.

### Problem 90: 
  const numbers = [1, 2, 3, 4, 5];
  const joinedNumbers = numbers.join('-');
  console.log(joinedNumbers);

Answer:
  1-2-3-4-5

Explanation: Arrays in JavaScript have a join method that allows you to join the elements of an array into a string. In this case, the numbers array contains the elements [1, 2, 3, 4, 5], and when you use the join method to join the elements with a hyphen separator, a string with the joined elements is returned.

### Problem 91: 
  const numbers = [1, 2, 3, 4, 5];
  const reversedNumbers = numbers.reverse();
  console.log(reversedNumbers);

Answer:
  [5, 4, 3, 2, 1]

Explanation: Arrays in JavaScript have a reverse method that allows you to reverse the order of elements in an array. In this case, the numbers array contains the elements [1, 2, 3, 4, 5], and when you use the reverse method to reverse the order of the elements, a new array with the reversed elements is returned.

### Problem 92: 
  const numbers = [1, 2, 3, 4, 5];
  const slicedNumbers = numbers.slice(1, 4);
  console.log(slicedNumbers);

Answer:
  [2, 3, 4]

Explanation: Arrays in JavaScript have a slice method that allows you to extract a portion of an array into a new array. In this case, the numbers array contains the elements [1, 2, 3, 4, 5], and when you use the slice method to extract the elements from index 1 to index 4 (not including index 4), a new array with the extracted elements is returned.

### Problem 93: 
  const numbers = [1, 2, 3, 4, 5];
  const sortedNumbers = numbers.sort();
  console.log(sortedNumbers);

Answer:
  [1, 2, 3, 4, 5]

Explanation: Arrays in JavaScript have a sort method that allows you to sort the elements of an array. In this case, the numbers array contains the elements [1, 2, 3, 4, 5], and when you use the sort method to sort the elements, the array is updated to [1, 2, 3, 4, 5].

### Problem 94: 
  const numbers = [1, 2, 3, 4, 5];
  const sortedNumbers = numbers.sort((a, b) => b - a);
  console.log(sortedNumbers);

Answer:
  [5, 4, 3, 2, 1]

Explanation: Arrays in JavaScript have a sort method that allows you to sort the elements of an array. By default, the sort method sorts elements as strings. In this case, the numbers array contains the elements [1, 2, 3, 4, 5], and when you use the sort method with a custom comparison function that sorts the elements in descending order, the array is updated to [5, 4, 3, 2, 1].

### Problem 95: 
  const numbers = [1, 2, 3, 4, 5];
  const sum = numbers.reduce((acc, curr) => acc + curr, 0);
  console.log(sum);

Answer:
  15

Explanation: Arrays in JavaScript have a reduce method that allows you to reduce an array to a single value. In this case, the numbers array contains the elements [1, 2, 3, 4, 5], and when you use the reduce method with an accumulator that sums the elements, the sum of the elements is returned.

### Problem 96: 
  const numbers = [1, 2, 3, 4, 5];
  const doubledNumbers = numbers.map((num) => num * 2);
  console.log(doubledNumbers);

Answer:
  [2, 4, 6, 8, 10]

Explanation: Arrays in JavaScript have a map method that allows you to transform each element of an array. In this case, the numbers array contains the elements [1, 2, 3, 4, 5], and when you use the map method to double each element, a new array with the doubled elements is returned.

### Problem 97: 
  const numbers = [1, 2, 3, 4, 5];
  const filteredNumbers = numbers.filter((num) => num % 2 === 0);
  console.log(filteredNumbers);

Answer:
  [2, 4]

Explanation: Arrays in JavaScript have a filter method that allows you to filter elements of an array based on a condition. In this case, the numbers array contains the elements [1, 2, 3, 4, 5], and when you use the filter method to filter out the even elements, a new array with the filtered elements is returned.

### Problem 98: 
  const numbers = [1, 2, 3, 4, 5];
  const includesThree = numbers.includes(3);
  console.log(includesThree);

Answer:
  true

Explanation: Arrays in JavaScript have an includes method that allows you to check if an array includes a specific element. In this case, the numbers array contains the elements [1, 2, 3, 4, 5], and when you use the includes method to check if the array includes the element 3, the value true is returned.

### Problem 99: 
  const numbers = [1, 2, 3, 4, 5];
  const indexOfThree = numbers.indexOf(3);
  console.log(indexOfThree);

Answer:
  2

Explanation: Arrays in JavaScript have an indexOf method that allows you to find the index of a specific element in an array. In this case, the numbers array contains the elements [1, 2, 3, 4, 5], and when you use the indexOf method to find the index of the element 3, the index 2 is returned.

### Problem 100: 
  const numbers = [1, 2, 3, 4, 5];
  const joinedNumbers = numbers.join('-');
  console.log(joinedNumbers);

Answer:
  1-2-3-4-5

Explanation: Arrays in JavaScript have a join method that allows you to join the elements of an array into a string. In this case, the numbers array contains the elements [1, 2, 3, 4, 5], and when you use the join method to join the elements with a hyphen separator, a string with the joined elements is returned.


## TOPIC: STRINGS

### Problem 101: 
  const str = 'Hello, World!';
  console.log(str[0]);

Answer:
  H

Explanation: Strings in JavaScript are zero-indexed, which means the first character of a string has an index of 0. In this case, the str string contains the text 'Hello, World!', and when you access the character at index 0, the character 'H' is logged to the console.

### Problem 102: 
  const str = 'Hello, World!';
  console.log(str[12]);

Answer:
  !

Explanation: Strings in JavaScript are zero-indexed, which means the first character of a string has an index of 0. In this case, the str string contains the text 'Hello, World!', and when you access the character at index 12, which is beyond the length of the string, the character '!' is logged to the console.

### Problem 103: 
  const str = 'Hello, World!';
  console.log(str.length);

Answer:
  13

Explanation: Strings in JavaScript have a length property that returns the number of characters in the string. In this case, the str string contains the text 'Hello, World!', which has 13 characters, and when you access the length property of the string, the value 13 is logged to the console.

### Problem 104: 
  const str = 'Hello, World!';
  console.log(str.toUpperCase());

Answer:
  HELLO, WORLD!
  
Explanation: Strings in JavaScript have built-in methods that allow you to manipulate the text. In this case, the str string contains the text 'Hello, World!', and when you use the toUpperCase method to convert the text to uppercase, the uppercase version of the text is returned.

### Problem 105: 
  const str = 'Hello, World!';
  console.log(str.toLowerCase());

Answer:
  hello, world!

Explanation: Strings in JavaScript have built-in methods that allow you to manipulate the text. In this case, the str string contains the text 'Hello, World!', and when you use the toLowerCase method to convert the text to lowercase, the lowercase version of the text is returned.

### Problem 106: 
  const str = 'Hello, World!';
  console.log(str.split(','));

Answer:
  ['Hello', ' World!']

Explanation: Strings in JavaScript have a split method that allows you to split a string into an array of substrings based on a separator. In this case, the str string contains the text 'Hello, World!', and when you use the split method with a comma separator, an array with the substrings ['Hello', ' World!'] is returned.

### Problem 107: 
  const str = 'Hello, World!';
  console.log(str.replace('Hello', 'Hi'));

Answer:
  Hi, World!

Explanation: Strings in JavaScript have a replace method that allows you to replace a substring with another substring. In this case, the str string contains the text 'Hello, World!', and when you use the replace method to replace the substring 'Hello' with 'Hi', the text 'Hi, World!' is returned.

### Problem 108: 
  const str = 'Hello, World!';
  console.log(str.includes('World'));

Answer:
  true

Explanation: Strings in JavaScript have an includes method that allows you to check if a string includes a specific substring. In this case, the str string contains the text 'Hello, World!', and when you use the includes method to check if the string includes the substring 'World', the value true is returned.

### Problem 109: 
  const str = 'Hello, World!';
  console.log(str.indexOf('World'));

Answer:
  7

Explanation: Strings in JavaScript have an indexOf method that allows you to find the index of a specific substring in a string. In this case, the str string contains the text 'Hello, World!', and when you use the indexOf method to find the index of the substring 'World', the index 7 is returned.

### Problem 110: 
  const str = 'Hello, World!';
  console.log(str.slice(7));

Answer:
  World!

Explanation: Strings in JavaScript have a slice method that allows you to extract a portion of a string. In this case, the str string contains the text 'Hello, World!', and when you use the slice method with a starting index of 7, the substring 'World!' is returned.

### Problem 111: 
  const str = 'Hello, World!';
  console.log(str.substring(7));

Answer:
  World!
  
Explanation: Strings in JavaScript have a substring method that allows you to extract a portion of a string. In this case, the str string contains the text 'Hello, World!', and when you use the substring method with a starting index of 7, the substring 'World!' is returned.

### Problem 112: 
  const str = 'Hello, World!';
  console.log(str.substr(7));

Answer:
  World!

Explanation: Strings in JavaScript have a substr method that allows you to extract a portion of a string. In this case, the str string contains the text 'Hello, World!', and when you use the substr method with a starting index of 7, the substring 'World!' is returned.

### Problem 113: 
  const str = 'Hello, World!';
  console.log(str.split(''));

Answer:
  ['H', 'e', 'l', 'l', 'o', ',', ' ', 'W', 'o', 'r', 'l', 'd', '!']

Explanation: Strings in JavaScript have a split method that allows you to split a string into an array of substrings based on a separator. In this case, the str string contains the text 'Hello, World!', and when you use the split method with an empty string separator, an array with the individual characters of the string is returned.


## TOPIC: NUMBERS

### Problem 114: 
  const num = 42;
  console.log(num.toString());

Answer:
  42

Explanation: Numbers in JavaScript have a toString method that allows you to convert a number to a string. In this case, the num variable contains the number 42, and when you use the toString method, the number is converted to the string '42'.

### Problem 115: 
  const num = 42;
  console.log(num.toFixed(2));

Answer:
  42.00
  
Explanation: Numbers in JavaScript have a toFixed method that allows you to format a number with a specific number of decimal places. In this case, the num variable contains the number 42, and when you use the toFixed method with 2 decimal places, the number is formatted as '42.00'.

### Problem 116: 
  const num = 42.12345;
  console.log(num.toFixed(2));

Answer:
  42.12

Explanation: Numbers in JavaScript have a toFixed method that allows you to format a number with a specific number of decimal places. In this case, the num variable contains the number 42.12345, and when you use the toFixed method with 2 decimal places, the number is formatted as '42.12'.

### Problem 117: 
  const num = 42;
  console.log(num.toPrecision(3));

Answer:
  42.0

Explanation: Numbers in JavaScript have a toPrecision method that allows you to format a number with a specific number of significant digits. In this case, the num variable contains the number 42, and when you use the toPrecision method with 3 significant digits, the number is formatted as '42.0'.


## TOPIC: BOOLEANS

### Problem 118: 
  const bool = true;
  console.log(bool.toString());

Answer:
  true

Explanation: Booleans in JavaScript have a toString method that allows you to convert a boolean to a string. In this case, the bool variable contains the boolean value true, and when you use the toString method, the boolean is converted to the string 'true'.

### Problem 119: 
  const bool = true;
  console.log(bool.valueOf());

Answer:
  true

Explanation: Booleans in JavaScript have a valueOf method that allows you to get the primitive value of a boolean. In this case, the bool variable contains the boolean value true, and when you use the valueOf method, the boolean value true is returned.


## TOPIC: FUNCTIONS

### Problem 120: 
  function add(a, b) {
    return a + b;
  }
  console.log(add(2, 3));

Answer:
  5

Explanation: Functions in JavaScript allow you to define reusable blocks of code. In this case, the add function takes two parameters a and b, and returns the sum of the two parameters. When you call the add function with the arguments 2 and 3, the sum 5 is returned.

### Problem 121: 
  const add = function(a, b) {
    return a + b;
  };
  console.log(add(2, 3));

Answer:
  5

Explanation: Functions in JavaScript can be assigned to variables. In this case, the add variable is assigned a function expression that takes two parameters a and b, and returns the sum of the two parameters. When you call the add function with the arguments 2 and 3, the sum 5 is returned.

### Problem 122: 
  const add = (a, b) => a + b;
  console.log(add(2, 3));

Answer:
  5

Explanation: Arrow functions in JavaScript provide a concise syntax for defining functions. In this case, the add arrow function takes two parameters a and b, and returns the sum of the two parameters. When you call the add function with the arguments 2 and 3, the sum 5 is returned.

### Problem 123: 
  const add = (a, b) => {
    return a + b;
  };
  console.log(add(2, 3));

Answer:
  5

Explanation: Arrow functions in JavaScript provide a concise syntax for defining functions. In this case, the add arrow function takes two parameters a and b, and returns the sum of the two parameters. When you call the add function with the arguments 2 and 3, the sum 5 is returned.

### Problem 124: 
  const add = (a, b) => {
    const sum = a + b;
    return sum;
  };
  console.log(add(2, 3));

Answer:
  5

Explanation: Arrow functions in JavaScript provide a concise syntax for defining functions. In this case, the add arrow function takes two parameters a and b, calculates the sum of the two parameters, and returns the sum. When you call the add function with the arguments 2 and 3, the sum 5 is returned.

### Problem 125: 
  const add = (a, b) => a + b;
  console.log(add(2, 3));

Answer:
  5

Explanation: Arrow functions in JavaScript provide a concise syntax for defining functions. In this case, the add arrow function takes two parameters a and b, and returns the sum of the two parameters. When you call the add function with the arguments 2 and 3, the sum 5 is returned.

### Problem 126: 
  const add = (a, b) => a + b;
  console.log(add(2, 3));

Answer:
  5

Explanation: Arrow functions in JavaScript provide a concise syntax for defining functions. In this case, the add arrow function takes two parameters a and b, and returns the sum of the two parameters. When you call the add function with the arguments 2 and 3, the sum 5 is returned.

### Problem 127: 
  const add = (a, b) => a + b;
  console.log(add(2, 3));

Answer:
  5

Explanation: Arrow functions in JavaScript provide a concise syntax for defining functions. In this case, the add arrow function takes two parameters a and b, and returns the sum of the two parameters. When you call the add function with the arguments 2 and 3, the sum 5 is returned.



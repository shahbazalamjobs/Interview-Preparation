



### Function Basics

1. **What is a function in JavaScript?**
   - A function in JavaScript is a reusable block of code that performs a specific task. It can accept inputs (parameters), execute statements, and return a value.

2. **How do you declare a function? Provide examples of different ways.**
   - Function Declaration:
   ```javascript
   function greet(name) {
       return `Hello, ${name}!`;
   }
   ```

   - Function Expression:
   ```javascript
   const greet = function(name) {
       return `Hello, ${name}!`;
   };
   ```

   - Arrow Function (ES6):
   ```javascript
   const greet = name => `Hello, ${name}!`;
   ```

3. **Explain the difference between function declarations and function expressions.**
   - Function Declaration is hoisted and can be used before its declaration in the code.
   - Function Expression is not hoisted and must be defined before it is used.

4. **What is the purpose of the return statement in a function?**
   - The `return` statement specifies the value that the function should return when called. It also exits the function execution.

**Function Parameters and Arguments:**

5. **How do you pass parameters to a function?**
   - Parameters are declared in the function's parentheses and are used to accept values when the function is called.
   ```javascript
   function greet(name) {
       return `Hello, ${name}!`;
   }
   ```

6. **What are default parameters in a function?**
   - Default parameters provide values to function parameters if no value or `undefined` is provided during the function call.
   ```javascript
   function greet(name = "Guest") {
       return `Hello, ${name}!`;
   }
   ```

7. **Explain the concept of rest parameters and provide an example.**
   - Rest parameters allow a function to accept an arbitrary number of arguments as an array.
   ```javascript
   function sum(...numbers) {
       return numbers.reduce((total, num) => total + num, 0);
   }
   ```

### Function Scope:

8. **Describe the difference between global scope and local scope.**
   - Global scope refers to variables accessible throughout the entire program.
   - Local scope (function scope) refers to variables accessible only within the function where they are declared.

9. **What is variable shadowing, and how does it occur?**
   - Variable shadowing occurs when a variable declared in a local scope has the same name as a variable in an outer scope, causing the inner variable to "shadow" the outer one.

10. **How can you access a variable from an outer (enclosing) function in an inner (nested) function?**
    - Inner functions have access to variables in their outer functions due to closure.
    ```javascript
    function outer() {
        const outerVar = "Outer";
        function inner() {
            console.log(outerVar); // Access outerVar from outer function
        }
        inner();
    }
    ```

### Closures:

11. **Define a closure and explain its practical use.**
    - A closure is a function that retains access to its outer function's variables even after the outer function has finished executing.
    - Practical use: Creating private variables, maintaining state, and implementing data encapsulation.

12. **How does a closure retain access to its outer function's variables even after the outer function has finished executing?**
    - Closures retain access to outer function variables through lexical scoping, capturing references to those variables even after the outer function has completed.

13. **Provide an example of a closure being used to create private variables.**
    ```javascript
    function createCounter() {
        let count = 0;
        return function() {
            return ++count;
        };
    }
    const counter = createCounter();
    console.log(counter()); // Output: 1
    ```

### Higher-Order Functions:

14. **What is a higher-order function? Provide an example.**
    - A higher-order function is a function that either accepts other functions as arguments or returns a function.
    ```javascript
    function higherOrder(func) {
        return func();
    }
    ```

15. **Explain how you can pass functions as arguments to other functions.**
    - Functions can be passed as arguments just like any other value.
    ```javascript
    function greet(name) {
        return `Hello, ${name}!`;
    }
    function processGreeting(func, name) {
        return func(name);
    }
    ```

16. **Describe the map, filter, and reduce functions and provide use cases.**
    - `map`: Transforms each element of an array and returns a new array with transformed values.
    - `filter`: Creates a new array containing elements that pass a specified condition.
    - `reduce`: Accumulates elements of an array into a single value through a provided function.

    ```javascript
    const numbers = [1, 2, 3, 4, 5];
    const doubled = numbers.map(num => num * 2);            // [2, 4, 6, 8, 10]
    const evens = numbers.filter(num => num % 2 === 0);     // [2, 4]
    const sum = numbers.reduce((acc, num) => acc + num, 0); // 15
    ```

### Callback Functions:

17. **What is a callback function? How is it used in JavaScript?**
    - A callback function is a function passed as an argument to another function, which is then invoked later, often in response to an event or condition.

18. **Explain the concept of a callback hell and how you can avoid it.**
    - Callback hell occurs when multiple nested callbacks make code hard to read. It can be avoided using modularization, named functions, Promises, or async/await.

19. **Provide an example of using a callback function to handle asynchronous operations.**
    ```javascript
    function fetchData(url, callback) {
        setTimeout(() => {
            const data = "Data from " + url;
            callback(data);
        }, 1000);
    }
    fetchData("https://example.com", (data) => {
        console.log(data); // Output: "Data from https://example.com"
    });
    ```

### Arrow Functions:

20. **What are arrow functions, and how do they differ from regular functions?**
    - Arrow functions are a concise way to write functions in ES6, with a shorter syntax.
    - They do not have their own `this` context and are not suitable for all scenarios, such as as methods or constructors.

21. **Describe scenarios where arrow functions may not be suitable.**
    - Arrow functions should not be used as methods in objects since they don't bind their own `this`.
    - They also cannot be used as constructors.

### Lexical Scope and this:

22. **How does lexical scoping affect the value of `this` in JavaScript?**
    - Lexical scoping preserves the value of `this` based on where a function is defined, not where it is called.

23. **What is the purpose of the `bind`, `call`, and `apply` methods in relation to `this`?**
    - These methods allow you to control the value of `this` within a function:
    ```javascript
    const person = {
        name: "Alice",
        greet: function() {
            console.log(`Hello, ${this.name}!`);
        }
    };
    const greetFunc = person.greet.bind(person);
    greetFunc(); // Output: "Hello, Alice!"
    ```

### Immediately Invoked Function Expressions (IIFE):

24. **What is an IIFE, and why would you use it?**
    - An IIFE is a function that is executed immediately after it's defined. It is often used to create a private scope and avoid polluting the global scope.

25. **Provide an example of creating and invoking an IIFE.**
    ```javascript
    (function() {
        const message = "Hello from IIFE!";
        console.log(message);
    })(); // Output: "Hello from IIFE!"
    ```

### Recursion:

26. **What is recursion? Provide an example of a recursive function.**
    - Recursion is a technique where a function calls itself to solve a problem.
    ```javascript
    function factorial(n) {
        if (n <= 1) {    // Base case
            return 1;
        }
        return n * factorial(n - 1);
    }
    console.log(factorial(5)); // Output: 120
    ```

27. **Explain the concept of a base case in recursive functions.**
    - A base case is a condition that terminates the recursive process. Without it, the function would infinitely call itself.

Sure! Here are detailed explanations with code examples for the Module Pattern and Async Functions:

**Module Pattern:**

1. **Describe the module pattern in JavaScript:**
   - The module pattern is a design pattern in JavaScript that provides a way to encapsulate and organize code by creating self-contained modules. It uses closures to create private and public members, allowing for better code organization and avoiding global namespace pollution.

2. **How does the module pattern help with encapsulation and avoiding global namespace pollution?**
   - Encapsulation: The module pattern creates private members (variables and functions) that are not accessible from the outside, ensuring data privacy and preventing unintended modifications.
   - Namespace Pollution: By encapsulating functionality within modules, the module pattern avoids polluting the global namespace, reducing the risk of naming conflicts.

**Example of Module Pattern:**

```javascript
const CounterModule = (function() {
    let count = 0; // Private variable
    
    function increment() {
        count++;
    }
    
    function getCount() {
        return count;
    }
    
    return {
        increment: increment, // Public method
        getCount: getCount    // Public method
    };
})();

console.log(CounterModule.getCount()); // Output: 0
CounterModule.increment();
console.log(CounterModule.getCount()); // Output: 1
```

### Async Functions:

1. **What are async functions?**
   - Async functions are a feature introduced in ECMAScript 2017 (ES8) that make working with asynchronous operations, such as Promises, easier and more readable. They allow you to write asynchronous code in a synchronous-like manner.

2. **How do they relate to promises and async/await?**
   - Async functions use the `async` keyword before the function declaration and implicitly return a Promise. They can contain the `await` keyword, which pauses the execution of the function until the Promise is resolved, making the code appear more linear and readable.

**Example of Async Function:**

```javascript
function fetchUser(id) {
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            const users = [
                { id: 1, name: "Alice" },
                { id: 2, name: "Bob" }
            ];
            const user = users.find(user => user.id === id);
            if (user) {
                resolve(user);
            } else {
                reject("User not found");
            }
        }, 1000);
    });
}

async function getUserInfo(id) {
    try {
        const user = await fetchUser(id);
        console.log(`User ID: ${user.id}, Name: ${user.name}`);
    } catch (error) {
        console.error(error);
    }
}

getUserInfo(1);
```

In the example above, the `getUserInfo` function is an async function that awaits the `fetchUser` Promise. This makes the asynchronous code read like synchronous code, improving code readability and maintainability.


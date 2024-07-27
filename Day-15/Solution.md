#### Activity 1: Understanding Closures

**Task 1: Write a function that returns another function, where the inner function accesses a variable from the outer function's scope. Call the inner function and log the result.**
```javascript
function outerFunction() {
    let outerVariable = 'I am from outer scope';

    function innerFunction() {
        console.log(outerVariable);
    }

    return innerFunction;
}

const inner = outerFunction();
inner(); // Output: I am from outer scope
```

**Task 2: Create a closure that maintains a private counter. Implement functions to increment and get the current value of the counter.**
```javascript
function createCounter() {
    let counter = 0;

    return {
        increment: function() {
            counter++;
        },
        getValue: function() {
            return counter;
        }
    };
}

const counter = createCounter();
counter.increment();
console.log(counter.getValue()); // Output: 1
counter.increment();
console.log(counter.getValue()); // Output: 2
```

#### Activity 2: Practical Closures

**Task 3: Write a function that generates unique IDs. Use a closure to keep track of the last generated ID and increment it with each call.**
```javascript
function createIDGenerator() {
    let lastID = 0;

    return function() {
        lastID++;
        return lastID;
    };
}

const generateID = createIDGenerator();
console.log(generateID()); // Output: 1
console.log(generateID()); // Output: 2
console.log(generateID()); // Output: 3
```

**Task 4: Create a closure that captures a user's name and returns a function that greets the user by name.**
```javascript
function createGreeting(name) {
    return function() {
        console.log(`Hello, ${name}!`);
    };
}

const greetJohn = createGreeting('John');
greetJohn(); // Output: Hello, John!
const greetJane = createGreeting('Jane');
greetJane(); // Output: Hello, Jane!
```

#### Activity 3: Closures in Loops

**Task 5: Write a loop that creates an array of functions. Each function should log its index when called. Use a closure to ensure each function logs the correct index.**
```javascript
function createFunctionArray() {
    let functionArray = [];

    for (let i = 0; i < 5; i++) {
        functionArray.push(function() {
            console.log(i);
        });
    }

    return functionArray;
}

const functions = createFunctionArray();
functions[0](); // Output: 0
functions[1](); // Output: 1
functions[2](); // Output: 2
functions[3](); // Output: 3
functions[4](); // Output: 4
```

#### Activity 4: Module Pattern

**Task 6: Use closures to create a simple module for managing a collection of items. Implement methods to add, remove, and list items.**
```javascript
const itemManager = (function() {
    let items = [];

    return {
        addItem: function(item) {
            items.push(item);
        },
        removeItem: function(item) {
            items = items.filter(i => i !== item);
        },
        listItems: function() {
            return items;
        }
    };
})();

itemManager.addItem('Item1');
itemManager.addItem('Item2');
console.log(itemManager.listItems()); // Output: ['Item1', 'Item2']
itemManager.removeItem('Item1');
console.log(itemManager.listItems()); // Output: ['Item2']
```

#### Activity 5: Memoization

**Task 7: Write a function that memoizes the results of another function. Use a closure to store the results of previous computations.**
```javascript
function memoize(fn) {
    const cache = {};

    return function(...args) {
        const key = JSON.stringify(args);
        if (cache[key]) {
            return cache[key];
        } else {
            const result = fn(...args);
            cache[key] = result;
            return result;
        }
    };
}

const add = (a, b) => a + b;
const memoizedAdd = memoize(add);

console.log(memoizedAdd(1, 2)); // Output: 3
console.log(memoizedAdd(1, 2)); // Output: 3 (cached result)
console.log(memoizedAdd(2, 3)); // Output: 5
```

**Task 8: Create a memoized version of a function that calculates the factorial of a number.**
```javascript
function factorial(n) {
    if (n === 0) return 1;
    return n * factorial(n - 1);
}

const memoizedFactorial = memoize(factorial);

console.log(memoizedFactorial(5)); // Output: 120
console.log(memoizedFactorial(5)); // Output: 120 (cached result)
console.log(memoizedFactorial(6)); // Output: 720
```

### Thats it for today

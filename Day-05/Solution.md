### Day 5: Functions

### Activity 1: Function Declaration

#### Task 1: Write a function to check if a number is even or odd and log the result to the console.
```javascript
function checkEvenOdd(number) {
    if (number % 2 === 0) {
        console.log(`${number} is even`);
    } else {
        console.log(`${number} is odd`);
    }
}
checkEvenOdd(5);  // Output: 5 is odd
```

#### Task 2: Write a function to calculate the square of a number and return the result.
```javascript
function square(number) {
    return number * number;
}
console.log(square(5));  // Output: 25
```

### Activity 2: Function Expression

#### Task 3: Write a function expression to find the maximum of two numbers and log the result to the console.
```javascript
const maxOfTwo = function(a, b) {
    return a > b ? a : b;
};
console.log(maxOfTwo(5, 10));  // Output: 10
```

#### Task 4: Write a function expression to concatenate two strings and return the result.
```javascript
const concatenateStrings = function(str1, str2) {
    return str1 + str2;
};
console.log(concatenateStrings('Hello, ', 'world!'));  // Output: Hello, world!
```

### Activity 3: Arrow Functions

#### Task 5: Write an arrow function to calculate the sum of two numbers and return the result.
```javascript
const sum = (a, b) => a + b;
console.log(sum(5, 10));  // Output: 15
```

#### Task 6: Write an arrow function to check if a string contains a specific character and return a boolean value.
```javascript
const containsCharacter = (str, char) => str.includes(char);
console.log(containsCharacter('Hello, world!', 'o'));  // Output: true
```

### Activity 4: Function Parameters and Default Values

#### Task 7: Write a function that takes two parameters and returns their product. Provide a default value for the second parameter.
```javascript
function multiply(a, b = 1) {
    return a * b;
}
console.log(multiply(5, 2));  // Output: 10
console.log(multiply(5));     // Output: 5
```

#### Task 8: Write a function that takes a person's name and age and returns a greeting message. Provide a default value for the age.
```javascript
function greet(name, age = 30) {
    return `Hello, ${name}! You are ${age} years old.`;
}
console.log(greet('Alice', 25));  // Output: Hello, Alice! You are 25 years old.
console.log(greet('Bob'));        // Output: Hello, Bob! You are 30 years old.
```

### Activity 5: Higher-Order Functions

#### Task 9: Write a higher-order function that takes a function and a number, and calls the function that many times.
```javascript
function repeatFunction(fn, times) {
    for (let i = 0; i < times; i++) {
        fn();
    }
}
repeatFunction(() => console.log('Hello!'), 3);
// Output:
// Hello!
// Hello!
// Hello!
```

#### Task 10: Write a higher-order function that takes two functions and a value, applies the first function to the value, and then applies the second function to the result.
```javascript
function composeFunctions(fn1, fn2, value) {
    return fn2(fn1(value));
}
const double = x => x * 2;
const square = x => x * x;
console.log(composeFunctions(double, square, 5));  // Output: 100
```

### Feature Requests

1. **Even or Odd Function Script**: Write a script that includes a function to check if a number is even or odd and logs the result.
```javascript
function checkEvenOdd(number) {
    if (number % 2 === 0) {
        console.log(`${number} is even`);
    } else {
        console.log(`${number} is odd`);
    }
}
checkEvenOdd(7);  // Output: 7 is odd
```

2. **Square Calculation Function Script**: Create a script that includes a function to calculate the square of a number and returns the result.
```javascript
function square(number) {
    return number * number;
}
console.log(square(8));  // Output: 64
```

3. **Concatenation Function Script**: Write a script that includes a function expression to concatenate two strings and returns the result.
```javascript
const concatenateStrings = function(str1, str2) {
    return str1 + str2;
};
console.log(concatenateStrings('Good ', 'morning!'));  // Output: Good morning!
```

4. **Sum Calculation Arrow Function Script**: Create a script that includes an arrow function to calculate the sum of two numbers and returns the result.
```javascript
const sum = (a, b) => a + b;
console.log(sum(12, 8));  // Output: 20
```

5. **Higher-Order Function Script**: Write a script that includes a higher-order function to apply a given function multiple times.
```javascript
function repeatFunction(fn, times) {
    for (let i = 0; i < times; i++) {
        fn();
    }
}
repeatFunction(() => console.log('Hi!'), 5);
// Output:
// Hi!
// Hi!
// Hi!
// Hi!
// Hi!
```

Thats it for today

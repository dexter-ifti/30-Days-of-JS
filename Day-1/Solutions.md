

### Task 1: Declare a variable using `var`, assign it a number, and log the value to the console.
In JavaScript, you can declare a variable using `var` and assign a number to it. Here's an example:

```javascript
var numberVariable = 10;
console.log(numberVariable);  // This will log 10 to the console
```

### Task 2: Declare a variable using `let`, assign it a string, and log the value to the console.
Similarly, you can declare a variable using `let` and assign a string to it. Here's an example:

```javascript
let stringVariable = "Hello, world!";
console.log(stringVariable);  // This will log "Hello, world!" to the console
```

### Task 3: Declare a variable using `const`, assign it a boolean value, and log the value to the console.
You can declare a variable using `const` and assign a boolean value to it. Here's an example:

```javascript
const booleanVariable = true;
console.log(booleanVariable);  // This will log true to the console
```

### Task 4: Create variables of different data types (number, string, boolean, object, array) and log each variable's type using the `typeof` operator.
You can create variables of various data types and use the `typeof` operator to log their types. Here's an example:

```javascript
let numberVar = 42;
let stringVar = "JavaScript";
let booleanVar = false;
let objectVar = { name: "John", age: 30 };
let arrayVar = [1, 2, 3];

console.log(typeof numberVar);  // number
console.log(typeof stringVar);  // string
console.log(typeof booleanVar); // boolean
console.log(typeof objectVar);  // object
console.log(typeof arrayVar);   // object (arrays are a type of object in JavaScript)
```

### Task 5: Declare a variable using `let`, assign it an initial value, reassign a new value, and log both values to the console.
Variables declared with `let` can be reassigned. Here's an example:

```javascript
let reassignVar = "initial value";
console.log(reassignVar);  // This will log "initial value" to the console

reassignVar = "new value";
console.log(reassignVar);  // This will log "new value" to the console
```

### Task 6: Try reassigning a variable declared with `const` and observe the error.
Variables declared with `const` cannot be reassigned. Trying to do so will result in an error. Here's an example:

```javascript
const immutableVar = "initial value";
console.log(immutableVar);  // This will log "initial value" to the console

// Trying to reassign the variable will result in an error
immutableVar = "new value";  // This will cause an error
```

### Feature Requests

1. **Variable Types Console Log**: Write a script that declares variables of different data types and logs both the value and type of each variable to the console.
```javascript
let numberVar = 100;
let stringVar = "Learning JavaScript";
let booleanVar = true;
let objectVar = { language: "JavaScript", level: "beginner" };
let arrayVar = ["var", "let", "const"];

console.log(numberVar, typeof numberVar);
console.log(stringVar, typeof stringVar);
console.log(booleanVar, typeof booleanVar);
console.log(objectVar, typeof objectVar);
console.log(arrayVar, typeof arrayVar);
```

2. **Reassignment Demo**: Create a script that demonstrates the difference in behavior between `let` and `const` when it comes to reassignment.
```javascript
// Using let
let reassignableVar = "original value";
console.log(reassignableVar);  // Logs "original value"

reassignableVar = "new value";
console.log(reassignableVar);  // Logs "new value"

// Using const
const immutableVar = "original value";
console.log(immutableVar);  // Logs "original value"

// Trying to reassign a const variable will cause an error
try {
  immutableVar = "new value";  // This will cause an error
} catch (error) {
  console.log(error.message);  // Logs the error message
}
```

By following these examples, you should be able to complete the tasks and understand the concepts outlined in your document. Let me know if you need further explanation or assistance!

### Day 8: ES6+ Features

### Activity 1: Template Literals

#### Task 1: Use template literals to create a string that includes variables for a person's name and age, and log the string to the console.
```javascript
let name = "John";
let age = 30;
let greeting = `Hello, my name is ${name} and I am ${age} years old.`;
console.log(greeting);
// Output: Hello, my name is John and I am 30 years old.
```

#### Task 2: Create a multi-line string using template literals and log it to the console.
```javascript
let multilineString = `This is a string
that spans across
multiple lines.`;
console.log(multilineString);
// Output:
// This is a string
// that spans across
// multiple lines.
```

### Activity 2: Destructuring

#### Task 3: Use array destructuring to extract the first and second elements from an array of numbers and log them to the console.
```javascript
let numbers = [1, 2, 3, 4, 5];
let [first, second] = numbers;
console.log(first, second);  // Output: 1 2
```

#### Task 4: Use object destructuring to extract the title and author from a book object and log them to the console.
```javascript
let book = {
    title: "1984",
    author: "George Orwell",
    year: 1949
};
let { title, author } = book;
console.log(title, author);  // Output: 1984 George Orwell
```

### Activity 3: Spread and Rest Operators

#### Task 5: Use the spread operator to create a new array that includes all elements of an existing array plus additional elements, and log the new array to the console.
```javascript
let originalArray = [1, 2, 3];
let newArray = [...originalArray, 4, 5];
console.log(newArray);  // Output: [1, 2, 3, 4, 5]
```

#### Task 6: Use the rest operator in a function to accept an arbitrary number of arguments, sum them, and return the result.
```javascript
function sum(...numbers) {
    return numbers.reduce((total, num) => total + num, 0);
}
console.log(sum(1, 2, 3));  // Output: 6
console.log(sum(4, 5, 6, 7));  // Output: 22
```

### Activity 4: Default Parameters

#### Task 7: Write a function that takes two parameters and returns their product, with the second parameter having a default value of 1. Log the result of calling this function with and without the second parameter.
```javascript
function multiply(a, b = 1) {
    return a * b;
}
console.log(multiply(5));  // Output: 5
console.log(multiply(5, 2));  // Output: 10
```

### Activity 5: Enhanced Object Literals

#### Task 8: Use enhanced object literals to create an object with methods and properties, and log the object to the console.
```javascript
let person = {
    name: "Alice",
    age: 25,
    greet() {
        return `Hello, my name is ${this.name} and I am ${this.age} years old.`;
    }
};
console.log(person);
console.log(person.greet());
// Output:
// { name: 'Alice', age: 25, greet: [Function: greet] }
// Hello, my name is Alice and I am 25 years old.
```

#### Task 9: Create an object with computed property names based on variables and log the object to the console.
```javascript
let propName = "age";
let user = {
    name: "Bob",
    [propName]: 30
};
console.log(user);
// Output: { name: 'Bob', age: 30 }
```

### Feature Requests

1. **Template Literals Script**: Write a script that demonstrates the use of template literals to create and log strings with embedded variables and multi-line strings.
```javascript
let firstName = "Emma";
let lastName = "Stone";
let fullName = `${firstName} ${lastName}`;
let address = `123 Main St
Springfield, USA`;

console.log(fullName);  // Output: Emma Stone
console.log(address);
// Output:
// 123 Main St
// Springfield, USA
```

2. **Destructuring Script**: Create a script that uses array and object destructuring to extract values and log them.
```javascript
let fruits = ["Apple", "Banana", "Cherry"];
let [firstFruit, secondFruit] = fruits;
console.log(firstFruit, secondFruit);  // Output: Apple Banana

let car = {
    make: "Toyota",
    model: "Corolla",
    year: 2020
};
let { make, model } = car;
console.log(make, model);  // Output: Toyota Corolla
```

3. **Spread and Rest Operators Script**: Write a script that demonstrates the use of the spread operator to combine arrays and the rest operator to handle multiple function arguments.
```javascript
let arr1 = [1, 2, 3];
let arr2 = [4, 5, 6];
let combinedArray = [...arr1, ...arr2];
console.log(combinedArray);  // Output: [1, 2, 3, 4, 5, 6]

function multiply(...nums) {
    return nums.reduce((product, num) => product * num, 1);
}
console.log(multiply(2, 3, 4));  // Output: 24
```

4. **Default Parameters Script**: Create a script that defines a function with default parameters and logs the results of calling it with different arguments.
```javascript
function greet(name, greeting = "Hello") {
    return `${greeting}, ${name}!`;
}
console.log(greet("Alice"));  // Output: Hello, Alice!
console.log(greet("Bob", "Hi"));  // Output: Hi, Bob!
```

5. **Enhanced Object Literals Script**: Write a script that uses enhanced object literals to create and log an object with methods and computed property names.
```javascript
let key = "status";
let task = {
    description: "Complete the project",
    completed: false,
    [key]: "In Progress",
    toggleStatus() {
        this.completed = !this.completed;
        this.status = this.completed ? "Completed" : "In Progress";
    }
};
console.log(task);
// Output: { description: 'Complete the project', completed: false, status: 'In Progress', toggleStatus: [Function: toggleStatus] }

task.toggleStatus();
console.log(task);
// Output: { description: 'Complete the project', completed: true, status: 'Completed', toggleStatus: [Function: toggleStatus] }
```

Thats it for today

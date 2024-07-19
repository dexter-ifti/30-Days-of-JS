### Day 6: Arrays

Let's go through each task step by step:

### Activity 1: Array Creation and Access

#### Task 1: Create an array of numbers from 1 to 5 and log the array to the console.
```javascript
let array = [1, 2, 3, 4, 5];
console.log(array);  // Output: [1, 2, 3, 4, 5]
```

#### Task 2: Access the first and last elements of the array and log them to the console.
```javascript
console.log(array[0]);  // Output: 1
console.log(array[array.length - 1]);  // Output: 5
```

### Activity 2: Array Methods (Basic)

#### Task 3: Use the `push` method to add a new number to the end of the array and log the updated array.
```javascript
array.push(6);
console.log(array);  // Output: [1, 2, 3, 4, 5, 6]
```

#### Task 4: Use the `pop` method to remove the last element from the array and log the updated array.
```javascript
array.pop();
console.log(array);  // Output: [1, 2, 3, 4, 5]
```

#### Task 5: Use the `shift` method to remove the first element from the array and log the updated array.
```javascript
array.shift();
console.log(array);  // Output: [2, 3, 4, 5]
```

#### Task 6: Use the `unshift` method to add a new number to the beginning of the array and log the updated array.
```javascript
array.unshift(1);
console.log(array);  // Output: [1, 2, 3, 4, 5]
```

### Activity 3: Array Methods (Intermediate)

#### Task 7: Use the `map` method to create a new array where each number is doubled and log the new array.
```javascript
let doubledArray = array.map(num => num * 2);
console.log(doubledArray);  // Output: [2, 4, 6, 8, 10]
```

#### Task 8: Use the `filter` method to create a new array with only even numbers and log the new array.
```javascript
let evenArray = array.filter(num => num % 2 === 0);
console.log(evenArray);  // Output: [2, 4]
```

#### Task 9: Use the `reduce` method to calculate the sum of all numbers in the array and log the result.
```javascript
let sum = array.reduce((accumulator, currentValue) => accumulator + currentValue, 0);
console.log(sum);  // Output: 15
```

### Activity 4: Array Iteration

#### Task 10: Use a `for` loop to iterate over the array and log each element to the console.
```javascript
for (let i = 0; i < array.length; i++) {
    console.log(array[i]);
}
// Output:
// 1
// 2
// 3
// 4
// 5
```

#### Task 11: Use the `forEach` method to iterate over the array and log each element to the console.
```javascript
array.forEach(element => console.log(element));
// Output:
// 1
// 2
// 3
// 4
// 5
```

### Activity 5: Multi-dimensional Arrays

#### Task 12: Create a two-dimensional array (matrix) and log the entire array to the console.
```javascript
let matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
];
console.log(matrix);
// Output:
// [
//   [1, 2, 3],
//   [4, 5, 6],
//   [7, 8, 9]
// ]
```

#### Task 13: Access and log a specific element from the two-dimensional array.
```javascript
console.log(matrix[1][1]);  // Output: 5
```

### Feature Requests

1. **Array Manipulation Script**: Write a script that demonstrates the creation of an array, adding and removing elements using `push`, `pop`, `shift`, and `unshift` methods.
```javascript
let numbers = [1, 2, 3, 4, 5];
numbers.push(6);
console.log(numbers);  // Output: [1, 2, 3, 4, 5, 6]
numbers.pop();
console.log(numbers);  // Output: [1, 2, 3, 4, 5]
numbers.shift();
console.log(numbers);  // Output: [2, 3, 4, 5]
numbers.unshift(1);
console.log(numbers);  // Output: [1, 2, 3, 4, 5]
```

2. **Array Transformation Script**: Create a script that uses `map`, `filter`, and `reduce` methods to transform and aggregate array data.
```javascript
let numbers = [1, 2, 3, 4, 5];
let doubled = numbers.map(num => num * 2);
console.log(doubled);  // Output: [2, 4, 6, 8, 10]
let evens = numbers.filter(num => num % 2 === 0);
console.log(evens);  // Output: [2, 4]
let sum = numbers.reduce((acc, num) => acc + num, 0);
console.log(sum);  // Output: 15
```

3. **Array Iteration Script**: Write a script that iterates over an array using both `for` loop and `forEach` method and logs each element.
```javascript
let numbers = [1, 2, 3, 4, 5];
for (let i = 0; i < numbers.length; i++) {
    console.log(numbers[i]);
}
// Output:
// 1
// 2
// 3
// 4
// 5

numbers.forEach(num => console.log(num));
// Output:
// 1
// 2
// 3
// 4
// 5
```

4. **Two-dimensional Array Script**: Create a script that demonstrates the creation and manipulation of a two-dimensional array.
```javascript
let matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
];
console.log(matrix);
// Output:
// [
//   [1, 2, 3],
//   [4, 5, 6],
//   [7, 8, 9]
// ]
console.log(matrix[1][1]);  // Output: 5
```

Thats it for today

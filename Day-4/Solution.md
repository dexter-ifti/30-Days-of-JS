### Day 4: Loops

### Activity 1: For Loop

#### Task 1: Write a program to print numbers from 1 to 10 using a for loop.
```javascript
for (let i = 1; i <= 10; i++) {
    console.log(i);
}
```

#### Task 2: Write a program to print the multiplication table of 5 using a for loop.
```javascript
for (let i = 1; i <= 10; i++) {
    console.log(`5 x ${i} = ${5 * i}`);
}
```

### Activity 2: While Loop

#### Task 3: Write a program to calculate the sum of numbers from 1 to 10 using a while loop.
```javascript
let sum = 0;
let i = 1;
while (i <= 10) {
    sum += i;
    i++;
}
console.log("Sum of numbers from 1 to 10 is:", sum);
```

#### Task 4: Write a program to print numbers from 10 to 1 using a while loop.
```javascript
let i = 10;
while (i >= 1) {
    console.log(i);
    i--;
}
```

### Activity 3: Do...While Loop

#### Task 5: Write a program to print numbers from 1 to 5 using a do...while loop.
```javascript
let i = 1;
do {
    console.log(i);
    i++;
} while (i <= 5);
```

#### Task 6: Write a program to calculate the factorial of a number using a do...while loop.
```javascript
let number = 5;
let factorial = 1;
let i = 1;
do {
    factorial *= i;
    i++;
} while (i <= number);
console.log(`Factorial of ${number} is:`, factorial);
```

### Activity 4: Nested Loops

#### Task 7: Write a program to print a pattern using nested for loops.
Here's an example to print the given pattern (ignoring colors):
```javascript
for (let i = 1; i <= 5; i++) {
    let row = '';
    for (let j = 1; j <= i; j++) {
        row += '* ';
    }
    console.log(row);
}
```

### Activity 5: Loop Control Statements

#### Task 8: Write a program to print numbers from 1 to 10, but skip the number 5 using the continue statement.
```javascript
for (let i = 1; i <= 10; i++) {
    if (i === 5) {
        continue;
    }
    console.log(i);
}
```

#### Task 9: Write a program to print numbers from 1 to 10, but stop the loop when the number is 7 using the break statement.
```javascript
for (let i = 1; i <= 10; i++) {
    if (i === 7) {
        break;
    }
    console.log(i);
}
```

### Feature Requests

1. **Number Printing Script**: Write a script that prints numbers from 1 to 10 using a for loop and a while loop.
```javascript
// Using for loop
for (let i = 1; i <= 10; i++) {
    console.log(i);
}

// Using while loop
let i = 1;
while (i <= 10) {
    console.log(i);
    i++;
}
```

2. **Multiplication Table Script**: Create a script that prints the multiplication table of 5 using a for loop.
```javascript
for (let i = 1; i <= 10; i++) {
    console.log(`5 x ${i} = ${5 * i}`);
}
```

3. **Pattern Printing Script**: Write a script that prints a pattern of stars using nested loops.
```javascript
for (let i = 1; i <= 5; i++) {
    let row = '';
    for (let j = 1; j <= i; j++) {
        row += '* ';
    }
    console.log(row);
}
```

4. **Sum Calculation Script**: Write a script that calculates the sum of numbers from 1 to 10 using a while loop.
```javascript
let sum = 0;
let i = 1;
while (i <= 10) {
    sum += i;
    i++;
}
console.log("Sum of numbers from 1 to 10 is:", sum);
```

5. **Factorial Calculation Script**: Create a script that calculates the factorial of a number using a do...while loop.
```javascript
let number = 5;
let factorial = 1;
let i = 1;
do {
    factorial *= i;
    i++;
} while (i <= number);
console.log(`Factorial of ${number} is:`, factorial);
```

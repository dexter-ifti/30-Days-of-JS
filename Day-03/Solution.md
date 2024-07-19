### Day 3: Control Structures

### Activity 1: If-Else Statements

#### Task 1: Write a program to check if a number is positive, negative, or zero, and log the result to the console.
```javascript
let number = -5;
if (number > 0) {
    console.log("The number is positive.");
} else if (number < 0) {
    console.log("The number is negative.");
} else {
    console.log("The number is zero.");
}
```

#### Task 2: Write a program to check if a person is eligible to vote (age >= 18) and log the result to the console.
```javascript
let age = 20;
if (age >= 18) {
    console.log("The person is eligible to vote.");
} else {
    console.log("The person is not eligible to vote.");
}
```

### Activity 2: Nested If-Else Statements

#### Task 3: Write a program to find the largest of three numbers using nested if-else statements.
```javascript
let num1 = 10;
let num2 = 15;
let num3 = 5;

if (num1 >= num2 && num1 >= num3) {
    console.log("The largest number is:", num1);
} else if (num2 >= num1 && num2 >= num3) {
    console.log("The largest number is:", num2);
} else {
    console.log("The largest number is:", num3);
}
```

### Activity 3: Switch Case

#### Task 4: Write a program that uses a switch case to determine the day of the week based on a number (1-7) and log the day name to the console.
```javascript
let dayNumber = 3;
let dayName;

switch (dayNumber) {
    case 1:
        dayName = "Sunday";
        break;
    case 2:
        dayName = "Monday";
        break;
    case 3:
        dayName = "Tuesday";
        break;
    case 4:
        dayName = "Wednesday";
        break;
    case 5:
        dayName = "Thursday";
        break;
    case 6:
        dayName = "Friday";
        break;
    case 7:
        dayName = "Saturday";
        break;
    default:
        dayName = "Invalid day number";
}

console.log("The day is:", dayName);
```

#### Task 5: Write a program that uses a switch case to assign a grade ('A', 'B', 'C', 'D', 'F') based on a score and log the grade to the console.
```javascript
let score = 85;
let grade;

switch (true) {
    case (score >= 90):
        grade = 'A';
        break;
    case (score >= 80):
        grade = 'B';
        break;
    case (score >= 70):
        grade = 'C';
        break;
    case (score >= 60):
        grade = 'D';
        break;
    default:
        grade = 'F';
}

console.log("The grade is:", grade);
```

### Activity 4: Conditional (Ternary) Operator

#### Task 6: Write a program that uses the ternary operator to check if a number is even or odd and log the result to the console.
```javascript
let number = 7;
let result = (number % 2 === 0) ? "Even" : "Odd";
console.log("The number is:", result);
```

### Activity 5: Combining Conditions

#### Task 7: Write a program to check if a year is a leap year using multiple conditions (divisible by 4, but not 100 unless also divisible by 400) and log the result to the console.
```javascript
let year = 2020;
let isLeapYear;

if ((year % 4 === 0 && year % 100 !== 0) || (year % 400 === 0)) {
    isLeapYear = true;
} else {
    isLeapYear = false;
}

console.log("Is it a leap year?", isLeapYear);
```

### Feature Requests

1. **Number Check Script**: Write a script that checks if a number is positive, negative, or zero using if-else statements and logs the result.
```javascript
let number = -3;
if (number > 0) {
    console.log("The number is positive.");
} else if (number < 0) {
    console.log("The number is negative.");
} else {
    console.log("The number is zero.");
}
```

2. **Voting Eligibility Script**: Create a script to check if a person is eligible to vote based on their age and log the result.
```javascript
let age = 17;
if (age >= 18) {
    console.log("The person is eligible to vote.");
} else {
    console.log("The person is not eligible to vote.");
}
```

3. **Day of the Week Script**: Write a script that uses a switch case to determine the day of the week based on a number (1-7) and logs the day name.
```javascript
let dayNumber = 5;
let dayName;

switch (dayNumber) {
    case 1:
        dayName = "Sunday";
        break;
    case 2:
        dayName = "Monday";
        break;
    case 3:
        dayName = "Tuesday";
        break;
    case 4:
        dayName = "Wednesday";
        break;
    case 5:
        dayName = "Thursday";
        break;
    case 6:
        dayName = "Friday";
        break;
    case 7:
        dayName = "Saturday";
        break;
    default:
        dayName = "Invalid day number";
}

console.log("The day is:", dayName);
```

4. **Grade Assignment Script**: Create a script that uses a switch case to assign a grade based on a score and logs the grade.
```javascript
let score = 72;
let grade;

switch (true) {
    case (score >= 90):
        grade = 'A';
        break;
    case (score >= 80):
        grade = 'B';
        break;
    case (score >= 70):
        grade = 'C';
        break;
    case (score >= 60):
        grade = 'D';
        break;
    default:
        grade = 'F';
}

console.log("The grade is:", grade);
```

5. **Leap Year Check Script**: Write a script that checks if a year is a leap year using multiple conditions and logs the result.
```javascript
let year = 2000;
let isLeapYear;

if ((year % 4 === 0 && year % 100 !== 0) || (year % 400 === 0)) {
    isLeapYear = true;
} else {
    isLeapYear = false;
}

console.log("Is it a leap year?", isLeapYear);
```

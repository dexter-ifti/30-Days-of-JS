#### Activity 1: Class Definition

**Task 1: Define a class `Person` with properties `name` and `age`, and a method to return a greeting message. Create an instance of the class and log the greeting message.**
```javascript
class Person {
    constructor(name, age) {
        this.name = name;
        this.age = age;
    }

    greet() {
        return `Hello, my name is ${this.name} and I am ${this.age} years old.`;
    }
}

const person = new Person('John', 30);
console.log(person.greet()); // Output: Hello, my name is John and I am 30 years old.
```

**Task 2: Add a method to the `Person` class that updates the age property and logs the updated age.**
```javascript
class Person {
    constructor(name, age) {
        this.name = name;
        this.age = age;
    }

    greet() {
        return `Hello, my name is ${this.name} and I am ${this.age} years old.`;
    }

    updateAge(newAge) {
        this.age = newAge;
        console.log(`Updated age: ${this.age}`);
    }
}

const person = new Person('John', 30);
console.log(person.greet()); // Output: Hello, my name is John and I am 30 years old.
person.updateAge(31); // Output: Updated age: 31
```

#### Activity 2: Class Inheritance

**Task 3: Define a class `Student` that extends the `Person` class. Add a property `studentId` and a method to return the student ID. Create an instance of the `Student` class and log the student ID.**
```javascript
class Student extends Person {
    constructor(name, age, studentId) {
        super(name, age);
        this.studentId = studentId;
    }

    getStudentId() {
        return `Student ID: ${this.studentId}`;
    }
}

const student = new Student('Jane', 22, 'S12345');
console.log(student.getStudentId()); // Output: Student ID: S12345
```

**Task 4: Override the greeting method in the `Student` class to include the student ID in the message. Log the overridden greeting message.**
```javascript
class Student extends Person {
    constructor(name, age, studentId) {
        super(name, age);
        this.studentId = studentId;
    }

    greet() {
        return `Hello, my name is ${this.name}, I am ${this.age} years old, and my student ID is ${this.studentId}.`;
    }
}

const student = new Student('Jane', 22, 'S12345');
console.log(student.greet()); // Output: Hello, my name is Jane, I am 22 years old, and my student ID is S12345.
```

#### Activity 3: Static Methods and Properties

**Task 5: Add a static method to the `Person` class that returns a generic greeting message. Call this static method without creating an instance of the class and log the message.**
```javascript
class Person {
    constructor(name, age) {
        this.name = name;
        this.age = age;
    }

    greet() {
        return `Hello, my name is ${this.name} and I am ${this.age} years old.`;
    }

    static genericGreeting() {
        return 'Hello, welcome!';
    }
}

console.log(Person.genericGreeting()); // Output: Hello, welcome!
```

**Task 6: Add a static property to the `Student` class to keep track of the number of students created. Increment this property in the constructor and log the total number of students.**
```javascript
class Student extends Person {
    static studentCount = 0;

    constructor(name, age, studentId) {
        super(name, age);
        this.studentId = studentId;
        Student.studentCount++;
    }

    greet() {
        return `Hello, my name is ${this.name}, I am ${this.age} years old, and my student ID is ${this.studentId}.`;
    }

    static getStudentCount() {
        return `Total students: ${Student.studentCount}`;
    }
}

const student1 = new Student('Jane', 22, 'S12345');
const student2 = new Student('John', 23, 'S67890');
console.log(Student.getStudentCount()); // Output: Total students: 2
```

#### Activity 4: Getters and Setters

**Task 7: Add a getter method to the `Person` class to return the full name (assume a `firstName` and `lastName` property). Create an instance and log the full name using the getter.**
```javascript
class Person {
    constructor(firstName, lastName, age) {
        this.firstName = firstName;
        this.lastName = lastName;
        this.age = age;
    }

    get fullName() {
        return `${this.firstName} ${this.lastName}`;
    }

    greet() {
        return `Hello, my name is ${this.fullName} and I am ${this.age} years old.`;
    }
}

const person = new Person('John', 'Doe', 30);
console.log(person.fullName); // Output: John Doe
```

**Task 8: Add a setter method to the `Person` class to update the name properties (`firstName` and `lastName`). Update the name using the setter and log the updated full name.**
```javascript
class Person {
    constructor(firstName, lastName, age) {
        this.firstName = firstName;
        this.lastName = lastName;
        this.age = age;
    }

    get fullName() {
        return `${this.firstName} ${this.lastName}`;
    }

    set fullName(name) {
        [this.firstName, this.lastName] = name.split(' ');
    }

    greet() {
        return `Hello, my name is ${this.fullName} and I am ${this.age} years old.`;
    }
}

const person = new Person('John', 'Doe', 30);
console.log(person.fullName); // Output: John Doe
person.fullName = 'Jane Smith';
console.log(person.fullName); // Output: Jane Smith
```

#### Activity 5: Private Fields (Optional)

**Task 9: Define a class `Account` with private fields for `balance` and a method to deposit and withdraw money. Ensure that the balance can only be updated through these methods.**
```javascript
class Account {
    #balance = 0;

    deposit(amount) {
        if (amount > 0) {
            this.#balance += amount;
            console.log(`Deposited: ${amount}`);
        }
    }

    withdraw(amount) {
        if (amount > 0 && amount <= this.#balance) {
            this.#balance -= amount;
            console.log(`Withdrew: ${amount}`);
        } else {
            console.log('Insufficient funds');
        }
    }

    getBalance() {
        return this.#balance;
    }
}

const account = new Account();
account.deposit(100); // Output: Deposited: 100
account.withdraw(50); // Output: Withdrew: 50
console.log(account.getBalance()); // Output: 50
```

**Task 10: Create an instance of the `Account` class and test the deposit and withdraw methods, logging the balance after each operation.**
```javascript
const account = new Account();
account.deposit(100); // Output: Deposited: 100
console.log(`Balance: ${account.getBalance()}`); // Output: Balance: 100

account.withdraw(50); // Output: Withdrew: 50
console.log(`Balance: ${account.getBalance()}`); // Output: Balance: 50

account.withdraw(60); // Output: Insufficient funds
console.log(`Balance: ${account.getBalance()}`); // Output: Balance: 50
```

### Feature Request

1. **Basic Class Script**: Write a script that defines a `Person` class with properties and methods, creates instances, and logs messages.
2. **Class Inheritance Script**: Create a script that defines a `Student` class extending `Person`, overrides methods, and logs the results.
3. **Static Methods and Properties Script**: Write a script that demonstrates static methods and properties in classes.
4. **Getters and Setters Script**: Create a script that uses getters and setters in a class.
5. **Private Fields Script**: Write a script that defines a class with private fields and methods to manipulate these fields (optional).

### Thats it for today!

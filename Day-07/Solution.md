### Day 7: Objects


### Activity 1: Object Creation and Access

#### Task 1: Create an object representing a book with properties like title, author, and year, and log the object to the console.
```javascript
let book = {
    title: "To Kill a Mockingbird",
    author: "Harper Lee",
    year: 1960
};
console.log(book);
// Output: { title: 'To Kill a Mockingbird', author: 'Harper Lee', year: 1960 }
```

#### Task 2: Access and log the title and author properties of the book object.
```javascript
console.log(book.title);  // Output: To Kill a Mockingbird
console.log(book.author);  // Output: Harper Lee
```

### Activity 2: Object Methods

#### Task 3: Add a method to the book object that returns a string with the book's title and author, and log the result of calling this method.
```javascript
book.getInfo = function() {
    return `${this.title} by ${this.author}`;
};
console.log(book.getInfo());  // Output: To Kill a Mockingbird by Harper Lee
```

#### Task 4: Add a method to the book object that takes a parameter (year) and updates the book's year property, then log the updated object.
```javascript
book.updateYear = function(newYear) {
    this.year = newYear;
};
book.updateYear(1961);
console.log(book);
// Output: { title: 'To Kill a Mockingbird', author: 'Harper Lee', year: 1961, getInfo: [Function], updateYear: [Function] }
```

### Activity 3: Nested Objects

#### Task 5: Create a nested object representing a library with properties like name and books (an array of book objects), and log the library object to the console.
```javascript
let library = {
    name: "City Library",
    books: [
        { title: "To Kill a Mockingbird", author: "Harper Lee", year: 1960 },
        { title: "1984", author: "George Orwell", year: 1949 }
    ]
};
console.log(library);
// Output:
// {
//     name: 'City Library',
//     books: [
//         { title: 'To Kill a Mockingbird', author: 'Harper Lee', year: 1960 },
//         { title: '1984', author: 'George Orwell', year: 1949 }
//     ]
// }
```

#### Task 6: Access and log the name of the library and the titles of all the books in the library.
```javascript
console.log(library.name);  // Output: City Library
library.books.forEach(book => console.log(book.title));
// Output:
// To Kill a Mockingbird
// 1984
```

### Activity 4: The `this` Keyword

#### Task 7: Add a method to the book object that uses the `this` keyword to return a string with the book's title and year, and log the result of calling this method.
```javascript
book.getTitleAndYear = function() {
    return `${this.title} (${this.year})`;
};
console.log(book.getTitleAndYear());  // Output: To Kill a Mockingbird (1961)
```

### Activity 5: Object Iteration

#### Task 8: Use a `for...in` loop to iterate over the properties of the book object and log each property and its value.
```javascript
for (let property in book) {
    console.log(`${property}: ${book[property]}`);
}
// Output:
// title: To Kill a Mockingbird
// author: Harper Lee
// year: 1961
// getInfo: function() { ... }
// updateYear: function(newYear) { ... }
// getTitleAndYear: function() { ... }
```

#### Task 9: Use `Object.keys` and `Object.values` methods to log all the keys and values of the book object.
```javascript
console.log(Object.keys(book));
// Output: [ 'title', 'author', 'year', 'getInfo', 'updateYear', 'getTitleAndYear' ]

console.log(Object.values(book));
// Output: [ 'To Kill a Mockingbird', 'Harper Lee', 1961, [Function: getInfo], [Function: updateYear], [Function: getTitleAndYear] ]
```

### Feature Requests

1. **Book Object Script**: Write a script that creates a book object, adds methods to it, and logs its properties and method results.
```javascript
let book = {
    title: "To Kill a Mockingbird",
    author: "Harper Lee",
    year: 1960,
    getInfo: function() {
        return `${this.title} by ${this.author}`;
    },
    updateYear: function(newYear) {
        this.year = newYear;
    },
    getTitleAndYear: function() {
        return `${this.title} (${this.year})`;
    }
};

console.log(book.getInfo());  // Output: To Kill a Mockingbird by Harper Lee
book.updateYear(1961);
console.log(book);  // Output: updated book object with year 1961
console.log(book.getTitleAndYear());  // Output: To Kill a Mockingbird (1961)
```

2. **Library Object Script**: Create a script that defines a library object containing an array of book objects and logs the library's details.
```javascript
let library = {
    name: "City Library",
    books: [
        { title: "To Kill a Mockingbird", author: "Harper Lee", year: 1960 },
        { title: "1984", author: "George Orwell", year: 1949 }
    ],
    getLibraryInfo: function() {
        let info = `${this.name} contains the following books:\n`;
        this.books.forEach(book => {
            info += `${book.title} by ${book.author} (${book.year})\n`;
        });
        return info;
    }
};

console.log(library.getLibraryInfo());
// Output:
// City Library contains the following books:
// To Kill a Mockingbird by Harper Lee (1960)
// 1984 by George Orwell (1949)
```

3. **Object Iteration Script**: Write a script that demonstrates iterating over an object's properties using `for...in` loop and `Object.keys`/`Object.values`.
```javascript
let book = {
    title: "To Kill a Mockingbird",
    author: "Harper Lee",
    year: 1960
};

for (let property in book) {
    console.log(`${property}: ${book[property]}`);
}
// Output:
// title: To Kill a Mockingbird
// author: Harper Lee
// year: 1960

console.log(Object.keys(book));
// Output: [ 'title', 'author', 'year' ]

console.log(Object.values(book));
// Output: [ 'To Kill a Mockingbird', 'Harper Lee', 1960 ]
```

Thats it for today

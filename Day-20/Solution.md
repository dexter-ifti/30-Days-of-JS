#### Activity 1: Understanding LocalStorage

**Task 1: Write a script to save a string value to `localStorage` and retrieve it. Log the retrieved value.**
```javascript
// Save string to localStorage
localStorage.setItem('myString', 'Hello, LocalStorage!');

// Retrieve the string from localStorage
let retrievedString = localStorage.getItem('myString');
console.log(retrievedString);
```

**Task 2: Write a script to save an object to `localStorage` by converting it to a JSON string. Retrieve and parse the object, then log it.**
```javascript
// Save object to localStorage
let myObject = { name: 'John', age: 30 };
localStorage.setItem('myObject', JSON.stringify(myObject));

// Retrieve and parse the object from localStorage
let retrievedObject = JSON.parse(localStorage.getItem('myObject'));
console.log(retrievedObject);
```

#### Activity 2: Using LocalStorage

**Task 3: Create a simple form that saves user input (e.g., name and email) to `localStorage` when submitted. Retrieve and display the saved data on page load.**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>LocalStorage Form</title>
</head>
<body>
    <form id="userForm">
        <label for="name">Name:</label>
        <input type="text" id="name" name="name" required>
        <label for="email">Email:</label>
        <input type="email" id="email" name="email" required>
        <button type="submit">Submit</button>
    </form>
    <div id="savedData"></div>

    <script>
        document.getElementById('userForm').addEventListener('submit', function(event) {
            event.preventDefault();
            let name = document.getElementById('name').value;
            let email = document.getElementById('email').value;
            localStorage.setItem('userName', name);
            localStorage.setItem('userEmail', email);
            displaySavedData();
        });

        function displaySavedData() {
            let savedName = localStorage.getItem('userName');
            let savedEmail = localStorage.getItem('userEmail');
            if (savedName && savedEmail) {
                document.getElementById('savedData').innerText = `Name: ${savedName}, Email: ${savedEmail}`;
            }
        }

        // Display saved data on page load
        displaySavedData();
    </script>
</body>
</html>
```

**Task 4: Write a script to remove an item from `localStorage`. Log the `localStorage` content before and after removal.**
```javascript
// Log localStorage content before removal
console.log('Before removal:', localStorage.getItem('myString'));

// Remove item from localStorage
localStorage.removeItem('myString');

// Log localStorage content after removal
console.log('After removal:', localStorage.getItem('myString'));
```

#### Activity 3: Understanding SessionStorage

**Task 5: Write a script to save a string value to `sessionStorage` and retrieve it. Log the retrieved value.**
```javascript
// Save string to sessionStorage
sessionStorage.setItem('myString', 'Hello, SessionStorage!');

// Retrieve the string from sessionStorage
let retrievedString = sessionStorage.getItem('myString');
console.log(retrievedString);
```

**Task 6: Write a script to save an object to `sessionStorage` by converting it to a JSON string. Retrieve and parse the object, then log it.**
```javascript
// Save object to sessionStorage
let myObject = { name: 'Doe', age: 25 };
sessionStorage.setItem('myObject', JSON.stringify(myObject));

// Retrieve and parse the object from sessionStorage
let retrievedObject = JSON.parse(sessionStorage.getItem('myObject'));
console.log(retrievedObject);
```

#### Activity 4: Using SessionStorage

**Task 7: Create a simple form that saves user input (e.g., name and email) to `sessionStorage` when submitted. Retrieve and display the saved data on page load.**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SessionStorage Form</title>
</head>
<body>
    <form id="userForm">
        <label for="name">Name:</label>
        <input type="text" id="name" name="name" required>
        <label for="email">Email:</label>
        <input type="email" id="email" name="email" required>
        <button type="submit">Submit</button>
    </form>
    <div id="savedData"></div>

    <script>
        document.getElementById('userForm').addEventListener('submit', function(event) {
            event.preventDefault();
            let name = document.getElementById('name').value;
            let email = document.getElementById('email').value;
            sessionStorage.setItem('userName', name);
            sessionStorage.setItem('userEmail', email);
            displaySavedData();
        });

        function displaySavedData() {
            let savedName = sessionStorage.getItem('userName');
            let savedEmail = sessionStorage.getItem('userEmail');
            if (savedName && savedEmail) {
                document.getElementById('savedData').innerText = `Name: ${savedName}, Email: ${savedEmail}`;
            }
        }

        // Display saved data on page load
        displaySavedData();
    </script>
</body>
</html>
```

**Task 8: Write a script to remove an item from `sessionStorage`. Log the `sessionStorage` content before and after removal.**
```javascript
// Log sessionStorage content before removal
console.log('Before removal:', sessionStorage.getItem('myString'));

// Remove item from sessionStorage
sessionStorage.removeItem('myString');

// Log sessionStorage content after removal
console.log('After removal:', sessionStorage.getItem('myString'));
```

#### Activity 5: Comparing LocalStorage and SessionStorage

**Task 9: Write a function that accepts a key and a value, and saves the value to both `localStorage` and `sessionStorage`. Retrieve and log the values from both storage mechanisms.**
```javascript
function saveToBothStorages(key, value) {
    localStorage.setItem(key, value);
    sessionStorage.setItem(key, value);

    let localValue = localStorage.getItem(key);
    let sessionValue = sessionStorage.getItem(key);
    
    console.log(`LocalStorage: ${localValue}, SessionStorage: ${sessionValue}`);
}

// Example usage
saveToBothStorages('myKey', 'Hello, Storage!');
```

**Task 10: Write a function that clears all data from both `localStorage` and `sessionStorage`. Verify that both storages are empty.**
```javascript
function clearAllStorages() {
    localStorage.clear();
    sessionStorage.clear();

    console.log('LocalStorage:', localStorage.length === 0 ? 'Empty' : 'Not Empty');
    console.log('SessionStorage:', sessionStorage.length === 0 ? 'Empty' : 'Not Empty');
}

// Example usage
clearAllStorages();
```

### Thats it for today

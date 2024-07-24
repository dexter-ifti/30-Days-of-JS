I'll provide solutions for each task. I'll group them by activity and provide code examples for each.

Activity 1: Basic Error Handling with Try-Catch

Task 1:
```javascript
function throwError() {
  try {
    throw new Error("This is an intentional error");
  } catch (error) {
    console.log("Error caught:", error.message);
  }
}

throwError();
```

Task 2:
```javascript
function divideNumbers(a, b) {
  try {
    if (b === 0) {
      throw new Error("Cannot divide by zero");
    }
    return a / b;
  } catch (error) {
    console.log("Error:", error.message);
  }
}

console.log(divideNumbers(10, 2));  // Output: 5
divideNumbers(10, 0);  // Output: Error: Cannot divide by zero
```

Activity 2: Finally Block

Task 3:
```javascript
function demonstrateFinally() {
  try {
    console.log("Trying something...");
    throw new Error("Something went wrong");
  } catch (error) {
    console.log("Caught an error:", error.message);
  } finally {
    console.log("This always executes");
  }
}

demonstrateFinally();
```

Activity 3: Custom Error Objects

Task 4:
```javascript
class CustomError extends Error {
  constructor(message) {
    super(message);
    this.name = "CustomError";
  }
}

function throwCustomError() {
  try {
    throw new CustomError("This is a custom error");
  } catch (error) {
    if (error instanceof CustomError) {
      console.log("Caught custom error:", error.message);
    } else {
      console.log("Caught unexpected error:", error);
    }
  }
}

throwCustomError();
```

Task 5:
```javascript
function validateInput(input) {
  if (!input || input.trim() === "") {
    throw new CustomError("Input cannot be empty");
  }
  return input;
}

function processInput(input) {
  try {
    const validatedInput = validateInput(input);
    console.log("Valid input:", validatedInput);
  } catch (error) {
    if (error instanceof CustomError) {
      console.log("Validation error:", error.message);
    } else {
      console.log("Unexpected error:", error);
    }
  }
}

processInput("");  // Output: Validation error: Input cannot be empty
processInput("Hello");  // Output: Valid input: Hello
```

Activity 4: Error Handling in Promises

Task 6:
```javascript
function randomPromise() {
  return new Promise((resolve, reject) => {
    if (Math.random() > 0.5) {
      resolve("Success");
    } else {
      reject("Random failure");
    }
  });
}

randomPromise().catch(error => {
  console.log("Promise rejected:", error);
});
```

Task 7:
```javascript
async function handleRandomPromise() {
  try {
    const result = await randomPromise();
    console.log("Promise resolved:", result);
  } catch (error) {
    console.log("Async function caught error:", error);
  }
}

handleRandomPromise();
```

Activity 5: Graceful Error Handling in Fetch

Task 8:
```javascript
fetch('https://invalid-url.com')
  .then(response => response.json())
  .catch(error => {
    console.log("Fetch error:", error.message);
  });
```

Task 9:
```javascript
async function fetchData(url) {
  try {
    const response = await fetch(url);
    const data = await response.json();
    console.log("Data fetched:", data);
  } catch (error) {
    console.log("Async fetch error:", error.message);
  }
}

fetchData('https://invalid-url.com');
```

### Thats it for today!

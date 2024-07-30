#### Activity 1: Callbacks

**Task 1: Implement a function that uses a callback to log a message after a delay.**
```javascript
function logAfterDelay(message, delay, callback) {
    setTimeout(() => {
        console.log(message);
        if (callback) callback();
    }, delay);
}

// Example usage:
logAfterDelay("Hello, World!", 2000, () => console.log("Callback executed!"));
```

**Task 2: Implement a function that performs an asynchronous operation (e.g., fetching data) using a callback.**
```javascript
function fetchData(url, callback) {
    setTimeout(() => {
        const data = `Data from ${url}`;
        callback(data);
    }, 2000);
}

// Example usage:
fetchData("https://api.example.com/data", (data) => console.log(data));
```

#### Activity 2: Promises

**Task 3: Implement a function that returns a promise which resolves after a delay.**
```javascript
function delay(ms) {
    return new Promise((resolve) => setTimeout(resolve, ms));
}

// Example usage:
delay(2000).then(() => console.log("2 seconds have passed!"));
```

**Task 4: Implement a function that performs an asynchronous operation using a promise.**
```javascript
function fetchData(url) {
    return new Promise((resolve) => {
        setTimeout(() => {
            const data = `Data from ${url}`;
            resolve(data);
        }, 2000);
    });
}

// Example usage:
fetchData("https://api.example.com/data").then((data) => console.log(data));
```

#### Activity 3: Async/Await

**Task 5: Implement an async function that uses `await` to wait for a promise to resolve and then logs the result.**
```javascript
async function logDataAfterDelay(url) {
    const data = await fetchData(url);
    console.log(data);
}

// Example usage:
logDataAfterDelay("https://api.example.com/data");
```

**Task 6: Implement an async function that performs multiple asynchronous operations in sequence using `await`.**
```javascript
async function performAsyncOperations() {
    console.log("Starting operations...");
    await delay(1000);
    console.log("1 second delay complete");
    const data = await fetchData("https://api.example.com/data");
    console.log(data);
}

// Example usage:
performAsyncOperations();
```

#### Activity 4: Error Handling

**Task 7: Implement a function that returns a promise which rejects after a delay, and handle the error using `catch`.**
```javascript
function errorAfterDelay(ms) {
    return new Promise((_, reject) => setTimeout(() => reject("Error occurred!"), ms));
}

// Example usage:
errorAfterDelay(2000)
    .catch((error) => console.error(error));
```

**Task 8: Implement an async function that performs an asynchronous operation and handles errors using `try/catch`.**
```javascript
async function fetchDataWithErrorHandling(url) {
    try {
        const data = await fetchData(url);
        console.log(data);
    } catch (error) {
        console.error("Failed to fetch data:", error);
    }
}

// Example usage:
fetchDataWithErrorHandling("https://api.example.com/data");
```

#### Activity 5: Advanced Promises

**Task 9: Implement a function that performs multiple asynchronous operations in parallel using `Promise.all`.**
```javascript
function fetchMultipleData(urls) {
    const promises = urls.map(url => fetchData(url));
    return Promise.all(promises);
}

// Example usage:
fetchMultipleData(["https://api.example.com/data1", "https://api.example.com/data2"])
    .then((data) => console.log(data));
```

**Task 10: Implement a function that performs asynchronous operations and handles both success and failure using `Promise.allSettled`.**
```javascript
function fetchAllSettled(urls) {
    const promises = urls.map(url => fetchData(url));
    return Promise.allSettled(promises);
}

// Example usage:
fetchAllSettled(["https://api.example.com/data1", "https://api.invalidurl.com/data2"])
    .then((results) => results.forEach(result => console.log(result.status, result.value || result.reason)));
```

### Thats it for today

### Day 11: Promises and Async/Await


### Activity 1: Understanding Promises

#### Task 1: Create a promise that resolves with a message after a 2-second timeout and log the message to the console.
```javascript
let promise1 = new Promise((resolve) => {
    setTimeout(() => {
        resolve('Resolved after 2 seconds');
    }, 2000);
});

promise1.then((message) => {
    console.log(message);
});
```

#### Task 2: Create a promise that rejects with an error message after a 2-second timeout and handle the error using `.catch()`.
```javascript
let promise2 = new Promise((_, reject) => {
    setTimeout(() => {
        reject('Rejected after 2 seconds');
    }, 2000);
});

promise2.catch((error) => {
    console.error(error);
});
```

### Activity 2: Chaining Promises

#### Task 3: Create a sequence of promises that simulate fetching data from a server. Chain the promises to log messages in a specific order.
```javascript
let fetchData = new Promise((resolve) => {
    setTimeout(() => {
        resolve('Data fetched');
    }, 1000);
});

fetchData
    .then((message) => {
        console.log(message);
        return new Promise((resolve) => {
            setTimeout(() => {
                resolve('Data processed');
            }, 1000);
        });
    })
    .then((message) => {
        console.log(message);
        return new Promise((resolve) => {
            setTimeout(() => {
                resolve('Data displayed');
            }, 1000);
        });
    })
    .then((message) => {
        console.log(message);
    });
```

### Activity 3: Using Async/Await

#### Task 4: Write an async function that waits for a promise to resolve and then logs the resolved value.
```javascript
let promise3 = new Promise((resolve) => {
    setTimeout(() => {
        resolve('Resolved after 3 seconds');
    }, 3000);
});

async function logResolvedValue() {
    let value = await promise3;
    console.log(value);
}

logResolvedValue();
```

#### Task 5: Write an async function that handles a rejected promise using try-catch and logs the error message.
```javascript
let promise4 = new Promise((_, reject) => {
    setTimeout(() => {
        reject('Rejected after 3 seconds');
    }, 3000);
});

async function handleRejection() {
    try {
        let value = await promise4;
        console.log(value);
    } catch (error) {
        console.error(error);
    }
}

handleRejection();
```

### Activity 4: Fetching Data from an API

#### Task 6: Use the `fetch` API to get data from a public API and log the response data to the console using promises.
```javascript
fetch('https://api.example.com/data')
    .then((response) => response.json())
    .then((data) => {
        console.log(data);
    })
    .catch((error) => {
        console.error('Error:', error);
    });
```

#### Task 7: Use the `fetch` API to get data from a public API and log the response data to the console using async/await.
```javascript
async function fetchData() {
    try {
        let response = await fetch('https://api.example.com/data');
        let data = await response.json();
        console.log(data);
    } catch (error) {
        console.error('Error:', error);
    }
}

fetchData();
```

### Activity 5: Concurrent Promises

#### Task 8: Use `Promise.all` to wait for multiple promises to resolve and then log all their values.
```javascript
let promiseA = new Promise((resolve) => setTimeout(resolve, 1000, 'A'));
let promiseB = new Promise((resolve) => setTimeout(resolve, 2000, 'B'));
let promiseC = new Promise((resolve) => setTimeout(resolve, 3000, 'C'));

Promise.all([promiseA, promiseB, promiseC])
    .then((values) => {
        console.log(values);
    });
```

#### Task 9: Use `Promise.race` to log the value of the first promise that resolves among multiple promises.
```javascript
let promiseX = new Promise((resolve) => setTimeout(resolve, 1000, 'X'));
let promiseY = new Promise((resolve) => setTimeout(resolve, 2000, 'Y'));
let promiseZ = new Promise((resolve) => setTimeout(resolve, 3000, 'Z'));

Promise.race([promiseX, promiseY, promiseZ])
    .then((value) => {
        console.log('First resolved value:', value);
    });
```

### Feature Requests

1. **Promise Creation Script**: Write a script that demonstrates creating and handling promises, including both resolved and rejected states.
```javascript
let createPromise = (isResolved) => {
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            if (isResolved) {
                resolve('Promise resolved');
            } else {
                reject('Promise rejected');
            }
        }, 2000);
    });
};

createPromise(true).then(console.log).catch(console.error);
createPromise(false).then(console.log).catch(console.error);
```

2. **Promise Chaining Script**: Create a script that chains multiple promises and logs messages in a specific sequence.
```javascript
let chainPromises = () => {
    return new Promise((resolve) => {
        setTimeout(() => {
            resolve('Step 1 completed');
        }, 1000);
    })
    .then((message) => {
        console.log(message);
        return new Promise((resolve) => {
            setTimeout(() => {
                resolve('Step 2 completed');
            }, 1000);
        });
    })
    .then((message) => {
        console.log(message);
        return new Promise((resolve) => {
            setTimeout(() => {
                resolve('Step 3 completed');
            }, 1000);
        });
    })
    .then(console.log);
};

chainPromises();
```

3. **Async/Await Script**: Write a script that uses async/await to handle promises and includes error handling with try-catch.
```javascript
let asyncFunction = async (isResolved) => {
    try {
        let value = await new Promise((resolve, reject) => {
            setTimeout(() => {
                if (isResolved) {
                    resolve('Async/await resolved');
                } else {
                    reject('Async/await rejected');
                }
            }, 2000);
        });
        console.log(value);
    } catch (error) {
        console.error(error);
    }
};

asyncFunction(true);
asyncFunction(false);
```

4. **API Fetch Script**: Create a script that fetches data from a public API using both promises and async/await, and logs the response data.
```javascript
let fetchDataWithPromise = () => {
    fetch('https://api.example.com/data')
        .then((response) => response.json())
        .then(console.log)
        .catch(console.error);
};

let fetchDataWithAsyncAwait = async () => {
    try {
        let response = await fetch('https://api.example.com/data');
        let data = await response.json();
        console.log(data);
    } catch (error) {
        console.error(error);
    }
};

fetchDataWithPromise();
fetchDataWithAsyncAwait();
```

5. **Concurrent Promises Script**: Write a script that uses `Promise.all` and `Promise.race` to handle multiple promises concurrently and logs the results.
```javascript
let promise1 = new Promise((resolve) => setTimeout(resolve, 1000, 'One'));
let promise2 = new Promise((resolve) => setTimeout(resolve, 2000, 'Two'));
let promise3 = new Promise((resolve) => setTimeout(resolve, 3000, 'Three'));

Promise.all([promise1, promise2, promise3])
    .then((values) => {
        console.log('Promise.all results:', values);
    });

Promise.race([promise1, promise2, promise3])
    .then((value) => {
        console.log('Promise.race result:', value);
    });
```

### Thats it for Today

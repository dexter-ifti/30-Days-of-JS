#### Activity 1: Creating and Exporting Modules

**Task 1: Create a module that exports a function to add two numbers. Import and use this module in another script.**
```javascript
// mathModule.js
export const add = (a, b) => a + b;

// main.js
import { add } from './mathModule.js';

console.log(add(2, 3)); // Output: 5
```

**Task 2: Create a module that exports an object representing a person with properties and methods. Import and use this module in another script.**
```javascript
// personModule.js
export const person = {
  name: "John",
  age: 30,
  greet() {
    console.log(`Hello, my name is ${this.name}`);
  },
};

// main.js
import { person } from './personModule.js';

console.log(person.name); // Output: John
person.greet(); // Output: Hello, my name is John
```

#### Activity 2: Named and Default Exports

**Task 3: Create a module that exports multiple functions using named exports. Import and use these functions in another

 script.**
```javascript
// utilities.js
export const multiply = (a, b) => a * b;
export const divide = (a, b) => a / b;

// main.js
import { multiply, divide } from './utilities.js';

console.log(multiply(2, 3)); // Output: 6
console.log(divide(6, 2)); // Output: 3
```

**Task 4: Create a module that exports a single function using default export. Import and use this function in another script.**
```javascript
// square.js
const square = (x) => x * x;
export default square;

// main.js
import square from './square.js';

console.log(square(4)); // Output: 16
```

#### Activity 3: Importing Entire Modules

**Task 5: Create a module that exports multiple constants and functions. Import the entire module as an object in another script and use its properties.**
```javascript
// constants.js
export const PI = 3.14;
export const E = 2.71;

export const add = (a, b) => a + b;
export const subtract = (a, b) => a - b;

// main.js
import * as math from './constants.js';

console.log(math.PI); // Output: 3.14
console.log(math.add(2, 3)); // Output: 5
```

#### Activity 4: Using Third-Party Modules

**Task 6: Install a third-party module (e.g., lodash) using npm. Import and use a function from this module in a script.**
```bash
# Terminal
npm install lodash
```

```javascript
// main.js
import _ from 'lodash';

const array = [1, 2, 3, 4];
const reversed = _.reverse(array.slice());
console.log(reversed); // Output: [4, 3, 2, 1]
```

**Task 7: Install a third-party module (e.g., axios) using npm. Import and use this module to make a network request in a script.**
```bash
# Terminal
npm install axios
```

```javascript
// main.js
import axios from 'axios';

axios.get('https://jsonplaceholder.typicode.com/posts/1')
  .then(response => console.log(response.data))
  .catch(error => console.error('Error:', error));
```

#### Activity 5: Module Bundling (Optional)

**Task 8: Use a module bundler like Webpack or Parcel to bundle multiple JavaScript files into a single file. Write a script to demonstrate the bundling process.**

```bash
# Terminal
npm install --save-dev webpack webpack-cli
```

```javascript
// webpack.config.js
const path = require('path');

module.exports = {
  entry: './src/index.js',
  output: {
    filename: 'bundle.js',
    path: path.resolve(__dirname, 'dist'),
  },
  mode: 'development',
};
```

```javascript
// src/index.js
import { add } from './mathModule.js';
import square from './square.js';

console.log(add(2, 3)); // Output: 5
console.log(square(4)); // Output: 16
```

```bash
# Terminal
npx webpack
```

After running `npx webpack`, the bundled file `bundle.js` will be created in the `dist` directory.

### Thats it for today

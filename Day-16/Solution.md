#### Activity 1: Basic Recursion

**Task 1: Write a recursive function to calculate the factorial of a number. Log the result for a few test cases.**
```javascript
function factorial(n) {
    if (n === 0) {
        return 1;
    }
    return n * factorial(n - 1);
}

console.log(factorial(5)); // Output: 120
console.log(factorial(3)); // Output: 6
console.log(factorial(0)); // Output: 1
```

**Task 2: Write a recursive function to calculate the nth Fibonacci number. Log the result for a few test cases.**
```javascript
function fibonacci(n) {
    if (n <= 1) {
        return n;
    }
    return fibonacci(n - 1) + fibonacci(n - 2);
}

console.log(fibonacci(6)); // Output: 8
console.log(fibonacci(10)); // Output: 55
console.log(fibonacci(0)); // Output: 0
```

#### Activity 2: Recursion with Arrays

**Task 3: Write a recursive function to find the sum of all elements in an array. Log the result for a few test cases.**
```javascript
function sumArray(arr) {
    if (arr.length === 0) {
        return 0;
    }
    return arr[0] + sumArray(arr.slice(1));
}

console.log(sumArray([1, 2, 3, 4, 5])); // Output: 15
console.log(sumArray([10, 20, 30])); // Output: 60
console.log(sumArray([])); // Output: 0
```

**Task 4: Write a recursive function to find the maximum element in an array. Log the result for a few test cases.**
```javascript
function maxArray(arr) {
    if (arr.length === 1) {
        return arr[0];
    }
    return Math.max(arr[0], maxArray(arr.slice(1)));
}

console.log(maxArray([1, 2, 3, 4, 5])); // Output: 5
console.log(maxArray([10, 20, 30])); // Output: 30
console.log(maxArray([5])); // Output: 5
```

#### Activity 3: String Manipulation with Recursion

**Task 5: Write a recursive function to reverse a string. Log the result for a few test cases.**
```javascript
function reverseString(str) {
    if (str === "") {
        return "";
    }
    return reverseString(str.substr(1)) + str.charAt(0);
}

console.log(reverseString("hello")); // Output: "olleh"
console.log(reverseString("world")); // Output: "dlrow"
console.log(reverseString("a")); // Output: "a"
```

**Task 6: Write a recursive function to check if a string is a palindrome. Log the result for a few test cases.**
```javascript
function isPalindrome(str) {
    if (str.length <= 1) {
        return true;
    }
    if (str.charAt(0) !== str.charAt(str.length - 1)) {
        return false;
    }
    return isPalindrome(str.slice(1, str.length - 1));
}

console.log(isPalindrome("racecar")); // Output: true
console.log(isPalindrome("hello")); // Output: false
console.log(isPalindrome("a")); // Output: true
```

#### Activity 4: Recursive Search

**Task 7: Write a recursive function to perform a binary search on a sorted array. Log the index of the target element for a few test cases.**
```javascript
function binarySearch(arr, target, start = 0, end = arr.length - 1) {
    if (start > end) {
        return -1;
    }
    let mid = Math.floor((start + end) / 2);
    if (arr[mid] === target) {
        return mid;
    }
    if (arr[mid] > target) {
        return binarySearch(arr, target, start, mid - 1);
    }
    return binarySearch(arr, target, mid + 1, end);
}

console.log(binarySearch([1, 2, 3, 4, 5], 3)); // Output: 2
console.log(binarySearch([10, 20, 30, 40, 50], 40)); // Output: 3
console.log(binarySearch([1, 2, 3, 4, 5], 6)); // Output: -1
```

**Task 8: Write a recursive function to count the occurrences of the target element in an array. Log the result for a few test cases.**
```javascript
function countOccurrences(arr, target) {
    if (arr.length === 0) {
        return 0;
    }
    return (arr[0] === target ? 1 : 0) + countOccurrences(arr.slice(1), target);
}

console.log(countOccurrences([1, 2, 3, 4, 5, 3, 3], 3)); // Output: 3
console.log(countOccurrences([10, 20, 30, 20, 20], 20)); // Output: 3
console.log(countOccurrences([1, 2, 3, 4, 5], 6)); // Output: 0
```

#### Activity 5: Tree Traversal (Optional)

**Task 9: Write a recursive function to perform an in-order traversal of a binary tree. Log the nodes as they are visited.**
```javascript
class TreeNode {
    constructor(value, left = null, right = null) {
        this.value = value;
        this.left = left;
        this.right = right;
    }
}

function inOrderTraversal(node) {
    if (node !== null) {
        inOrderTraversal(node.left);
        console.log(node.value);
        inOrderTraversal(node.right);
    }
}

const root = new TreeNode(1, new TreeNode(2), new TreeNode(3));
inOrderTraversal(root); // Output: 2 1 3
```

**Task 10: Write a recursive function to calculate the depth of a binary tree. Log the result for a few test cases.**
```javascript
function calculateDepth(node) {
    if (node === null) {
        return 0;
    }
    let leftDepth = calculateDepth(node.left);
    let rightDepth = calculateDepth(node.right);
    return Math.max(leftDepth, rightDepth) + 1;
}

const root = new TreeNode(1, new TreeNode(2, new TreeNode(4)), new TreeNode(3));
console.log(calculateDepth(root)); // Output: 3
```

### Thats it for today

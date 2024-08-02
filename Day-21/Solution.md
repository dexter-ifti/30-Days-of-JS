### Activity 1: Two Sum

**Task 1: Solve the "Two Sum" problem on LeetCode.**
- Write a function that takes an array of numbers and a target number, and returns the indices of the two numbers that add up to the target.
- Log the indices for a few test cases.

```javascript
function twoSum(nums, target) {
    const seen = {};
    for (let i = 0; i < nums.length; i++) {
        const remaining = target - nums[i];
        if (seen[remaining] !== undefined) {
            return [seen[remaining], i];
        }
        seen[nums[i]] = i;
    }
    return [];
}

// Test cases
console.log(twoSum([2, 7, 11, 15], 9));  // Output: [0, 1]
console.log(twoSum([3, 2, 4], 6));       // Output: [1, 2]
console.log(twoSum([3, 3], 6));          // Output: [0, 1]
```

### Activity 2: Reverse Integer

**Task 2: Solve the "Reverse Integer" problem on LeetCode.**
- Write a function that takes an integer and returns it with its digits reversed.
- Handle edge cases like negative numbers and numbers ending in zero.
- Log the reversed integers for a few test cases.

```javascript
function reverseInteger(x) {
    const sign = x < 0 ? -1 : 1;
    x = Math.abs(x);
    const reversedX = parseInt(x.toString().split('').reverse().join(''));
    if (reversedX > 2**31 - 1) {
        return 0;
    }
    return sign * reversedX;
}

// Test cases
console.log(reverseInteger(123));   // Output: 321
console.log(reverseInteger(-123));  // Output: -321
console.log(reverseInteger(120));   // Output: 21
```

### Activity 3: Palindrome Number

**Task 3: Solve the "Palindrome Number" problem on LeetCode.**
- Write a function that takes an integer and returns true if it is a palindrome, and false otherwise.
- Log the result for a few test cases, including edge cases like negative numbers.

```javascript
function isPalindrome(x) {
    if (x < 0) {
        return false;
    }
    const str = x.toString();
    return str === str.split('').reverse().join('');
}

// Test cases
console.log(isPalindrome(121));   // Output: true
console.log(isPalindrome(-121));  // Output: false
console.log(isPalindrome(10));    // Output: false
```

### Activity 4: Merge Two Sorted Lists

**Task 4: Solve the "Merge Two Sorted Lists" problem on LeetCode.**
- Write a function that takes two sorted linked lists and returns a new sorted list by merging them.
- Create a few test cases with linked lists and log the merged list.

```javascript
class ListNode {
    constructor(val = 0, next = null) {
        this.val = val;
        this.next = next;
    }
}

function mergeTwoLists(l1, l2) {
    const dummy = new ListNode();
    let current = dummy;
    while (l1 && l2) {
        if (l1.val < l2.val) {
            current.next = l1;
            l1 = l1.next;
        } else {
            current.next = l2;
            l2 = l2.next;
        }
        current = current.next;
    }
    current.next = l1 || l2;
    return dummy.next;
}

function printList(node) {
    let result = '';
    while (node) {
        result += node.val + ' -> ';
        node = node.next;
    }
    result += 'null';
    console.log(result);
}

// Test cases
const l1 = new ListNode(1, new ListNode(2, new ListNode(4)));
const l2 = new ListNode(1, new ListNode(3, new ListNode(4)));
const mergedList = mergeTwoLists(l1, l2);
printList(mergedList);  // Output: 1 -> 1 -> 2 -> 3 -> 4 -> 4 -> null
```

### Activity 5: Valid Parentheses

**Task 5: Solve the "Valid Parentheses" problem on LeetCode.**
- Write a function that takes a string containing just the characters '(', ')', '{', '}', '[' and ']', and determines if the input string is valid.
- A string is valid if open brackets are closed in the correct order.
- Log the result for a few test cases.

```javascript
function isValid(s) {
    const stack = [];
    const mapping = { ')': '(', '}': '{', ']': '[' };
    for (let char of s) {
        if (mapping[char]) {
            const topElement = stack.length ? stack.pop() : '#';
            if (mapping[char] !== topElement) {
                return false;
            }
        } else {
            stack.push(char);
        }
    }
    return stack.length === 0;
}

// Test cases
console.log(isValid("()"));     // Output: true
console.log(isValid("()[]{}")); // Output: true
console.log(isValid("(]"));     // Output: false
console.log(isValid("([)]"));   // Output: false
console.log(isValid("{[]}"));   // Output: true
```

### Feature Request Scripts

1. **Two Sum Script**

```javascript
function twoSum(nums, target) {
    const seen = {};
    for (let i = 0; i < nums.length; i++) {
        const remaining = target - nums[i];
        if (seen[remaining] !== undefined) {
            return [seen[remaining], i];
        }
        seen[nums[i]] = i;
    }
    return [];
}

// Test cases
console.log(twoSum([2, 7, 11, 15], 9));  // Output: [0, 1]
console.log(twoSum([3, 2, 4], 6));       // Output: [1, 2]
console.log(twoSum([3, 3], 6));          // Output: [0, 1]
```

2. **Reverse Integer Script**

```javascript
function reverseInteger(x) {
    const sign = x < 0 ? -1 : 1;
    x = Math.abs(x);
    const reversedX = parseInt(x.toString().split('').reverse().join(''));
    if (reversedX > 2**31 - 1) {
        return 0;
    }
    return sign * reversedX;
}

// Test cases
console.log(reverseInteger(123));   // Output: 321
console.log(reverseInteger(-123));  // Output: -321
console.log(reverseInteger(120));   // Output: 21
```

3. **Palindrome Number Script**

```javascript
function isPalindrome(x) {
    if (x < 0) {
        return false;
    }
    const str = x.toString();
    return str === str.split('').reverse().join('');
}

// Test cases
console.log(isPalindrome(121));   // Output: true
console.log(isPalindrome(-121));  // Output: false
console.log(isPalindrome(10));    // Output: false
```

4. **Merge Two Sorted Lists Script**

```javascript
class ListNode {
    constructor(val = 0, next = null) {
        this.val = val;
        this.next = next;
    }
}

function mergeTwoLists(l1, l2) {
    const dummy = new ListNode();
    let current = dummy;
    while (l1 && l2) {
        if (l1.val < l2.val) {
            current.next = l1;
            l1 = l1.next;
        } else {
            current.next = l2;
            l2 = l2.next;
        }
        current = current.next;
    }
    current.next = l1 || l2;
    return dummy.next;
}

function printList(node) {
    let result = '';
    while (node) {
        result += node.val + ' -> ';
        node = node.next;
    }
    result += 'null';
    console.log(result);
}

// Test cases
const l1 = new ListNode(1, new ListNode(2, new ListNode(4)));
const l2 = new ListNode(1, new ListNode(3, new ListNode(4)));
const mergedList = mergeTwoLists(l1, l2);
printList(mergedList);  // Output: 1 -> 1 -> 2 -> 3 -> 4 -> 4 -> null
```

5. **Valid Parentheses Script**

```javascript
function isValid(s) {
    const stack = [];
    const mapping = { ')': '(', '}': '{', ']': '[' };
    for (let char of s) {
        if (mapping[char]) {
            const topElement = stack.length ? stack.pop() : '#';
            if (mapping[char] !== topElement) {
                return false;
            }
        } else {
            stack.push(char);
        }
    }
    return stack.length === 0;
}

// Test cases
console.log(isValid("()"));     // Output: true
console.log(isValid("()[]{}")); // Output: true
console.log(isValid("(]"));     // Output: false
```
### Thats it  

### Activity 1: Add Two Numbers

**Task 1: Solve the "Add Two Numbers" problem on LeetCode.**
- Write a function that takes two non-empty linked lists representing two non-negative integers. The digits are stored in reverse order, and each node contains a single digit. Add the two numbers and return the sum as a linked list.
- Create a few test cases with linked lists and log the sum as a linked list.

```javascript
class ListNode {
    constructor(val = 0, next = null) {
        this.val = val;
        this.next = next;
    }
}

function addTwoNumbers(l1, l2) {
    const dummy = new ListNode(0);
    let current = dummy;
    let carry = 0;
    while (l1 !== null || l2 !== null) {
        const x = l1 !== null ? l1.val : 0;
        const y = l2 !== null ? l2.val : 0;
        const sum = carry + x + y;
        carry = Math.floor(sum / 10);
        current.next = new ListNode(sum % 10);
        current = current.next;
        if (l1 !== null) l1 = l1.next;
        if (l2 !== null) l2 = l2.next;
    }
    if (carry > 0) {
        current.next = new ListNode(carry);
    }
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
const l1 = new ListNode(2, new ListNode(4, new ListNode(3)));
const l2 = new ListNode(5, new ListNode(6, new ListNode(4)));
const sumList = addTwoNumbers(l1, l2);
printList(sumList);  // Output: 7 -> 0 -> 8 -> null
```

### Activity 2: Longest Substring Without Repeating Characters

**Task 2: Solve the "Longest Substring Without Repeating Characters" problem on LeetCode.**
- Write a function that takes a string and returns the length of the longest substring without repeating characters.
- Log the length for a few test cases, including edge cases.

```javascript
function lengthOfLongestSubstring(s) {
    let maxLen = 0;
    let start = 0;
    const seen = new Map();
    for (let end = 0; end < s.length; end++) {
        if (seen.has(s[end])) {
            start = Math.max(seen.get(s[end]) + 1, start);
        }
        seen.set(s[end], end);
        maxLen = Math.max(maxLen, end - start + 1);
    }
    return maxLen;
}

// Test cases
console.log(lengthOfLongestSubstring("abcabcbb"));  // Output: 3
console.log(lengthOfLongestSubstring("bbbbb"));     // Output: 1
console.log(lengthOfLongestSubstring("pwwkew"));    // Output: 3
console.log(lengthOfLongestSubstring(""));          // Output: 0
```

### Activity 3: Container with Most Water

**Task 3: Solve the "Container With Most Water" problem on LeetCode.**
- Write a function that takes an array of non-negative integers where each integer represents the height of a line drawn at each point. Find two lines that together with the x-axis form a container, such that the container holds the most water.
- Log the maximum amount of water for a few test cases.

```javascript
function maxArea(height) {
    let maxWater = 0;
    let left = 0;
    let right = height.length - 1;
    while (left < right) {
        const width = right - left;
        const minHeight = Math.min(height[left], height[right]);
        maxWater = Math.max(maxWater, width * minHeight);
        if (height[left] < height[right]) {
            left++;
        } else {
            right--;
        }
    }
    return maxWater;
}

// Test cases
console.log(maxArea([1, 8, 6, 2, 5, 4, 8, 3, 7]));  // Output: 49
console.log(maxArea([1, 1]));                      // Output: 1
console.log(maxArea([4, 3, 2, 1, 4]));             // Output: 16
```

### Activity 4: 3Sum

**Task 4: Solve the "3Sum" problem on LeetCode.**
- Write a function that takes an array of integers and finds all unique triplets in the array which give the sum of zero.
- Log the triplets for a few test cases, including edge cases.

```javascript
function threeSum(nums) {
    nums.sort((a, b) => a - b);
    const results = [];
    for (let i = 0; i < nums.length - 2; i++) {
        if (i > 0 && nums[i] === nums[i - 1]) continue;
        let left = i + 1;
        let right = nums.length - 1;
        while (left < right) {
            const sum = nums[i] + nums[left] + nums[right];
            if (sum === 0) {
                results.push([nums[i], nums[left], nums[right]]);
                while (left < right && nums[left] === nums[left + 1]) left++;
                while (left < right && nums[right] === nums[right - 1]) right--;
                left++;
                right--;
            } else if (sum < 0) {
                left++;
            } else {
                right--;
            }
        }
    }
    return results;
}

// Test cases
console.log(threeSum([-1, 0, 1, 2, -1, -4]));  // Output: [[-1, -1, 2], [-1, 0, 1]]
console.log(threeSum([]));                    // Output: []
console.log(threeSum([0]));                   // Output: []
```

### Activity 5: Group Anagrams

**Task 5: Solve the "Group Anagrams" problem on LeetCode.**
- Write a function that takes an array of strings and groups anagrams together.
- Log the grouped anagrams for a few test cases.

```javascript
function groupAnagrams(strs) {
    const map = new Map();
    for (let str of strs) {
        const sorted = str.split('').sort().join('');
        if (!map.has(sorted)) {
            map.set(sorted, []);
        }
        map.get(sorted).push(str);
    }
    return Array.from(map.values());
}

// Test cases
console.log(groupAnagrams(["eat", "tea", "tan", "ate", "nat", "bat"]));  
// Output: [["eat", "tea", "ate"], ["tan", "nat"], ["bat"]]
console.log(groupAnagrams([""]));                 
// Output: [[""]]
console.log(groupAnagrams(["a"]));                
// Output: [["a"]]
```

### Feature Request Scripts

1. **Add Two Numbers Script**

```javascript
class ListNode {
    constructor(val = 0, next = null) {
        this.val = val;
        this.next = next;
    }
}

function addTwoNumbers(l1, l2) {
    const dummy = new ListNode(0);
    let current = dummy;
    let carry = 0;
    while (l1 !== null || l2 !== null) {
        const x = l1 !== null ? l1.val : 0;
        const y = l2 !== null ? l2.val : 0;
        const sum = carry + x + y;
        carry = Math.floor(sum / 10);
        current.next = new ListNode(sum % 10);
        current = current.next;
        if (l1 !== null) l1 = l1.next;
        if (l2 !== null) l2 = l2.next;
    }
    if (carry > 0) {
        current.next = new ListNode(carry);
    }
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
const l1 = new ListNode(2, new ListNode(4, new ListNode(3)));
const l2 = new ListNode(5, new ListNode(6, new ListNode(4)));
const sumList = addTwoNumbers(l1, l2);
printList(sumList);  // Output: 7 -> 0 -> 8 -> null
```

2. **Longest Substring Script**

```javascript
function lengthOfLongestSubstring(s) {
    let maxLen = 0;
    let start = 0;
    const seen = new Map();
    for (let end = 0; end < s.length; end++) {
        if (seen.has(s[end])) {
            start = Math.max(seen.get(s[end]) + 1, start);
        }
        seen.set(s[end], end);
        maxLen = Math.max(maxLen, end - start + 1);
    }
    return maxLen;
}

// Test cases
console.log(lengthOfLongestSubstring("abcabcbb"));  // Output: 3
console.log(lengthOfLongestSubstring("bbbbb"));     // Output: 1


console.log(lengthOfLongestSubstring("pwwkew"));    // Output: 3
console.log(lengthOfLongestSubstring(""));          // Output: 0
```

3. **Container with Most Water Script**

```javascript
function maxArea(height) {
    let maxWater = 0;
    let left = 0;
    let right = height.length - 1;
    while (left < right) {
        const width = right - left;
        const minHeight = Math.min(height[left], height[right]);
        maxWater = Math.max(maxWater, width * minHeight);
        if (height[left] < height[right]) {
            left++;
        } else {
            right--;
        }
    }
    return maxWater;
}

// Test cases
console.log(maxArea([1, 8, 6, 2, 5, 4, 8, 3, 7]));  // Output: 49
console.log(maxArea([1, 1]));                      // Output: 1
console.log(maxArea([4, 3, 2, 1, 4]));             // Output: 16
```

4. **3Sum Script**

```javascript
function threeSum(nums) {
    nums.sort((a, b) => a - b);
    const results = [];
    for (let i = 0; i < nums.length - 2; i++) {
        if (i > 0 && nums[i] === nums[i - 1]) continue;
        let left = i + 1;
        let right = nums.length - 1;
        while (left < right) {
            const sum = nums[i] + nums[left] + nums[right];
            if (sum === 0) {
                results.push([nums[i], nums[left], nums[right]]);
                while (left < right && nums[left] === nums[left + 1]) left++;
                while (left < right && nums[right] === nums[right - 1]) right--;
                left++;
                right--;
            } else if (sum < 0) {
                left++;
            } else {
                right--;
            }
        }
    }
    return results;
}

// Test cases
console.log(threeSum([-1, 0, 1, 2, -1, -4]));  // Output: [[-1, -1, 2], [-1, 0, 1]]
console.log(threeSum([]));                    // Output: []
console.log(threeSum([0]));                   // Output: []
```

5. **Group Anagrams Script**

```javascript
function groupAnagrams(strs) {
    const map = new Map();
    for (let str of strs) {
        const sorted = str.split('').sort().join('');
        if (!map.has(sorted)) {
            map.set(sorted, []);
        }
        map.get(sorted).push(str);
    }
    return Array.from(map.values());
}

// Test cases
console.log(groupAnagrams(["eat", "tea", "tan", "ate", "nat", "bat"]));  
// Output: [["eat", "tea", "ate"], ["tan", "nat"], ["bat"]]
console.log(groupAnagrams([""]));                 
// Output: [[""]]
console.log(groupAnagrams(["a"]));                
// Output: [["a"]]
```

### Thats it for today
1. **Median of Two Sorted Arrays Script**

```javascript
function findMedianSortedArrays(nums1, nums2) {
    const merged = [];
    let i = 0, j = 0;
    
    while (i < nums1.length && j < nums2.length) {
        if (nums1[i] < nums2[j]) {
            merged.push(nums1[i]);
            i++;
        } else {
            merged.push(nums2[j]);
            j++;
        }
    }
    
    while (i < nums1.length) {
        merged.push(nums1[i]);
        i++;
    }
    
    while (j < nums2.length) {
        merged.push(nums2[j]);
        j++;
    }
    
    const mid = Math.floor(merged.length / 2);
    
    if (merged.length % 2 === 0) {
        return (merged[mid - 1] + merged[mid]) / 2;
    } else {
        return merged[mid];
    }
}

// Test cases
console.log(findMedianSortedArrays([1, 3], [2]));              // Output: 2.0
console.log(findMedianSortedArrays([1, 2], [3, 4]));           // Output: 2.5
console.log(findMedianSortedArrays([0, 0], [0, 0]));           // Output: 0.0
console.log(findMedianSortedArrays([], [1]));                  // Output: 1.0
console.log(findMedianSortedArrays([2], []));                  // Output: 2.0
```

2. **Merge k Sorted Lists Script**

```javascript
function mergeKLists(lists) {
    if (lists.length === 0) return null;
    
    const mergeTwoLists = (l1, l2) => {
        const dummy = new ListNode(0);
        let current = dummy;
        
        while (l1 !== null && l2 !== null) {
            if (l1.val < l2.val) {
                current.next = l1;
                l1 = l1.next;
            } else {
                current.next = l2;
                l2 = l2.next;
            }
            current = current.next;
        }
        
        if (l1 !== null) current.next = l1;
        if (l2 !== null) current.next = l2;
        
        return dummy.next;
    };
    
    while (lists.length > 1) {
        const l1 = lists.shift();
        const l2 = lists.shift();
        const mergedList = mergeTwoLists(l1, l2);
        lists.push(mergedList);
    }
    
    return lists[0];
}

// Test cases (Example usage with ListNode)
function ListNode(val, next = null) {
    this.val = val;
    this.next = next;
}

const list1 = new ListNode(1, new ListNode(4, new ListNode(5)));
const list2 = new ListNode(1, new ListNode(3, new ListNode(4)));
const list3 = new ListNode(2, new ListNode(6));

console.log(mergeKLists([list1, list2, list3])); // Output: Merged linked list
```

3. **Trapping Rain Water Script**

```javascript
function trap(height) {
    if (height.length === 0) return 0;
    
    let left = 0, right = height.length - 1;
    let leftMax = 0, rightMax = 0;
    let totalWater = 0;
    
    while (left < right) {
        if (height[left] < height[right]) {
            if (height[left] >= leftMax) {
                leftMax = height[left];
            } else {
                totalWater += leftMax - height[left];
            }
            left++;
        } else {
            if (height[right] >= rightMax) {
                rightMax = height[right];
            } else {
                totalWater += rightMax - height[right];
            }
            right--;
        }
    }
    
    return totalWater;
}

// Test cases
console.log(trap([0,1,0,2,1,0,1,3,2,1,2,1])); // Output: 6
console.log(trap([4,2,0,3,2,5]));             // Output: 9
```

4. **N-Queens Script**

```javascript
function solveNQueens(n) {
    const solutions = [];
    const board = Array(n).fill().map(() => Array(n).fill('.'));
    
    const isSafe = (row, col) => {
        for (let i = 0; i < row; i++) {
            if (board[i][col] === 'Q') return false;
            if (col - (row - i) >= 0 && board[i][col - (row - i)] === 'Q') return false;
            if (col + (row - i) < n && board[i][col + (row - i)] === 'Q') return false;
        }
        return true;
    };
    
    const solve = (row) => {
        if (row === n) {
            solutions.push(board.map(row => row.join('')));
            return;
        }
        for (let col = 0; col < n; col++) {
            if (isSafe(row, col)) {
                board[row][col] = 'Q';
                solve(row + 1);
                board[row][col] = '.';
            }
        }
    };
    
    solve(0);
    return solutions;
}

// Test cases
console.log(solveNQueens(4)); 
// Output: [[".Q..","...Q","Q...","..Q."],["..Q.","Q...","...Q",".Q.."]]
console.log(solveNQueens(1)); 
// Output: [["Q"]]
```

5. **Word Ladder Script**

```javascript
function ladderLength(beginWord, endWord, wordList) {
    const wordSet = new Set(wordList);
    if (!wordSet.has(endWord)) return 0;
    
    const queue = [[beginWord, 1]];
    
    while (queue.length > 0) {
        const [word, length] = queue.shift();
        
        for (let i = 0; i < word.length; i++) {
            for (let c = 97; c <= 122; c++) {
                const newWord = word.substring(0, i) + String.fromCharCode(c) + word.substring(i + 1);
                if (newWord === endWord) return length + 1;
                if (wordSet.has(newWord)) {
                    wordSet.delete(newWord);
                    queue.push([newWord, length + 1]);
                }
            }
        }
    }
    
    return 0;
}

// Test cases
console.log(ladderLength("hit", "cog", ["hot", "dot", "dog", "lot", "log", "cog"])); // Output: 5
console.log(ladderLength("hit", "cog", ["hot", "dot", "dog", "lot", "log"]));       // Output: 0
```

### Thats it for today

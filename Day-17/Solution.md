### Day 17: Data Structures

#### Activity 1: Linked List

**Task 1: Implement a Node class to represent an element in a linked list with properties `value` and `next`.**
```javascript
class Node {
    constructor(value) {
        this.value = value;
        this.next = null;
    }
}
```

**Task 2: Implement a LinkedList class with methods to add a node to the end, remove a node from the end, and display all nodes.**
```javascript
class LinkedList {
    constructor() {
        this.head = null;
    }

    add(value) {
        const newNode = new Node(value);
        if (!this.head) {
            this.head = newNode;
            return;
        }
        let current = this.head;
        while (current.next) {
            current = current.next;
        }
        current.next = newNode;
    }

    remove() {
        if (!this.head) {
            return;
        }
        if (!this.head.next) {
            this.head = null;
            return;
        }
        let current = this.head;
        while (current.next.next) {
            current = current.next;
        }
        current.next = null;
    }

    display() {
        let current = this.head;
        while (current) {
            console.log(current.value);
            current = current.next;
        }
    }
}

// Example usage:
const list = new LinkedList();
list.add(1);
list.add(2);
list.add(3);
list.display(); // Output: 1 2 3
list.remove();
list.display(); // Output: 1 2
```

#### Activity 2: Stack

**Task 3: Implement a Stack class with methods `push` (add element), `pop` (remove element), and `peek` (view the top element).**
```javascript
class Stack {
    constructor() {
        this.items = [];
    }

    push(element) {
        this.items.push(element);
    }

    pop() {
        if (this.items.length === 0) {
            return "Underflow";
        }
        return this.items.pop();
    }

    peek() {
        return this.items[this.items.length - 1];
    }
}

// Example usage:
const stack = new Stack();
stack.push(10);
stack.push(20);
console.log(stack.peek()); // Output: 20
stack.pop();
console.log(stack.peek()); // Output: 10
```

**Task 4: Use the Stack class to reverse a string by pushing all characters onto the stack and then popping them off.**
```javascript
function reverseString(str) {
    const stack = new Stack();
    for (let char of str) {
        stack.push(char);
    }
    let reversedStr = '';
    while (stack.items.length > 0) {
        reversedStr += stack.pop();
    }
    return reversedStr;
}

console.log(reverseString("hello")); // Output: "olleh"
```

#### Activity 3: Queue

**Task 5: Implement a Queue class with methods `enqueue` (add element), `dequeue` (remove element), and `front` (view the first element).**
```javascript
class Queue {
    constructor() {
        this.items = [];
    }

    enqueue(element) {
        this.items.push(element);
    }

    dequeue() {
        if (this.items.length === 0) {
            return "Underflow";
        }
        return this.items.shift();
    }

    front() {
        if (this.items.length === 0) {
            return "No elements in Queue";
        }
        return this.items[0];
    }
}

// Example usage:
const queue = new Queue();
queue.enqueue(10);
queue.enqueue(20);
console.log(queue.front()); // Output: 10
queue.dequeue();
console.log(queue.front()); // Output: 20
```

**Task 6: Use the Queue class to simulate a simple printer queue where print jobs are added to the queue and processed in order.**
```javascript
class PrinterQueue extends Queue {
    printJob(job) {
        this.enqueue(job);
        console.log(`Job "${job}" added to the queue.`);
    }

    processJob() {
        if (this.items.length === 0) {
            console.log("No jobs in the queue.");
            return;
        }
        const job = this.dequeue();
        console.log(`Processing job: "${job}"`);
    }
}

// Example usage:
const printer = new PrinterQueue();
printer.printJob("Document1");
printer.printJob("Document2");
printer.processJob(); // Output: Processing job: "Document1"
printer.processJob(); // Output: Processing job: "Document2"
printer.processJob(); // Output: No jobs in the queue.
```

#### Activity 4: Binary Tree

**Task 7: Implement a TreeNode class to represent a node in a binary tree with properties `value`, `left`, and `right`.**
```javascript
class TreeNode {
    constructor(value) {
        this.value = value;
        this.left = null;
        this.right = null;
    }
}
```

**Task 8: Implement a BinaryTree class with methods for inserting values and performing in-order traversal to display nodes.**
```javascript
class BinaryTree {
    constructor() {
        this.root = null;
    }

    insert(value) {
        const newNode = new TreeNode(value);
        if (this.root === null) {
            this.root = newNode;
            return;
        }
        this._insertNode(this.root, newNode);
    }

    _insertNode(node, newNode) {
        if (newNode.value < node.value) {
            if (node.left === null) {
                node.left = newNode;
            } else {
                this._insertNode(node.left, newNode);
            }
        } else {
            if (node.right === null) {
                node.right = newNode;
            } else {
                this._insertNode(node.right, newNode);
            }
        }
    }

    inOrderTraversal(node = this.root) {
        if (node !== null) {
            this.inOrderTraversal(node.left);
            console.log(node.value);
            this.inOrderTraversal(node.right);
        }
    }
}

// Example usage:
const tree = new BinaryTree();
tree.insert(10);
tree.insert(5);
tree.insert(15);
tree.inOrderTraversal(); // Output: 5 10 15
```

#### Activity 5: Graph (Optional)

**Task 9: Implement a Graph class with methods to add vertices, add edges, and perform a breadth-first search (BFS).**
```javascript
class Graph {
    constructor() {
        this.adjList = new Map();
    }

    addVertex(vertex) {
        if (!this.adjList.has(vertex)) {
            this.adjList.set(vertex, []);
        }
    }

    addEdge(vertex1, vertex2) {
        this.adjList.get(vertex1).push(vertex2);
        this.adjList.get(vertex2).push(vertex1); // For an undirected graph
    }

    bfs(startingNode) {
        let visited = {};
        let queue = [startingNode];

        visited[startingNode] = true;

        while (queue.length > 0) {
            let currentNode = queue.shift();
            console.log(currentNode);

            let neighbors = this.adjList.get(currentNode);
            for (let neighbor of neighbors) {
                if (!visited[neighbor]) {
                    visited[neighbor] = true;
                    queue.push(neighbor);
                }
            }
        }
    }
}

// Example usage:
const graph = new Graph();
graph.addVertex('A');
graph.addVertex('B');
graph.addVertex('C');
graph.addEdge('A', 'B');
graph.addEdge('A', 'C');
graph.bfs('A'); // Output: A B C
```

**Task 10: Use the Graph class to represent a simple network and perform BFS to find the shortest path between two nodes.**
```javascript
class GraphWithShortestPath extends Graph {
    findShortestPath(start, end) {
        let visited = {};
        let queue = [[start]];
        visited[start] = true;

        while (queue.length > 0) {
            let path = queue.shift();
            let node = path[path.length - 1];

            if (node === end) {
                return path;
            }

            let neighbors = this.adjList.get(node);
            for (let neighbor of neighbors) {
                if (!visited[neighbor]) {
                    visited[neighbor] = true;
                    let newPath = [...path, neighbor];
                    queue.push(newPath);
                }
            }
        }
        return null;
    }
}

// Example usage:
const graphPath = new GraphWithShortestPath();
graphPath.addVertex('A');
graphPath.addVertex('B');
graphPath.addVertex('C');
graphPath.addVertex('D');
graphPath.addEdge('A', 'B');
graphPath.addEdge('A', 'C');
graphPath.addEdge('B', 'D');
graphPath.addEdge('C', 'D');

console.log(graphPath.findShortestPath('A', 'D')); // Output: [ 'A', 'B', 'D' ] or [ 'A', 'C', 'D' ]
```

### Thats it for todya

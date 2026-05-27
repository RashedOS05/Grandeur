---
publish: true
created: 2025-05-06T17:15:24.103+03:00
modified: 2026-05-27T16:59:56.795+03:00
---

# Lists

- **Unsorted List** → fast insert, slow remove

- **Sorted List** → slow insert, fast remove

# Stack ADT

## LIFO (Last in first out)

## Push Pop Top

## Example Code:

public class SimpleStack {
private int maxSize;
private int\[] stackArray;
private int top;

```
public SimpleStack(int size) {
    maxSize = size;
    stackArray = new int[maxSize];
    top = -1; // empty stack
}

// Push operation
public void push(int value) {
    if (!isFull()) {
        top++;
        stackArray[top] = value;
    } else {
        System.out.println("Stack is full!");
    }
}

// Pop operation
public void pop() {
    if (!isEmpty()) {
        top--;
    } else {
        System.out.println("Stack is empty!");
    }
}

// Top operation
public int top() {
    if (!isEmpty()) {
        return stackArray[top];
    } else {
        System.out.println("Stack is empty!");
        return -1; // or throw an exception
    }
}

// Check if stack is empty
public boolean isEmpty() {
    return top == -1;
}

// Check if stack is full
public boolean isFull() {
    return top == maxSize - 1;
}

// Main method to test the stack
public static void main(String[] args) {
    SimpleStack stack = new SimpleStack(5);

    stack.push(10);
    stack.push(20);
    stack.push(30);

    System.out.println("Top element: " + stack.top()); // 30

    stack.pop();
    System.out.println("Top after pop: " + stack.top()); // 20

    while (!stack.isEmpty()) {
        System.out.println("Popping: " + stack.top());
        stack.pop();
    }

    stack.pop(); // Test popping from empty stack
}
```

}

# Recursive Function

`public static int factorial(int n) {   
`if (n == 0) return 1;\
`else return n * factorial(n - 1); }`
**Crucial: has a base case + calls itself**

# **Queue ADT**

- A **FIFO (First-In, First-Out)** structure.

- Elements are added to the **rear** and removed from the **front**.
  **Enqueue/Dequeue**

## **enqueue:**

`rear = (rear + 1) % elements.length; elements[rear] = element; numElements++;`

#

# BFS: Breadth First Search (Queue)

Basically, you go through all of the adjacent notes before diving deeper

# DFS: Depth First Search (Stack)

In contrary to BFS, once you pick a node, you pretty much double down on its path until you reach a dead end, then you continue with the other nodes. After you finish exploring the entire path, you go back one node (not to the beginning), and you deal with the ones you've missed, following the same method.![[Infrastructure/Attachments/image-2.png]]

# **Binary Tree Traversals**

- **Preorder**: Root → Left → Right\
  `D B A C F G`

- **Inorder**: Left → Root → Right\
  `A B C D F G`\
  (returns sorted order in BST)

- **Postorder**: Left → Right → Root\
  `A C B G F D`

# **Tree Modifications**

- **Insert**: Always added as a **leaf**.

- **Remove**:

  - **Leaf Node**: Just delete it.

  - **One Child**: Replace node with child.

  - **Two Children**: Replace with inorder predecessor/successor.

# Adjacency Matrix

a matrix list representing each node and its adjacencies.
![[Infrastructure/Attachments/image-5.png]]

# Adjacency List

a list of linked lists for each node illustrating the nodes it's adjacent to (even the ones that aren't adjacent to any).

![[Infrastructure/Attachments/image-4.png]]

# **Collision Resolution Strategies**

#### 1. **Chaining**

- Each index holds a linked list of entries.

- Pros: Simple.

- Cons: Extra memory for pointers.

- Average complexity: **O(n/m)**, where n = number of keys, m = table size.

#### 2. **Open Addressing**

- Stores all keys in the table itself.

- If a spot is taken, tries other spots using a **probing strategy**.

**Probing Types:**

- **Linear**: `h, h+1, h+2, ...`

- **Quadratic**: `h, h+1², h+2², ...`

- **Custom Step**: `h, h+k, h+2k, ...`

**Downside**: Deletion is tricky and may break probing chains.

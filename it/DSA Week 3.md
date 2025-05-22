
# Hashing

## Introduction to Hashing

Hashing is a technique used to uniquely identify a specific object from a group of similar objects. A good example is storing phone numbers in a database to check if a number already exists.

### Motivation:
Suppose we need to store **phone numbers** and perform **insert** and **search** operations.

- **Array:** Needs sorting for efficient search → O(log n) for binary search.
- **Linked List:** Unsorted → O(n) search time.
- **Binary Search Tree (BST):** O(log n) on average, but can be O(n) if unbalanced.
- **Direct Access Table:** Needs table of size = max value of key → infeasible for large keys (e.g., 10-digit phone numbers).

### Hashing:
Hashing solves these issues by mapping keys to indices of an array using a **hash function**.

## Hash Function

A **hash function** \( h(x) \) maps a large key space to a smaller range.

### Desired Properties:
- Fast and easy to compute.
- Uniform distribution of keys to avoid clustering.

### Example:
Bad hash function: `h(x) = 1` maps all keys to index 1 → causes collisions.

## Hash Table

A **hash table** is a data structure that maps keys to values using a hash function.

```text
Insert/Search/Delete operations ideally in O(1) time.
```

## Collision Handling Techniques

### 1. Chaining

Each array index points to a linked list of entries with the same hash.

#### Advantages:
- Simple to implement.
- Handles more elements than array size.

#### Drawbacks:
- Extra memory for pointers.
- Performance degrades with many collisions.

### 2. Open Addressing

All elements are stored in the hash table itself. On collision, probe for the next available slot.

#### Steps:
- **Insert:** Probe for the next empty slot.
- **Search:** Follow the probe sequence until the key is found or an empty slot is encountered.
- **Delete:** Use a special "deleted" marker.

### Probing Methods

#### a. Linear Probing

In linear probing, we linearly probe for the next slot. For example, the typical gap between
the two probes is 1 as taken in the below example also.
let hash(x) be the slot index computed using a hash function and S be the table size.

```text
If slot hash(x) % S is full, then we try (hash(x) + 1) % S
If (hash(x) + 1) % S is also full, then we try (hash(x) + 2) % S
If (hash(x) + 2) % S is also full, then we try (hash(x) + 3) % S
..................................................
..................................................
```
Let us consider a simple hash function as “key mod 7” and a sequence of keys as 50, 700,
76, 85, 92, 73, 101.

![image](https://github.com/user-attachments/assets/2bb5d8d7-90da-452d-b241-684259786047)


- Simple, fast cache performance.
- Suffers from **primary clustering**.

#### b. Quadratic Probing
```text
h(k, i) = (h(k) + c1 * i + c2 * i^2) % m
```
- Reduces clustering.
- May not find a slot if table is more than half full.

#### c. Double Hashing
```text
h(k, i) = (h1(k) + i * h2(k)) % m
```
- Best distribution.
- No clustering if `h2(k)` is relatively prime to table size.

## Comparison: Probing Techniques

| Technique         | Cache Performance | Clustering       | Cost          |
|-------------------|-------------------|------------------|---------------|
| Linear Probing    | Best              | Primary          | Low           |
| Quadratic Probing | Moderate          | Secondary        | Moderate      |
| Double Hashing    | Moderate          | None             | High (2 hashes)|

## Chaining vs Open Addressing

| Feature                 | Chaining                      | Open Addressing              |
|-------------------------|-------------------------------|-------------------------------|
| Implementation          | Simple with linked list       | More complex probing logic    |
| Space Usage             | Extra space for pointers      | More space efficient          |
| Max Keys Supported      | More than table size          | Up to table size              |
| Cache Performance       | Poor (pointer access)         | Good (sequential memory)      |
| Load Factor Sensitivity | Less                          | High                          |
| Deletion Complexity     | Easy                          | Requires "deleted" markers    |

### Performance of Open Addressing:

Like Chaining, the performance of hashing can be evaluated under the assumption that
each key is equally likely to be hashed to any slot of the table (simple uniform hashing).

``` m = Number of slots in the hash table
n = Number of keys to be inserted in the hash table
Load factor α = n/m ( < 1 )
Expected time to search/insert/delete < 1/(1 - α)
So Search, Insert and Delete take (1/(1 - α)) time
```
---
## Performance and Load Factor

Let:
- \( m \) = number of slots in hash table.
- \( n \) = number of stored keys.
- \( \alpha = n/m \) = **load factor**.

### Expected Time for Search in Open Addressing:
```text
Expected Time ≈ 1 / (1 - α)
```
- As α approaches 1, time increases significantly.
- Best performance when α is kept below 0.7.

---

## Problems On Hashing
1. https://leetcode.com/problems/two-sum/
2. https://leetcode.com/problems/intersection-of-two-arrays/
3. https://www.geeksforgeeks.org/find-whether-an-array-is-subset-of-another-array-set-1/
4. https://www.geeksforgeeks.org/maximum-distance-two-occurrences-element-array/
5. https://leetcode.com/problems/find-the-difference-of-two-arrays/description/
6. https://leetcode.com/problems/intersection-of-two-arrays/description/
7. https://leetcode.com/problems/subarray-sum-equals-k/description/
8. https://leetcode.com/problems/frequency-of-the-most-frequent-element/description/


## Summary

Hashing provides fast access and insertion with O(1) time on average, making it ideal for sets, maps, and caches. Proper choice of hash function and collision resolution technique is key to performance.

---
# Recursion

The process in which a function calls itself directly or indirectly is called recursion and the corresponding function is called a recursive function.

- A recursive algorithm takes one step toward solution and then recursively call itself to further move. The algorithm stops once we reach the solution.
- Since called function may further call itself, this process might continue forever. So it is essential to provide a base case to terminate this recursion process.

Steps to Implement Recursion

Step1 - Define a base case: Identify the simplest (or base) case for which the solution is known or trivial. This is the stopping condition for the recursion, as it prevents the function from infinitely calling itself.
Step2 - Define a recursive case: Define the problem in terms of smaller subproblems. Break the problem down into smaller versions of itself, and call the function recursively to solve each subproblem.
Step3 - Ensure the recursion terminates: Make sure that the recursive function eventually reaches the base case, and does not enter an infinite loop.
Step4 - Combine the solutions: Combine the solutions of the subproblems to solve the original problem.

### What is the base condition in recursion? 
A recursive program stops at a base condition. There can be more than one base conditions in a recursion. In the above program, the base condition is when n = 1.

### How a particular problem is solved using recursion? 
The idea is to represent a problem in terms of one or more smaller problems, and add one or more base conditions that stop the recursion.  

### When does Stack Overflow error occur in recursion? 
If the base case is not reached or not defined, then the stack overflow problem may arise. Let us take an example to understand this.

```
int fact(int n)
{
    // wrong base case (it may cause stack overflow).
    if (n == 100) 
        return 1;
    else
        return n*fact(n-1);
}
```

- In this example, if fact(10) is called, the function will recursively call fact(9), then fact(8), fact(7), and so on. However, the base case checks if n == 100. Since n will never reach 100 during these recursive calls, the base case is never triggered. As a result, the recursion continues indefinitely.
- This continuous recursion consumes memory on the function call stack. If the system's memory is exhausted due to these unending function calls, a stack overflow error occurs.
- To prevent this, it's essential to define a proper base case, such as if (n == 0) to ensure that the recursion terminates and the function doesn't run out of memory.

 No.	Recursion	                                                    Iteration
1)	Terminates when the base case becomes true.	                 Terminates when the loop condition becomes false.
2)	Logic is built in terms of smaller problems.                 Logic is built using iterating over something.
3)	Every recursive call needs extra space in the stack memory.	 Every iteration does not require any extra space.
4)	Smaller code size.	                                         Larger code size.

## Recursion and backtracking 
They are powerful algorithmic techniques in DSA used to solve complex problems by breaking them down into smaller subproblems and exploring all possible solutions systematically. Recursion involves a function calling itself, while backtracking uses recursion to explore a decision tree, undoing previous choices when a solution isn't found. 

###Recursion:
Definition: A function calling itself within its own definition. 
Purpose: To solve problems by breaking them into smaller, similar subproblems. 
Key Components:
Base Case: The condition that stops the recursion. 
Recursive Case: The part of the function that calls itself. 
Example: Calculating factorial, Fibonacci sequence, or traversing a tree. 

###Backtracking:
Definition:
A systematic approach to exploring all possible solutions to a problem, often using recursion. 
Purpose:
To find solutions by trying different options, undoing choices when they lead to dead ends. 
Key Concepts:
Decision Tree: Backtracking explores a decision tree, where each node represents a choice. 
Exploration: It systematically tries different paths (choices) to find a solution. 
Undo (Backtrack): If a path doesn't lead to a solution, it returns to a previous choice and tries a different path. 
Example:
N-Queens problem, Sudoku solver, finding all permutations. 

### Differences between Recursion and Backtracking:
Purpose:
Recursion focuses on solving problems by breaking them down, while backtracking focuses on exploring all possible solutions. 
Scope:
Recursion can be used in various scenarios, while backtracking is more specialized for problems with a vast solution space. 
Complexity:
Backtracking can have higher time complexity (e.g., O(n!), according to GeeksforGeeks) depending on the problem, while recursion usually has O(n) stack space. 

Advantages of Recursion:
Elegant Solutions:
Recursion can provide concise and elegant solutions for problems that can be naturally broken down.
Simpler Code:
In some cases, recursive code can be easier to understand and maintain than iterative code. 

Disadvantages of Recursion:
Memory Overhead:
Recursive function calls create stack frames, which can consume memory, especially for deep recursion. 
Stack Overflow:
If there's no base case or if the recursion is too deep, a stack overflow error can occur. 

Advantages of Backtracking:
Systematic Exploration: Backtracking provides a structured way to explore all possible solutions. 
Constraint Satisfaction: Backtracking is well-suited for problems where constraints need to be considered during solution exploration. 

Disadvantages of Backtracking:
High Complexity:
Backtracking can have high time and space complexity, especially for problems with a large solution space. 
Potentially Slow:
Backtracking might not be efficient for all problems, and optimization techniques might be necessary. 

#  Tree Traversals and Recursive Implementations (Detailed Notes)

##  Introduction to Trees

A **Tree** is a hierarchical, non-linear data structure that consists of **nodes** connected by **edges**. It is widely used in representing hierarchical data like file systems, organization charts, etc.

### Key Terminologies:
- **Root**: The topmost node of the tree (only one root in a tree).
- **Leaf**: A node that does not have any children.
- **Internal Node**: A node with at least one child.
- **Parent**: A node that has branches to other nodes.
- **Child**: A node that descends from another node.
- **Subtree**: A tree formed by a node and its descendants.

---

##  Depth of a Tree

###  Max Depth of a Binary Tree

The **maximum depth** or **height** of a binary tree is the number of nodes along the longest path from the root node down to the farthest leaf node.

#### Recursive Logic:
At each node, recursively calculate the depth of its left and right subtrees. The max depth is 1 (for current node) + the greater of the two depths.

```cpp
int maxDepth(TreeNode* root) {
    if (!root) return 0;
    return 1 + max(maxDepth(root->left), maxDepth(root->right));
}
```
 [Leetcode: Maximum Depth of Binary Tree](https://leetcode.com/problems/maximum-depth-of-binary-tree/)

---

###  Max Depth of an N-ary Tree

Same principle as binary trees but the node can have more than two children.

#### Recursive Logic:
Traverse each child recursively, and keep track of the maximum depth obtained.

```cpp
int maxDepth(Node* root) {
    if (!root) return 0;
    int depth = 0;
    for (auto child : root->children)
        depth = max(depth, maxDepth(child));
    return 1 + depth;
}
```
 [Leetcode: Maximum Depth of N-ary Tree](https://leetcode.com/problems/maximum-depth-of-n-ary-tree/)

---

## Tree Traversals

**Tree traversal** means visiting every node in the tree exactly once in a specific order.

###  Preorder Traversal

- Visit the **root** node.
- Traverse the **left** subtree.
- Traverse the **right** subtree.

#### Binary Tree Preorder Example:
```cpp
void preorder(TreeNode* root) {
    if (!root) return;
    cout << root->val << " ";
    preorder(root->left);
    preorder(root->right);
}
```
 [Binary Tree Preorder Traversal](https://leetcode.com/problems/binary-tree-preorder-traversal/)

#### N-ary Tree Preorder Example:
```cpp
void preorder(Node* root) {
    if (!root) return;
    cout << root->val << " ";
    for (auto child : root->children)
        preorder(child);
}
```
 [N-ary Tree Preorder Traversal](https://leetcode.com/problems/n-ary-tree-preorder-traversal/)

---

###  Postorder Traversal

- Traverse the **left** subtree.
- Traverse the **right** subtree.
- Visit the **root** node.

#### Binary Tree Postorder Example:
```cpp
void postorder(TreeNode* root) {
    if (!root) return;
    postorder(root->left);
    postorder(root->right);
    cout << root->val << " ";
}
```
 [Binary Tree Postorder Traversal](https://leetcode.com/problems/binary-tree-postorder-traversal/)

#### N-ary Tree Postorder Example:
```cpp
void postorder(Node* root) {
    if (!root) return;
    for (auto child : root->children)
        postorder(child);
    cout << root->val << " ";
}
```
 [N-ary Tree Postorder Traversal](https://leetcode.com/problems/n-ary-tree-postorder-traversal/)

---

###  Inorder Traversal

Inorder traversal is mainly defined for **binary trees**.

- Traverse the **left** subtree.
- Visit the **root** node.
- Traverse the **right** subtree.

#### Binary Tree Inorder Example:
```cpp
void inorder(TreeNode* root) {
    if (!root) return;
    inorder(root->left);
    cout << root->val << " ";
    inorder(root->right);
}
```
 [Binary Tree Inorder Traversal](https://leetcode.com/problems/binary-tree-inorder-traversal/)

---

###  Inorder Traversal for N-ary Trees

For N-ary trees, the approach is:
- Visit all children **except the last**.
- Visit the root.
- Visit the **last** child.

#### Example:
```cpp
void inorder(Node* node) {
    if (!node) return;
    int total = node->length;
    for (int i = 0; i < total - 1; i++)
        inorder(node->children[i]);
    cout << node->data << " ";
    inorder(node->children[total - 1]);
}
```

---

##  Summary of Traversals

| Traversal   | Binary Tree Order     | N-ary Tree Order                                   |
|-------------|------------------------|----------------------------------------------------|
| Preorder    | Root → Left → Right    | Root → Children (Left to Right)                    |
| Inorder     | Left → Root → Right    | Children (except last) → Root → Last child         |
| Postorder   | Left → Right → Root    | Children → Root                                    |

## Practice examples on Trees
1. https://leetcode.com/problems/maximum-depth-of-binary-tree/
2. https://leetcode.com/problems/binary-tree-inorder-traversal/
3. https://leetcode.com/problems/invert-binary-tree/
4. https://leetcode.com/problems/symmetric-tree/
5. https://leetcode.com/problems/same-tree/
6. https://leetcode.com/problems/path-sum/
7. https://leetcode.com/problems/construct-binary-tree-from-inorder-and-postorder-traversal/
8. https://leetcode.com/problems/construct-binary-tree-from-preorder-and-inorder-traversal/
9. https://leetcode.com/problems/validate-binary-search-tree/
10. https://leetcode.com/problems/delete-node-in-a-bst/
11. https://leetcode.com/problems/two-sum-iv-input-is-a-bst/
12. https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-search-tree/

---


##  Backtracking Principles

**Backtracking** is a refinement of the brute-force approach where we explore all possible solutions but "backtrack" when a decision leads to an invalid or suboptimal solution.

### Where Trees & Backtracking Intersect:
- **Recursive calls** represent choices.
- **Backtracking** happens when we undo a decision (return from a recursive call).
- Common in problems like:
  - Path Sum
  - Generating all root-to-leaf paths
  - Subtree matching, etc.

###  Template for Backtracking in Trees:
```cpp
void dfs(TreeNode* root, vector<int>& path) {
    if (!root) return;

    // Choose
    path.push_back(root->val);

    // Explore
    if (!root->left && !root->right) {
        // Reached leaf, do something with path
    }
    dfs(root->left, path);
    dfs(root->right, path);

    // Un-choose (Backtrack)
    path.pop_back();
}
```

###  Example: All Root-to-Leaf Paths
```cpp
void getPaths(TreeNode* root, vector<int>& path, vector<vector<int>>& result) {
    if (!root) return;
    path.push_back(root->val);

    if (!root->left && !root->right)
        result.push_back(path);
    else {
        getPaths(root->left, path, result);
        getPaths(root->right, path, result);
    }

    path.pop_back(); // backtrack
}
```
## Practice Problems on Recursive Backtracking
1. https://leetcode.com/problems/subsets/
2. https://leetcode.com/problems/n-queens/
3. https://leetcode.com/problems/sudoku-solver/
4. https://leetcode.com/problems/permutations/
5. https://leetcode.com/problems/combination-sum/
6. https://leetcode.com/problems/palindrome-partitioning/
7. https://leetcode.com/problems/word-search/
8. https://leetcode.com/problems/letter-combinations-of-a-phone-number/

---

##  Summary

| Concept       | Key Point |
|---------------|-----------|
| **Recursion** | Natural for tree navigation due to self-similar structure |
| **Traversal** | Changing order of function calls alters traversal type |
| **Backtracking** | Used in recursive tree exploration to undo choices |
| **Use Cases** | Path generation, tree construction, matching, pruning invalid states |

---


#  Recursion Tree Method for Solving Time Complexity Recurrence Relations

The **Recursion Tree Method** is a visual technique used to determine the time complexity of recurrence relations.

---

##  Steps to Solve Using Recursion Tree:

1. **Draw the recursive tree** for the recurrence.
2. **Calculate the cost at each level** and **count total levels**.
3. **Determine the number of nodes** and the **cost at the last level**.
4. **Sum up the cost of all levels** to get total complexity.

---

##  Example 1: T(n) = 2T(n/2) + c

### Step 1: Draw Recursion Tree
Each call splits into two calls of size `n/2`, incurring a constant cost `c` at each level.

### Step 2: Calculate Work at Each Level
- Level 0: 1 node → cost = c
- Level 1: 2 nodes → cost = 2c
- Level 2: 4 nodes → cost = 4c
- ...
- Level k: 2^k nodes → cost = 2^k * c

### Total levels:
```
n / 2^k = 1 → 2^k = n → k = log₂(n)
Total levels = k + 1 = log₂(n) + 1
```

### Step 3: Cost of Last Level
```
# of nodes = 2^k = n
Each node cost = Θ(1)
Total cost = Θ(n)
```

### Step 4: Sum the Costs
```
T(n) = c + 2c + 4c + ... + n = c(1 + 2 + 4 + ... + 2^k)
Using GP formula → Sum = 2^{k+1} - 1 ≈ 2n → Θ(n)
T(n) = Θ(n)
```

---

##  Example 2: T(n) = T(n/10) + T(9n/10) + n

### Step 1: Draw Recursion Tree
Skewed recursion tree:
- Left child = T(n/10)
- Right child = T(9n/10)
- Total cost at each level = n

### Step 2: Calculate Number of Levels
```
Choose longest path: repeatedly taking 9n/10 path
(9/10)^k * n = 1 → k = log_{10/9}(n)
Total levels = log_{10/9}(n) + 1
```

### Step 3: Cost of Last Level
- Only a constant number of nodes → Θ(1) work

### Step 4: Sum Costs
```
T(n) < cn + cn + ... (log_{10/9}(n) times) + Θ(1)
T(n) = O(n log_{10/9}(n))
```

---

##  Summary

| Recurrence                      | Time Complexity       | Reasoning                                 |
|----------------------------------|------------------------|--------------------------------------------|
| T(n) = 2T(n/2) + c              | Θ(n)                  | Geometric growth in calls, total cost = n |
| T(n) = T(n/10) + T(9n/10) + n   | O(n log_{10/9}(n))    | Log-depth skewed tree with n cost per level |

 **Tip**: If summing all levels is complex, estimate upper bounds using full tree or geometric series.

---

# Competitive Programming Notes

Competitive programming involves solving algorithmic problems under constraints, with a focus on time and space efficiency. It emphasizes writing correct, optimal solutions within a limited time. This plan covers the most frequent patterns seen in interviews and contests, including algorithmic design, data structure mastery, and problem-solving strategies. These notes are written to help students grasp core ideas and sense how each concept contributes to efficient problem-solving.

---

# Arrays & Strings

Arrays are fundamental because they provide indexed access to a collection of elements. You'll encounter problems like finding subarrays with certain properties or manipulating elements in place.

* **Prefix Sum**: Build an array where each position holds the sum of all previous elements. Helps in constant-time subarray sum queries.
* **Sliding Window**: Move a fixed-size or dynamic-size window through an array to track or optimize subarray properties (sum, count, etc.).
* **Two Pointers**: Efficient for sorted arrays to perform linear-time comparisons.

Strings, though similar to arrays, often deal with character frequency, pattern detection, and transformation:

* **Character Frequency**: Helps in checking anagrams or counting specific letters.
* **String Matching**: Brute force methods are slow; advanced techniques (KMP, Rabin-Karp) improve performance.
* **Palindrome Checking**: Often involves comparing characters symmetrically or using dynamic programming.

---

# Linked Lists

Linked Lists are dynamic structures where elements point to the next. Useful in situations requiring constant-time insertions/deletions.

* **Reversing a List**: Core pointer manipulation skill.
* **Cycle Detection**: Detect loops using two pointers moving at different speeds.
* **Middle of List**: Fast-slow pointer trick helps find the middle node efficiently.
* **Merge Sorted Lists**: Requires careful pointer adjustments, especially in recursive formats.

Linked lists also build intuition for handling nulls, pointers, and edge cases.

---

# Trees

Trees represent hierarchical structures. Binary trees are the most tested form.

* **Traversals**: Pre-order (process before children), In-order (for BSTs: sorted output), Post-order (process children before node).
* **Level Order (BFS)**: Uses queues to explore nodes level by level.
* **BST Properties**: Left subtree < Node < Right subtree; useful in search and sorting.
* **Path-Based Problems**: Like max sum from root to leaf, or diameter between nodes.

Recursive and stack-based approaches often apply here.

---

# Binary Search

An essential divide-and-conquer technique, applied to sorted data or monotonic functions.

* **Standard Search**: Finds an element in log(n) time.
* **Rotated Arrays**: Binary search can adapt to rotated sorted inputs.
* **Search on Answer**: Instead of a concrete array, you search the *range* of values.

Understanding when to move the left/right pointers is crucial.

---

# Sliding Window

Used to optimize problems involving contiguous subarrays.

* **Fixed Window**: For problems where size is fixed (e.g., max sum of size k).
* **Dynamic Window**: Useful for problems like longest substring without repeating characters.
* **Hash Maps**: Often used to track frequencies in a window.

Requires careful start/end pointer management to expand and shrink windows.

---

# Two Pointers

Two indices move independently or together to achieve the goal.

* **In-Place Operations**: Like removing duplicates.
* **Sorted Array Use**: Merging, searching pairs, or triplets.
* **Partitioning**: Grouping values below and above a pivot.

Commonly appears in combination with sorting or greedy strategies.

---

# Stack

Stacks hold data in LIFO order. They're useful when the most recent item is needed next.

* **Monotonic Stack**: Maintains increasing or decreasing order for solving range maximum/minimum problems.
* **Expression Evaluation**: Converts infix to postfix or handles parenthesis evaluation.
* **Simulating Recursion**: Non-recursive DFS and backtracking.

Also used in problems like stock span, histogram area, etc.

---

# Heap / Priority Queue

A special tree-based structure to efficiently get min or max elements.

* **Min Heap**: Used in Dijkstra’s algorithm and finding smallest values.
* **Kth Largest/Smallest**: Maintain a heap of size k for efficiency.
* **Merging Sorted Lists**: Heaps help in merging efficiently.

Good for scenarios with dynamically updating streams.

---

# Graphs (BFS/DFS)

Graphs model relationships and connections. Traversals help explore or analyze such structures.

* **DFS**: Goes deep before backtracking. Useful in components and cycle detection.
* **BFS**: Explores level by level. Best for shortest path in unweighted graphs.
* **Topological Sort**: Orders tasks with dependencies (DAGs).
* **Connected Components**: Group all reachable nodes.

Know how to represent graphs using adjacency lists or matrices.

---

# Dynamic Programming

DP is used to solve problems with overlapping subproblems and optimal substructure.

* **Memoization**: Save results of recursive calls to avoid recomputation.
* **Tabulation**: Iterative bottom-up approach.
* **State Identification**: Define what each subproblem represents.

Useful in problems like:

* **Knapsack**: Max value under weight constraint.
* **Subsequences**: LCS, LIS, etc.
* **Partitioning**: Divide arrays under rules.

Understanding transitions is critical to mastering DP.

---

# Trie / String Matching

Trie is a tree where nodes represent prefixes.

* **Auto-complete**: Suggest words based on prefix.
* **Validation**: Check if word exists in a set efficiently.
* **Word Search**: In 2D grids, using Trie reduces time.

String matching also includes:

* **KMP**: Avoids redundant comparisons.
* **Aho-Corasick**: For multiple pattern matching.

Great for dictionary-based problems.

---

# Greedy

Greedy algorithms build up a solution piece by piece by choosing the best local option.

* **Activity Selection**: Choose max non-overlapping intervals.
* **Huffman Encoding**: Build optimal prefix codes.
* **Fractional Knapsack**: Take the best density items first.

Requires proving that local choices lead to global optimality.

---

# Backtracking

Explores all possibilities by choosing an option and reverting if needed.

* **Permutations/Combinations**: Try placing one element at a time.
* **Sudoku Solver**: Try filling numbers with constraints.
* **N-Queens**: Place queens without attacking each other.

Key is to prune branches that are guaranteed to fail.

---

# Practise Problems

### **1. Array & String**
1. [Two Sum](https://leetcode.com/problems/two-sum/)
2. [Best Time to Buy and Sell Stock](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/)
3. [Contains Duplicate](https://leetcode.com/problems/contains-duplicate/)
4. [Product of Array Except Self](https://leetcode.com/problems/product-of-array-except-self/)
5. [Maximum Subarray](https://leetcode.com/problems/maximum-subarray/)
6. [Maximum Product Subarray](https://leetcode.com/problems/maximum-product-subarray/)
7. [3Sum](https://leetcode.com/problems/3sum/)
8. [Set Matrix Zeroes](https://leetcode.com/problems/set-matrix-zeroes/)
9. [Rotate Image](https://leetcode.com/problems/rotate-image/)
10. [Spiral Matrix](https://leetcode.com/problems/spiral-matrix/)

---

### **2. Linked List**
11. [Reverse Linked List](https://leetcode.com/problems/reverse-linked-list/)
12. [Merge Two Sorted Lists](https://leetcode.com/problems/merge-two-sorted-lists/)
13. [Linked List Cycle](https://leetcode.com/problems/linked-list-cycle/)
14. [Palindrome Linked List](https://leetcode.com/problems/palindrome-linked-list/)
15. [Add Two Numbers](https://leetcode.com/problems/add-two-numbers/)
16. [Remove Nth Node From End of List](https://leetcode.com/problems/remove-nth-node-from-end-of-list/)
17. [Reorder List](https://leetcode.com/problems/reorder-list/)

---

### **3. Tree**
18. [Maximum Depth of Binary Tree](https://leetcode.com/problems/maximum-depth-of-binary-tree/)
19. [Same Tree](https://leetcode.com/problems/same-tree/)
20. [Invert Binary Tree](https://leetcode.com/problems/invert-binary-tree/)
21. [Binary Tree Maximum Path Sum](https://leetcode.com/problems/binary-tree-maximum-path-sum/)
22. [Binary Tree Level Order Traversal](https://leetcode.com/problems/binary-tree-level-order-traversal/)
23. [Serialize and Deserialize Binary Tree](https://leetcode.com/problems/serialize-and-deserialize-binary-tree/)
24. [Subtree of Another Tree](https://leetcode.com/problems/subtree-of-another-tree/)
25. [Construct Binary Tree from Preorder and Inorder Traversal](https://leetcode.com/problems/construct-binary-tree-from-preorder-and-inorder-traversal/)

---

### **4. Binary Search**
26. [Binary Search](https://leetcode.com/problems/binary-search/)
27. [Search a 2D Matrix](https://leetcode.com/problems/search-a-2d-matrix/)
28. [Find Minimum in Rotated Sorted Array](https://leetcode.com/problems/find-minimum-in-rotated-sorted-array/)
29. [Search in Rotated Sorted Array](https://leetcode.com/problems/search-in-rotated-sorted-array/)
30. [Time Based Key-Value Store](https://leetcode.com/problems/time-based-key-value-store/)

---

### **5. Sliding Window**
31. [Minimum Window Substring](https://leetcode.com/problems/minimum-window-substring/)
32. [Longest Substring Without Repeating Characters](https://leetcode.com/problems/longest-substring-without-repeating-characters/)
33. [Longest Repeating Character Replacement](https://leetcode.com/problems/longest-repeating-character-replacement/)
34. [Permutation in String](https://leetcode.com/problems/permutation-in-string/)
35. [Sliding Window Maximum](https://leetcode.com/problems/sliding-window-maximum/)

---

### **6. Two Pointers**
36. [Valid Palindrome](https://leetcode.com/problems/valid-palindrome/)
37. [3Sum](https://leetcode.com/problems/3sum/)
38. [Container With Most Water](https://leetcode.com/problems/container-with-most-water/)
39. [Trapping Rain Water](https://leetcode.com/problems/trapping-rain-water/)
40. [Remove Duplicates from Sorted Array](https://leetcode.com/problems/remove-duplicates-from-sorted-array/)

---

### **7. Stack**
41. [Valid Parentheses](https://leetcode.com/problems/valid-parentheses/)
42. [Min Stack](https://leetcode.com/problems/min-stack/)
43. [Daily Temperatures](https://leetcode.com/problems/daily-temperatures/)
44. [Car Fleet](https://leetcode.com/problems/car-fleet/)
45. [Evaluate Reverse Polish Notation](https://leetcode.com/problems/evaluate-reverse-polish-notation/)

---

### **8. Heap / Priority Queue**
46. [Merge k Sorted Lists](https://leetcode.com/problems/merge-k-sorted-lists/)
47. [Top K Frequent Elements](https://leetcode.com/problems/top-k-frequent-elements/)
48. [Find Median from Data Stream](https://leetcode.com/problems/find-median-from-data-stream/)

---

### **9. Graph / BFS / DFS**
49. [Clone Graph](https://leetcode.com/problems/clone-graph/)
50. [Course Schedule](https://leetcode.com/problems/course-schedule/)
51. [Pacific Atlantic Water Flow](https://leetcode.com/problems/pacific-atlantic-water-flow/)
52. [Number of Islands](https://leetcode.com/problems/number-of-islands/)
53. [Longest Consecutive Sequence](https://leetcode.com/problems/longest-consecutive-sequence/)
54. [Alien Dictionary](https://leetcode.com/problems/alien-dictionary/)

---

### **10. Dynamic Programming**
55. [Climbing Stairs](https://leetcode.com/problems/climbing-stairs/)
56. [Coin Change](https://leetcode.com/problems/coin-change/)
57. [Longest Increasing Subsequence](https://leetcode.com/problems/longest-increasing-subsequence/)
58. [Longest Common Subsequence](https://leetcode.com/problems/longest-common-subsequence/)
59. [Word Break](https://leetcode.com/problems/word-break/)
60. [Combination Sum](https://leetcode.com/problems/combination-sum/)
61. [House Robber](https://leetcode.com/problems/house-robber/)
62. [House Robber II](https://leetcode.com/problems/house-robber-ii/)
63. [Decode Ways](https://leetcode.com/problems/decode-ways/)
64. [Unique Paths](https://leetcode.com/problems/unique-paths/)
65. [Jump Game](https://leetcode.com/problems/jump-game/)

---

### **11. Trie / String Matching**
66. [Implement Trie](https://leetcode.com/problems/implement-trie-prefix-tree/)
67. [Add and Search Word - Data structure design](https://leetcode.com/problems/add-and-search-word-data-structure-design/)
68. [Word Search II](https://leetcode.com/problems/word-search-ii/)

---

### **12. Greedy**
69. [Gas Station](https://leetcode.com/problems/gas-station/)
70. [Jump Game II](https://leetcode.com/problems/jump-game-ii/)
71. [Merge Intervals](https://leetcode.com/problems/merge-intervals/)
72. [Insert Interval](https://leetcode.com/problems/insert-interval/)
73. [Non-overlapping Intervals](https://leetcode.com/problems/non-overlapping-intervals/)

---

### **13. Backtracking**
74. [Subsets](https://leetcode.com/problems/subsets/)
75. [Word Search](https://leetcode.com/problems/word-search/)

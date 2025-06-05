# Competitive Programming Notes

Competitive programming involves solving algorithmic problems under constraints, with a focus on time and space efficiency. This plan covers the most frequent patterns seen in interviews and contests.

# Arrays & Strings

Arrays are the foundation of most problems. Key techniques include prefix sums, sliding windows, and two-pointer methods.

Strings require manipulation and understanding of memory and traversal, often used in problems like anagrams, palindromes, and pattern matching.

# Linked Lists

Linked Lists are crucial for understanding pointers and memory management.

Problems often focus on reversing, detecting cycles (Floyd’s Algorithm), and merging sorted lists.

# Trees

Tree traversal (in-order, pre-order, post-order) is foundational.

Recursive thinking is key. Concepts like DFS/BFS, height calculation, and subtree comparison are core.

# Binary Search

A divide-and-conquer strategy that reduces time complexity from O(n) to O(log n).

Variants include lower/upper bound, rotated arrays, and binary search on answers.

# Sliding Window

Useful for subarray problems where we track a range in linear time.

Often paired with hash maps for frequency/counting purposes.

# Two Pointers

Used when comparing or moving through two indexes in a single pass.

Excellent for problems involving sorting, merging, or partitioning.

# Stack

Used for Last-In-First-Out operations.

Important in parsing expressions, backtracking, and maintaining monotonic sequences.

# Heap / Priority Queue

Great for keeping track of min/max values dynamically.

Essential for scheduling, median-finding, and merging tasks.

# Graphs (BFS/DFS)

Graph traversal is critical. BFS is ideal for shortest paths, while DFS is useful for exploring components.

Topological sort, connected components, and cycle detection are key concepts.

# Dynamic Programming

Breaks a problem into subproblems and caches results to avoid recomputation.

Recognizing overlapping subproblems and optimal substructure is key.

# Trie / String Matching

Trie helps in dictionary-like problems and prefix searching.

Efficient for solving auto-complete and word search variations.

# Greedy

Makes local optimal choices at each step with the hope of a global optimum.

Works well in interval scheduling, coin problems, and path optimization.

# Backtracking

A brute-force approach with pruning.
Often used in permutations, combinations, and constraint-satisfying problems.
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

# Dynamic Programming or DP

Dynamic Programming is an algorithmic technique with the following properties.
- It is mainly an optimization over plain recursion. Wherever we see a recursive solution that has repeated calls for the same inputs, we can optimize it using Dynamic Programming.
- The idea is to simply store the results of subproblems so that we do not have to re-compute them when needed later. This simple optimization typically reduces time complexities from exponential to polynomial.
- Some popular problems solved using Dynamic Programming are Fibonacci Numbers, Diff Utility (Longest Common Subsequence), Bellman–Ford Shortest Path, Floyd Warshall, Edit Distance and Matrix Chain Multiplication.


 Dynamic Programming is a commonly used algorithmic technique used to optimize recursive solutions when same subproblems are called again.

- The core idea behind DP is to store solutions to subproblems so that each is solved only once.
- To solve DP problems, we first write a recursive solution in a way that there are overlapping subproblems in the recursion tree (the recursive function is called with the same parameters multiple times)
- To make sure that a recursive value is computed only once (to improve time taken by algorithm), we store results of the recursive calls.
- There are two ways to store the results, one is top down (or memoization) and other is bottom up (or tabulation).

### When to Use Dynamic Programming (DP)?
Dynamic programming is used for solving problems that consists of the following characteristics:

### 1. Optimal Substructure:
The property Optimal substructure means that we use the optimal results of subproblems to achieve the optimal result of the bigger problem.
Example:

Consider the problem of finding the minimum cost path in a weighted graph from a source node to a destination node. We can break this problem down into smaller subproblems:

- Find the minimum cost path from the source node to each intermediate node.
- Find the minimum cost path from each intermediate node to the destination node.
The solution to the larger problem (finding the minimum cost path from the source node to the destination node) can be constructed from the solutions to these smaller subproblems.

### 2. Overlapping Subproblems:
The same subproblems are solved repeatedly in different parts of the problem refer to Overlapping Subproblems Property in Dynamic Programming.
Consider the problem of computing the Fibonacci series. To compute the Fibonacci number at index n, we need to compute the Fibonacci numbers at indices n-1 and n-2. This means that the subproblem of computing the Fibonacci number at index n-2 is used twice (note that the call for n - 1 will make two calls, one for n-2 and other for n-3) in the solution to the larger problem of computing the Fibonacci number at index n. 

## Approaches of Dynamic Programming (DP)
Dynamic programming can be achieved using two approaches:

1. Top-Down Approach (Memoization):
In the top-down approach, also known as memoization, we keep the solution recursive and add a memoization table to avoid repeated calls of same subproblems.
- Before making any recursive call, we first check if the memoization table already has solution for it.
- After the recursive call is over, we store the solution in the memoization table.

2. Bottom-Up Approach (Tabulation):
In the bottom-up approach, also known as tabulation, we start with the smallest subproblems and gradually build up to the final solution.
- We write an iterative solution (avoid recursion overhead) and build the solution in bottom-up manner.
- We use a dp table where we first fill the solution for base cases and then fill the remaining entries of the table using recursive formula.
- We only use recursive formula on table entries and do not make recursive calls.

  ![image](https://github.com/user-attachments/assets/1921fb54-3c24-4b16-8f74-c5394630a7de)

### Tabulation vs Memoization
Tabulation and memoization are two techniques used to implement dynamic programming. Both techniques are used when there are overlapping subproblems (the same subproblem is executed multiple times). Below is an overview of two approaches

Memoization:
-Top-down approach
-Stores the results of function calls in a table.
-Recursive implementation
-Entries are filled when needed.

Tabulation:
-Bottom-up approach
-Stores the results of subproblems in a table
-Iterative implementation
-Entries are filled in a bottom-up manner from the smallest size to the final size.

![image](https://github.com/user-attachments/assets/4de75c0e-c18a-4671-a83c-0472cede6bbf)

### Implementation Analysis: Rod Cutting Problem
Given a rod of length n inches and an array price[]. price[i] denotes the value of a piece of length i. The task is to determine the maximum value obtainable by cutting up the rod and selling the pieces.

Examples:
Input: price[] =  [1, 5, 8, 9, 10, 17, 17, 20]
Output: 22
Explanation:  The maximum obtainable value is 22 by cutting in two pieces of lengths 2 and 6, i.e., 5 + 17 = 22.

Input : price[] =  [3, 5, 8, 9, 10, 17, 17, 20]
Output : 24
Explanation : The maximum obtainable value is 24 by cutting the rod into 8 pieces of length 1, i.e, 8*price[1]= 8*3 = 24.

Input : price[] =  [3]
Output : 3
Explanation: There is only 1 way to pick a piece of length 1.

In the rod cutting problem, the goal is to determine the maximum profit that can be obtained by cutting a rod into smaller pieces and selling them, given a price list for each possible piece length. The approach involves considering all possible cuts for the rod and recursively calculating the maximum profit for each cut. For detailed explanation and approaches, refer to Rod Cutting.

### Using Top-Down DP (Memoization) - O(n^2) Time and O(n) Space
In this implementation of the rod cutting problem, memoization is used to optimize the recursive approach by storing the results of subproblems, avoiding redundant calculations.

```
// C++ program to find maximum
// profit from rod of size n
# include <bits/stdc++.h>
using namespace std;

int cutRodRecur(int i, vector<int> &price, vector<int> &memo) {

    // Base case
    if (i == 0)
        return 0;

    // If value is memoized
    if (memo[i - 1] != -1)
        return memo[i - 1];

    int ans = 0;

    // Find maximum value for each cut.
    // Take value of rod of length j, and
    // recursively find value of rod of
    // length (i-j).
    for (int j = 1; j <= i; j++) {
        ans = max(ans, price[j - 1] + cutRodRecur(i - j, price, memo));
    }

    return memo[i - 1] = ans;
}

int cutRod(vector<int> &price) {
    int n = price.size();
    vector<int> memo(price.size(), -1);
    return cutRodRecur(n, price, memo);
}

int main() {
  
    vector<int> price = {1, 5, 8, 9, 10, 17, 17, 20};
    cout << cutRod(price);
    return 0;
}
```
Output - 22

### Using Bottom-Up DP (Tabulation) - O(n^2) Time and O(n) Space
We iteratively calculate the maximum profit for each possible rod length. For each length i, we check all possible smaller cuts, update the profit by comparing the current maximum profit with the profit obtained by combining smaller cuts, and ultimately return the maximum profit for the entire rod.

```
// Java program to find maximum
// profit from rod of size n 

import java.util.*;

class GfG {

    static int cutRod(int[] price) {
        int n = price.length;
        int[] dp = new int[n + 1];

        // Find maximum value for all 
        // rod of length i.
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= i; j++) {
                dp[i] = Math.max(dp[i], price[j - 1] + dp[i - j]);
            }
        }

        return dp[n];
    }

    public static void main(String[] args) {
        int[] price = {1, 5, 8, 9, 10, 17, 17, 20};
        System.out.println(cutRod(price));
    }
}
```
Output - 22

## Example of Dynamic Programming (DP)

## Example 1: Consider the problem of finding the Fibonacci sequence:
Fibonacci sequence: 0, 1, 1, 2, 3, 5, 8, 13, 21, 34, ...

Brute Force Approach: To find the nth Fibonacci number using a brute force approach, you would simply add the (n-1)th and (n-2)th Fibonacci numbers.
```
// C++ program to find 
// fibonacci number using recursion.
#include <bits/stdc++.h>
using namespace std;

// Function to find nth fibonacci number
int fib(int n) {
    if (n <= 1) {
        return n;
    }

    return fib(n - 1) + fib(n - 2);
}

int main() {
    int n = 5;
    cout << fib(n);
    return 0;
}
```
Output - 5

Below is the recursion tree of the above recursive solution.

![image](https://github.com/user-attachments/assets/87da4f69-7f55-4db7-a166-a5bac3a9f757)

The time complexity of the above approach is exponential and upper bounded by O(2n) as we make two recursive calls in every function.

### How will Dynamic Programming (DP) Work?
Let’s us now see the above recursion tree with overlapping subproblems highlighted with same color. We can clearly see that that recursive solution is doing a lot work again and again which is causing the time complexity to be exponential. Imagine time taken for computing a large Fibonacci number.

![image](https://github.com/user-attachments/assets/dd2aa693-9b6b-4315-920f-da6bc68a404a)

- Identify Subproblems: Divide the main problem into smaller, independent subproblems, i.e., F(n-1) and F(n-2)
- Store Solutions: Solve each subproblem and store the solution in a table or array so that we do not have to recompute the same again.
- Build Up Solutions: Use the stored solutions to build up the solution to the main problem. For F(n), look up F(n-1) and F(n-2) in the table and add them.
- Avoid Recomputation: By storing solutions, DP ensures that each subproblem (for example, F(2)) is solved only once, reducing computation time.

### Using Memoization Approach - O(n) Time and O(n) Space
To achieve this in our example we simply take an memo array initialized to -1. As we make a recursive call, we first check if the value stored in the memo array corresponding to that position is -1. The value -1 indicates that we haven't calculated it yet and have to recursively compute it. The output must be stored in the memo array so that, next time, if the same value is encountered, it can be directly used from the memo array.   

```
// C++ program to find
// fibonacci number using memoization.
#include <iostream>
#include <vector>
using namespace std;

int fibRec(int n, vector<int> &memo) {
  
    // Base case
    if (n <= 1) {
        return n;
    }

    // To check if output already exists
    if (memo[n] != -1) {
        return memo[n];
    }

    // Calculate and save output for future use
    memo[n] = fibRec(n - 1, memo) + fibRec(n - 2, memo);

    return memo[n];
}

int fib(int n) {
    vector<int> memo(n + 1, -1);
    return fibRec(n, memo);
}

int main() {
    int n = 5;
    cout << fib(n);
    return 0;
}
```
Output - 5

### Using Tabulation Approach - O(n) Time and O(n) Space
In this approach, we use an array of size (n + 1), often called dp[], to store Fibonacci numbers. The array is initialized with base values at the appropriate indices, such as dp[0] = 0 and dp[1] = 1. Then, we iteratively calculate Fibonacci values from dp[2] to dp[n] by using the relation dp[i] = dp[i-1] + dp[i-2]. This allows us to efficiently compute Fibonacci numbers in a loop. Finally, the value at dp[n] gives the Fibonacci number for the input n, as each index holds the answer for its corresponding Fibonacci number.

```
// C++ program to find
// fibonacci number using tabulation.
#include <iostream>
#include <vector>
using namespace std;

// Function for calculating the nth Fibonacci number
int fibo(int n) {
    vector<int> dp(n + 1);

    // Storing the independent values in dp
    dp[0] = 0;
    dp[1] = 1;

    // Using the bottom-up approach
    for (int i = 2; i <= n; i++) {
        dp[i] = dp[i - 1] + dp[i - 2];
    }
  
    return dp[n];
}

int main() {
    int n = 5;
    cout << fibo(n);
    return 0;
}
```
Output - 5

In the above code, we can see that the current state of any fibonacci number depends only on the previous two values. So we do not need to store the whole table of size n+1 but instead of that we can only store the previous two values. 

```
// C++ program to find
// fibonacci number using space optimised.
#include <iostream>
using namespace std;

int fibo(int n) {
  
    int prevPrev, prev, curr;

    // Storing the independent values
    prevPrev = 0;
    prev = 1;
    curr = 1;

    // Using the bottom-up approach
    for (int i = 2; i <= n; i++) {
        curr = prev + prevPrev;
        prevPrev = prev;
        prev = curr;
    }

    return curr;
}

int main() {
    int n = 5;
    cout << fibo(n);
    return 0;
}

```
Output - 5

### Common Algorithms that Use DP:
- Longest Common Subsequence (LCS): This is used in day to day life to find difference between two files (diff utility)
- Edit Distance : Checks how close to strings are. Can we be useful in implementing Google's did you mean type feature.
- Longest Increasing Subsequence : There are plenty of variations of this problem that arise in real world.
Bellman–Ford Shortest Path: Finds the shortest path from a given source to all other vertices.
- Floyd Warshall : Finds shortest path from every pair of vertices.
- Knapsack Problem: Determines the maximum value of items that can be placed in a knapsack with a given capacity.
- Matrix Chain Multiplication: Optimizes the order of matrix multiplication to minimize the number of operations.
- Fibonacci Sequence: Calculates the nth Fibonacci number.

## Steps to solve a Dynamic Programming Problem
1. Identify if it is a Dynamic programming problem.
2. Decide a state expression with the Least parameters.
3. Formulate state and transition relationship.
4. Apply tabulation or memorization.

### Step 1: How to classify a problem as a Dynamic Programming Problem? 
- Typically, all the problems that require maximizing or minimizing certain quantities or counting problems that say to count the arrangements under certain conditions or certain probability problems can be solved by using Dynamic Programming.
- All dynamic programming problems satisfy the overlapping subproblems property and most of the classic Dynamic programming problems also satisfy the optimal substructure property. Once we observe these properties in a given problem be sure that it can be solved using Dynamic Programming.

### Step 2: Deciding the state
Dynamic Programming problems are all about the state and its transition. This is the most basic step which must be done very carefully because the state transition depends on the choice of state definition you make.
State: A state can be defined as the set of parameters that can uniquely identify a certain position or standing in the given problem. This set of parameters should be as small as possible to reduce state space.
Example:
Let's take the classic Knapsack problem, where we need to maximize profit by selecting items within a weight limit. Here, we define our state using two parameters: index and weight (dp[index][weight]). Think of it like this: dp[3][10] would tell us "what's the maximum profit we can make by choosing from the first 4 items (index 0 to 3) when our bag can hold 10 units of weight?" These two parameters (index and weight) work together to uniquely identify each subproblem we need to solve.
Just like GPS coordinates need both latitude and longitude to pinpoint a location, our knapsack solution needs both the item range and remaining capacity to determine the optimal profit at each step.
So, our next step will be to find a relation between previous states to reach the current state. 

### Step 3: Formulating a relation among the states 
This part is the hardest part of solving a Dynamic Programming problem and requires a lot of intuition, observation, and practice.
Example: 
Given 3 numbers {1, 3, 5}, The task is to tell the total number of ways we can form a number n using the sum of the given three numbers. (allowing repetitions and different arrangements).
The total number of ways to form 6 is: 8
1 + 1 + 1 + 1 + 1 + 1
1 + 1 + 1 + 3
1 + 1 + 3 + 1
1 + 3 + 1 + 1
3 + 1 + 1 + 1
3 + 3
1 + 5
5 + 1
The steps to solve the given problem will be:
- We decide a state for the given problem. 
- We will take a parameter n to decide the state as it uniquely identifies any subproblem. 
- DP state will look like state(n), state(n) means the total number of arrangements to form n by using {1, 3, 5} as elements. Derive a transition relation between any two states.
- Now, we need to compute state(n).

### How to Compute the state? 
As we can only use 1, 3, or 5 to form a given number n. Let us assume that we know the result for n = 1, 2, 3, 4, 5, 6 
Let us say we know the result for:
state (n = 1), state (n = 2), state (n = 3) ......... state (n = 6) 
Now, we wish to know the result of the state (n = 7). See, we can only add 1, 3, and 5. Now we can get a sum total of 7 in the following 3 ways:
1) Adding 1 to all possible combinations of state (n = 6) 
Eg : [(1 + 1 + 1 + 1 + 1 + 1) + 1] 
[(1 + 1 + 1 + 3) + 1] 
[(1 + 1 + 3 + 1) + 1] 
[(1 + 3 + 1 + 1) + 1] 
[(3 + 1 + 1 + 1) + 1] 
[(3 + 3) + 1] 
[(1 + 5) + 1] 
[(5 + 1) + 1] 

2) Adding 3 to all possible combinations of state (n = 4);
[(1 + 1 + 1 + 1) + 3] 
[(1 + 3) + 3] 
[(3 + 1) + 3] 

3) Adding 5 to all possible combinations of state(n = 2) 
[(1 + 1) + 5]

(Note how it sufficient to add only on the right-side - all the add-from-left-side cases are covered, either in the same state, or another, e.g. [1 + (1 + 1 + 1 + 3)]  is not needed in state (n=6) because it's covered by state (n = 4) [(1 + 1 + 1 + 1) + 3])

Now, think carefully and satisfy yourself that the above three cases are covering all possible ways to form a sum total of 7;
Therefore, we can say that result for 
state(7) = state (6) + state (4) + state (2) 
OR
state(7) = state (7-1) + state (7-3) + state (7-5)
In general, 
state(n) = state(n-1) + state(n-3) + state(n-5)

Below is the implementation of the above approach:
```
// C++ program to express
// n as sum of 1, 3, 5.
#include <bits/stdc++.h>
using namespace std;

// Returns the number of 
// arrangements to form 'n' 
int countWays(int n) { 
    
   // base case
   if (n < 0) 
      return 0;
   if (n == 0)  
      return 1;  

   return countWays(n-1) + countWays(n-3) + countWays(n-5);
}    

int main() {
    int n = 7;
    cout << countWays(n);
}
```
Output: 5
Time Complexity: O(3^n), As at every stage we need to take three decisions and the height of the tree will be of the order of n.
Auxiliary Space: O(n), The extra space is used due to the recursion call stack.

The above code seems exponential as it is calculating the same state again and again. So, we just need to add memoization. 

### Step 4: Adding memoization or tabulation for the state
This is the easiest part of a dynamic programming solution. We just need to store the state answer so that the next time that state is required, we can directly use it from our memory.

Using Top-Down DP (Memoization) 
We break down the problem into smaller subproblems, where each subproblem corresponds to finding the number of ways to form a sum for a smaller value of 'n'. By utilizing previously computed results, we can avoid redundant calculations and build up the solution for larger values of 'n'.

```
// C++ program to express
// n as sum of 1, 3, 5.
#include <bits/stdc++.h>
using namespace std;

int countRecur(int n, vector<int> &memo) {
    
    // base case
    if (n < 0) 
      return 0;
    if (n == 0)  
      return 1;  
      
    // If value is memoized
    if (memo[n] != -1) {
        return memo[n];
    }
    
    // Memoize the state 
    memo[n] = countRecur(n-1, memo) + 
    countRecur(n-3, memo) + countRecur(n-5, memo);    
   
   return memo[n];
}

// Returns the number of 
// arrangements to form 'n' 
int countWays(int n) { 
    
    vector<int> memo(n+1, -1);
    return countRecur(n, memo);
}    

int main() {
    int n = 7;
    cout << countWays(n);
}
```
Output: 12

Using Bottom-Up DP (Tabulation)
We define a DP array where each element dp[i] represents the number of ways to form the sum 'i'. Starting with the base case dp[0] = 1 (since there is exactly one way to form a sum of 0 - using no numbers), we iteratively calculate the number of ways to form each value from 1 to n.
```
// C++ program to express
// n as sum of 1, 3, 5.
#include <bits/stdc++.h>
using namespace std;

// Returns the number of
// arrangements to form 'n'
int countWays(int n) {

    vector<int> dp(n + 1);

    dp[0] = 1;

    for (int i = 1; i <= n; i++) {
        dp[i] = 0;

        if (i - 1 >= 0)
            dp[i] += dp[i - 1];
        if (i - 3 >= 0)
            dp[i] += dp[i - 3];
        if (i - 5 >= 0)
            dp[i] += dp[i - 5];
    }

    return dp[n];
}

int main() {
    int n = 7;
    cout << countWays(n);
}
```

Time Complexity: O(n), As we just need to make 3n function calls and there will be no repetitive calculations as we are returning previously calculated results.
Auxiliary Space: O(n), dp array of size n+1 is used to store the results of subproblems.

### Advantages of Dynamic Programming (DP)
Dynamic programming has a wide range of advantages, including:
- Avoids recomputing the same subproblems multiple times, leading to significant time savings.
- Ensures that the optimal solution is found by considering all possible combinations.

### Applications of Dynamic Programming (DP)
Dynamic programming has a wide range of applications, including:
- Optimization: Knapsack problem, shortest path problem, maximum subarray problem
- Computer Science: Longest common subsequence, edit distance, string matching
- Operations Research: Inventory management, scheduling, resource allocation

Problems:
[Link Text](https://leetcode.com/problems/fibonacci-number/description/?envType=problem-list-v2&envId=dynamic-programming)
[Link Text](https://leetcode.com/problems/is-subsequence/description/?envType=problem-list-v2&envId=dynamic-programming)
[Link Text](https://www.geeksforgeeks.org/problems/0-1-knapsack-problem0945/1?page=1&category=Dynamic%20Programming&sortBy=submissions)
[Link Text](https://www.geeksforgeeks.org/problems/subset-sum-problem-1611555638/1?page=1&category=Dynamic%20Programming&sortBy=submissions)
[Link Text](https://leetcode.com/problems/longest-palindromic-substring/description/?envType=problem-list-v2&envId=dynamic-programming)
[Link Text](https://leetcode.com/problems/maximum-subarray/description/?envType=problem-list-v2&envId=dynamic-programming)


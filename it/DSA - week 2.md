# Linked List

A linked list in data structures is a collection of elements called nodes, where each node contains some data and a reference to the next node in the sequence. This setup allows elements to be easily added or removed without reorganizing the entire structure. 

Linked lists are crucial in data structures and algorithms (DSA) because they provide a dynamic way to manage data, adapting the size of the structure as needed without the high overhead associated with arrays. 

# Example of Linked List

Consider a real-life application of linked list data structure like a music playlist.

Each song in the playlist can be thought of as a node in a linked list, with each node pointing to the next song. Adding or removing songs from your playlist doesn't require shifting all other songs; you simply adjust the links. 

# Structure or Representation of Linked List

# Node:

Each element of a linked list is called node. A node has two components: 

●​ Data: The actual value or information that needs to be stored. 

●​ Next: A pointer (or reference) to the next node in the linked list.

Head: 

The first node in a linked list is called the head. It is the entry point to the list and used as a reference point to traverse it. 

# Null:

The last node of a linked list, which points to null, indicating the end of the list.


![](https://web-api.textin.com/ocr_image/external/7e004c7439231898.jpg)

# Types of Linked List in Data Structures 

There are three primary types of linked lists:

## 1. Singly Linked List 

A singly linked list is a collection of nodes where each node contains data and a reference to the next node in the sequence. This structure allows for a simple, one-directional traversal from the head to the end of the list. 


![](https://web-api.textin.com/ocr_image/external/72c8b8fcba14e1db.jpg)

### Example: 

Consider managing a simple task list. Each task points to the next one until the end: 

$$Task1->Task2->Task3->null$$

Operations like adding or removing tasks involve adjusting the 'next' reference of the preceding node, which is straightforward but only allows moving forward through the list. 

## 2. Doubly Linked List

Doubly linked lists expand on singly linked lists by having each node contain two references: one pointing to the next node and one to the previous node. This allows nodes to be traversed in both forward and backward directions. 


![](https://web-api.textin.com/ocr_image/external/94dcae10beb8ea84.jpg)

### Example: 

Imagine a playlist where you can move to the next or previous song:

null $<-$ PrevSong $<->$ CurrentSong &lt;-&gt; NextSong $->$  null

This setup is particularly useful for applications like image viewers or document viewers where users may need to go forward and backward between images or pages. 

## 3. Circular Linked List

A circular linked list is a type of data structure where each node points to the next node, and the last node points back to the first, forming a circle. 

This setup allows for an endless cycle of node traversal, which can be particularly useful in applications where the end of the list naturally reconnects to the beginning. 


![](https://web-api.textin.com/ocr_image/external/9cdf7e4470201194.jpg)

### Example: 

In multiplayer games, a circular linked list manages player turns, cycling back to the first player after the last one finishes. 

### Uses of Linked Lists

Data structure linked lists offer several practical uses across different applications:

### 1. Dynamic Memory Allocation

Linked lists are ideal for applications where the amount of data is unknown in advance and can change dynamically. They are extensively used in implementing memory management algorithms. 

## 2. Implementing Stacks and Queues

Linked lists provide a natural way to implement other abstract data types like stacks and queues.

For example, a singly linked list can serve as a stack or queue by adding or removing nodes from one end. 

## 3. Browser History Management

The functionality of back and forward navigation in web browsers can be effectively managed using a doubly linked list where each node points to the previous and next web pages visited. 

# 4. Undo Functionality in Applications

Linked lists are used in implementing undo mechanisms in software applications, where operations are stored in a list and can be reversed by traversing backwards. 

# 5. Music Playlists and Image Viewers

Applications that require sequential access to elements, such as media players or image viewers, often use doubly linked lists to facilitate easy navigation between items (next and previous). 

# 6. Graphs Representation

Adjacency lists, which are used to represent graphs, can be implemented using linked lists, where each node represents a vertex and its linked list represents the adjacent vertices. 

# 7. Polynomial Arithmetic

Linked lists are useful in representing and manipulating polynomials. Each node can represent a term of the polynomial, allowing for dynamic adjustments to the polynomial as terms are added or subtracted. 

## Linked List Operations

Understanding how to perform operations on linked lists is crucial for using them effectively in programming. 

### 1. Insertion

Insertion in a linked list includes adding a new node to the list. You can insert a node at the beginning, in the middle, or at the end of the list. 


![](https://web-api.textin.com/ocr_image/external/ad9a80c463f6ace6.jpg)

Circular linkedlist 

#### Example: 

Inserting at the beginning: Imagine you have a list of daily tasks, and you suddenly need to add a new task at the top of your list. You create a new node for this task and make it the new head of the list, pointing to the previous first task. 

"Read book" $->$  becomes new head $->$ "Go to market" $->$ "Write $\text {essay"->null}$ 

## 2. Deletion

Deletion removes a node from the linked list. This can also be done at the beginning, at a specific position, or at the end. 

## 3. Search

Searching in a linked list involves traversing through the list from the head to find a node containing a specific value. 

## 4. Traversal

Traversal means going through each node in the list from the beginning to the end to access or modify data. 

## 5. Update

Updating involves changing the data in one of the nodes without altering the structure of the list. 

## Advantages of Linked Lists

●​ Dynamic Sizing: Linked lists can grow and shrink during runtime as they do not have a fixed size, unlike arrays. 

●​ Efficient Insertions and Deletions: Adding or removing nodes does not require the elements to be contiguous in memory, so operations can be performed without reallocating or reorganizing the entire structure. 

●​ No Memory Waste: Since there's no need to pre-allocate memory, linked lists can manage data more efficiently without wasting memory on unused space. 

●​ Ease of Implementation: Can easily be implemented and manipulated, particularly when it comes to complex data structures such as stacks, queues, and other abstract data types. 

●​Flexible Structure: Nodes can easily be rearranged by changing their next pointers without the need for data movement, which is beneficial for applications that require frequent reordering of data. 

# Disadvantages of Linked Lists (Limitations)

●​ Higher Memory Use: Each node in a linked list requires additional memory for a pointer to the next (and possibly previous) node, which is more memory-intensive than the tight data packing in arrays. 

●​ Slower Access Time: Direct access is not feasible with linked lists. To access an element at a specific index, you have to traverse the list from the head to that position, which takes more time than array access. 

●​ Complexity in Navigation: Navigating a linked list can be more complex compared to navigating an array, as it requires pointer manipulation, which can be prone to errors like pointer corruption or memory leaks. 

●​Extra Memory for Pointers: The requirement for storing pointers typically means using extra memory,which can be significant in systems with a large number of elements. 

# Array vs Linked List Difference

Let’s know about the difference between linked list and array in data structures:


| Feature  | Linked List  | Array  |
| --- | --- | --- |
| Memory Allocation  | Dynamic allocation. Nodes are allocated as needed.  | Static or dynamic allocation but fixed size once created.  |
| Element Access  | Sequential access. Must traverse from the head.  | Direct access via indices.  |
| Insertion/Deletion  | Fast operations as they only require pointer changes.  | Slower operations, especially in the middle, because elements must be shifted.  |
| Memory Efficiency  | Less memory-efficient due to extra space for pointers.  | More memory-efficient; only stores the data.  |
| Implementation  | More complex implementation, especially for beginners.  | Simpler implementation and easier to manage.  |
| Speed of Access  | Slower to read due to traversal needs.  | Fast and immediate access to any element.  |
| Data Structure Size  | Can grow or shrink dynamically without a high cost.  | Requires resizing and copying to grow, which is costly.  |
| Cache Locality  | Poor cache locality due to non-contiguous storage.  | Better cache locality due to contiguous memory layout.  |
| Usage Scenarios  | Good for scenarios with frequent insertions and deletions without a predetermined size of data.  | Best when the size is known in advance and fast element access is needed.  |
| Manipulation <br>Overhead  | Low overhead for adding/removing elements.  | Higher overhead for adding/removing elements due to shifting.  |
| Structural Overhead  | Nodes carry extra overhead due to storing pointers.  | No extra overhead beyond the data itself.  |


●​ Linked Lists are preferable when you need a flexible data structure that frequently changes size and where insertion and deletion speed is critical. 

●​ Arrays are suitable for situations requiring fast access to elements, where the size of the data structure can be known beforehand, and operations like sorting and random access are common. 

# Practise problems on Linkedlist 

1.​ Reverse Linked List​

2.​ Middle of the Linked List​

3.​ Merge Two Sorted Lists​

4.​ Linked List Cycle​

5.​ Remove Duplicates from Sorted List​

6.​ Remove Linked List Elements​

7.​ Palindrome Linked List​

8.​ Intersection of Two Linked Lists​

9.​ Remove Nth Node From End of List​

10.​Add Two Numbers​

11.​Reverse Linked List II​

12.​Reverse Nodes in k-Group​

13.​Copy List with Random Pointer​

14.​Linked List Cycle II​

15.​Partition List​

16.​Insertion Sort List​

17.​Sort List​

18.​Rotate List​

19.​Reorder List​

20.​Convert Sorted List to Binary Search Tree

# Stack 

Stack is a linear data structure that follows LIFO (Last In First Out) Principle, the last element inserted is the first to be popped out. It means both insertion and deletion operations happen at one end only. 

## LIFO(Last In First Out) Principle

Here are some real world examples of LIFO

●​ Consider a stack of plates. When we add a plate, we add at the top. When we remove, we remove from the top. 

●​ A shuttlecock box (or any other box that is closed from one end) is another great real-world example of the LIFO (Last In, First Out) principle where do insertions and removals from the same end. 

## Representation of Stack Data Structure: 

Stack follows LIFO (Last In First Out) Principle so the element which is pushed last is popped first. 


![](https://web-api.textin.com/ocr_image/external/5423026fcbbf085a.jpg)


![](https://web-api.textin.com/ocr_image/external/cb02d92949735610.jpg)

## Types of Stack: 

●​ Fixed Size Stack : As the name suggests, a fixed size stack has a fixed size and cannot grow or shrink dynamically. If the stack is full and an attempt is made to add an element to it, an overflow error occurs. If the stack is empty and an attempt is made to remove an element from it, an underflow error occurs. 

●​ Dynamic Size Stack : A dynamic size stack can grow or shrink dynamically. When the stack is full, it automatically increases its size to accommodate the new element, and when the stack is empty, it decreases its size. This type of stack is implemented using a linked list, as it allows for easy resizing of the stack. 

## Basic Operations on Stack: 

In order to make manipulations in a stack, there are certain operations provided to us. 

●​ push() to insert an element into the stack 

●​ pop() to remove an element from the stack 

●​ top() Returns the top element of the stack.

●​ isEmpty() returns true if stack is empty else false.

●​ isFull() returns true if the stack is full else false. 

To implement stack, we need to maintain reference to the top item.

## Push Operation on Stack 

Adds an item to the stack. If the stack is full, then it is said to be an Overflow condition. 

Algorithm for Push Operation: 

●​ Before pushing the element to the stack, we check if the stack is full .

●​ If the stack is full $\text {(top==capacity-1)}$ , then Stack Overflows and we cannot insert the element to the stack. 

●​ Otherwise, we increment the value of top by 1 $(\text {top}=\text {top}+1)$  and the new value is inserted at top position . 

●​ The elements can be pushed into the stack till we reach the capacity of the stack. 

# Pop Operation in Stack 

Removes an item from the stack. The items are popped in the reversed order in which they are pushed. If the stack is empty, then it is said to be an Underflow condition. 

Algorithm for Pop Operation: 

●​ Before popping the element from the stack, we check if the stack is empty .

●​ If the stack is empty (top $==-1$ ), then Stack Underflows and we cannot remove any element from the stack. 

●​ Otherwise, we store the value at top, decrement the value of top by 1 (top $=\text {top}-1$ ) and return the stored top value. 

# Top or Peek Operation on Stack

Returns the top element of the stack.

Algorithm for Top Operation:

●​ Before returning the top element from the stack, we check if the stack is empty. 

●​ If the stack is empty $(\text {top}==-1)$ , we simply print “Stack is empty”.

●​ Otherwise, we return the element stored at ind $ex=top$ 

# isEmpty Operation in Stack Data Structure: 

Returns true if the stack is empty, else false. 

Algorithm for isEmpty Operation:

●​ Check for the value of top in stack.

$·\text {If}(\text {top}==-1)$ , then the stack is empty so return true .

●​ Otherwise, the stack is not empty so return false .

# isFull Operation in Stack Data Structure: 

Returns true if the stack is full, else false.

Algorithm for isFull Operation: 

●​ Check for the value of top in stack.

●​ If (top $==$  capacity-1), then the stack is full so return true.

●​ Otherwise, the stack is not full so return false.

# Complexity Analysis of Operations on Stack Data Structure: 


| Operations  | Time Complexity  | Space Complexity  |
| --- | --- | --- |
| push()  | O(1)  | O(1)  |
| pop()  | O(1)  | O(1)  |
| top()top() or peek()  | O(1)  | O(1)  |
| isEmpty()  | O(1)  | O(1)  |
| isFull()  | O(1)  | O(1)  |


Monotonic Stack

A Monotonic Stack is a common data structure in computer science that maintains its elements in a specific order. Unlike traditional stacks, Monotonic Stacks ensure that elements inside the stack are arranged in an increasing or decreasing order based on their arrival time. In order to achieve the monotonic stacks, we have to enforce the push and pop operation depending on whether we want a monotonic increasing stack or monotonic decreasing stack. 

Monotonic: It is a word for mathematics functions. A function $y=f(x)is$ 

monotonically increasing or decreasing when it follows the below conditions:

●​ As x increases, y also increases always, then it's a monotonically increasing function. 

●​ As x increases, y decreases always, then it's a monotonically decreasing function. 

See the below examples:

●​ $y=2x+5$ , it's a monotonically increasing function.

●​ $y=-(2x)$ , it's a monotonically decreasing function.

Similarly, A stack is called a monotonic stack if all the elements starting from the bottom of the stack is either in increasing or in decreasing order. 

# Types of Monotonic Stack: 

Monotonic Stacks can be broadly classified into two types:

1.​ Monotonic Increasing Stack 

2.​ Monotonic Decreasing Stack


![](https://web-api.textin.com/ocr_image/external/ce2f7253237942d1.jpg)

# Monotonic Increasing Stack: 

A Monotonically Increasing Stack is a stack where elements are placed in increasing order from the bottom to the top. Each new element added to the stack is greater than or equal to the one below it. If a new element is smaller, we remove elements from the top of the stack until we find one that is smaller or equal to the new element, or until the stack is empty. This ensures that the stack always stays in increasing order. 

Example: 1, 3, 10, 15, 17

# How to achieve Monotonic Increasing Stack?

To achieve a monotonic increasing stack, you would typically push elements onto the stack while ensuring that the stack maintains a increasing order from bottom to top. When pushing a new element, you would pop elements from the stack that are greater than the new element until the stack maintains the desired monotonic increasing property. 

To achieve a monotonic increasing stack, you can follow these step-by-step approaches: 

●​ Initialize an empty stack.

●​ Iterate through the elements and for each element:

○​ while stack is not empty AND top of stack is more than the current element 

○​ pop element from the stack 

○​ Push the current element onto the stack.

●​ At the end of the iteration, the stack will contain the monotonic increasing order of elements. 

# Complexity Analysis:

●​ Time Complexity: O(N), each element from the input array is pushed and popped from the stack exactly once. Therefore, even though there is a loop inside a loop, no element is processed more than twice. 

●​ Auxiliary Space: O(N) 

# Monotonic Decreasing Stack:

A Monotonically Decreasing Stack is a stack where elements are placed in decreasing order from the bottom to the top. Each new element added to the stack must be smaller than or equal to the one below it. If a new element is greater than top of stack then we remove elements from the top of the stack until we find one that is greater or equal to the new element, or until the stack is empty. This ensures that the stack always stays in decreasing order. 

Example: 17, 14, 10, 5, 1

# How to achieve Monotonic Decreasing Stack

To achieve a monotonic decreasing stack, you would typically push elements onto the stack while ensuring that the stack maintains a decreasing order from bottom to top. When pushing a new element, you would pop elements from the stack that are greater than the new element until the stack maintains the desired monotonic decreasing property. 

To achieve a monotonic decreasing stack, you can follow these step-by-step approaches: 

●​ Start with an empty stack.

●​ Iterate through the elements of the input array.

○​ While stack is not empty AND top of stack is less than the current element: 

○​ pop element from the stack 

○​ Push the current element onto the stack.

●​ After iterating through all the elements, the stack will contain the elements in monotonic decreasing order. 

Complexity Analysis:

Time Complexity: O(N), each element is processed only twice, once for the push operation and once for the pop operation.​

Auxiliary Space: O(N)

# Practise problems on stack 

1.​ Valid Parentheses​

2.​ Min Stack​

3.​ Evaluate Reverse Polish Notation

4.​ Daily Temperatures​

5.​ Next Greater Element I​

6.​ Next Greater Element II​

7.​ Largest Rectangle in Histogram

8.​ Asteroid Collision

9.​ Remove All Adjacent Duplicates in String​

10.​Decode String​

11.​Simplify Path

12.​Remove K Digits

13.​Online Stock Span

14.​132 Pattern

15.​Basic Calculator II 

# Queue

A queue in data structures is a linear collection of elements that operates under the First In, First Out (FIFO) principle. This means that the first element added to the queue will be the first one removed.​

# Simple Example

Imagine you are at a movie theater where several people are waiting to buy tickets. The first person to join the queue will be the first to buy a ticket and leave the queue. 


![](https://web-api.textin.com/ocr_image/external/4ef7d3fafc453dae.jpg)

If the queue is represented as a list of names:

Enqueue (Join the Queue): John, Mary, and Alice join the queue in this order. The queue now looks like [John, Mary, Alice], where John is at the front. 

Dequeue (Leave the Queue): John buys his ticket and leaves the queue. Now, the queue is [Mary,Alice], with Mary at the front ready to be the next to buy a ticket.​

In this way, queues help manage data where the timing of the processing is crucial, ensuring that items are handled in the order they arrive, which is critical for fairness and efficiency in many 

real-world applications.

# Operations of Queue in Data Structure

The following are the primary operations performed on a queue data structure:

# Enqueue

The enqueue operation involves adding an element to the rear of the queue. When you "enqueue,"you are putting an item at the end of the line, waiting to be processed. ​

This operation may involve updating the rear pointer of the queue to point to the new element,which becomes the new rear of the queue.​

# Dequeue

The dequeue operation removes an element from the front of the queue. This is the primary action reflecting the FIFO nature of the queue; the oldest element added (the one at the front) gets removed and processed first. ​

After the dequeue, the front pointer of the queue needs to be updated to the next element.

# Peek or Front

This operation allows you to look at the front element of the queue without removing it. It's useful when you need to check which element is next to be processed but do not want to dequeue it yet.This operation simply retrieves the value of the front element.​

# IsEmpty

The isEmpty operation checks if the queue is empty. This is crucial to avoid errors such as underflow when attempting to dequeue from an empty queue. If the front of the queue is null (or the front pointer equals the rear pointer in an empty circular queue), the queue is empty.​

# IsFull (for fixed-size queues)

In the context of a static or fixed-size queue (like an array-based queue), the isFull operation checks if the queue has reached its maximum capacity. This is important to prevent overflow errors when trying to enqueue elements into a full queue.​

# Types of Queue in Data Structure

There are several types of queues in data structure to accommodate different programming needs and scenarios:​

## 1. Simple Queue

A simple queue operates on the FIFO (First In, First Out) principle, where elements are added to the rear and removed from the front. It is the most basic form of a queue used for sequential data processing.​

Example: Managing a queue at a ticket counter where the first person to arrive is the first to be served.​

# 2. Circular Queue

A circular queue is a more efficient version of the simple queue. It uses a circular structure to utilize memory optimally. ​

In a circular queue, when the rear reaches the end of the array and there is space at the beginning,it can wrap around and use this space, thus maximizing the use of available memory.​


![](https://web-api.textin.com/ocr_image/external/e8c32fe1aaf34552.jpg)

Example: A round-robin scheduler in a multitasking environment uses a circular queue to continuously cycle through tasks, allocating CPU time to each task one by one and then starting over at the beginning of the queue.​

# 3. Priority Queue

In a priority queue, elements are not necessarily dequeued in the order they were enqueued. Instead, each element is associated with a priority, and the element with the highest priority is dequeued first. Priority queues are often implemented using heaps to allow for efficient priority-based retrieval. 


![](https://web-api.textin.com/ocr_image/external/f0482bdc39d89cb6.jpg)

Example: An emergency room could use a priority queue for patient triage. Patients with more serious conditions are treated before those with less urgent needs, regardless of their order of arrival.​

# 4. Double-Ended Queue (Deque)

A deque allows insertion and removal of elements from both the front and the rear of the queue. This flexibility makes it a handy tool for various applications where elements need to be processed from both ends.​


![](https://web-api.textin.com/ocr_image/external/bfe692a8a6c051bb.jpg)

Example: A list of recently used documents or applications where you can add new entries from both ends, or remove the least recently used items from either end, based on user interaction.​

# Applications of Queue Data Structure

Queues are used across various real-world applications to manage processes and data efficiently:Operating Systems: Queues are used to manage processes in multitasking environments. The 

operating system maintains a queue of processes that need to be executed, managing them in an orderly fashion based on their arrival time, priority, or other criteria. 

●​ Printing and Task Scheduling: In environments where multiple jobs are submitted to a printer or any other task execution system, queues help manage these jobs efficiently. Jobs are processed in the order they are received unless priorities are assigned. 

●​ Web Server Request Management: Web servers use queues to manage incoming client requests. Requests are stored in a queue and processed sequentially, ensuring that resources are allocated fairly and efficiently. 

●​ Call Centers: In customer service call centers, incoming calls are held in a queue until an operator is available, ensuring that calls are answered in the order they arrive. 

●​ Traffic Management: Queues are used in traffic light systems and other transportation management systems to regulate the flow of traffic and ensure orderly movement of vehicles. 

●​ Data Streaming Services: For live data streaming services, such as video or live news feeds, queues help in buffering data packets, ensuring a smooth and continuous flow of data to the user. 

●​ Banking Services: Banks use queues to manage customer transactions at branches, where customers take a number and wait to be served in order. 

●​ E-commerce Order Processing: E-commerce platforms use queues to manage order processing, from order receipt through payment processing to shipment. 

●​ Simulation of Real-world Systems: Queues are extensively used in simulations where real-world processes involve waiting lines or sequential processing, such as in amusement parks, restaurant service, or airport check-in systems. 

●​ Healthcare Systems: In hospitals and clinics, queues are used to manage patient appointments and treatments in an orderly system.​

## Advantages of Queue Data Structure

●​ Simplicity and Predictability: Queues operate on a simple and predictable First In, First Out (FIFO) principle, which is easy to implement and understand. 

●​ Fairness: By processing elements in the order they arrive, queues ensure fairness in systems like scheduling processes in an operating system or managing customers in service industries. 

Resource Sharing: Queues help manage resources efficiently in various applications, such as print spooling and task scheduling, by maintaining a queue of tasks that await processing. 

●​ Asynchronous Data Handling: Queues are excellent for handling data from asynchronous processes, such as buffering inputs in I/O operations, where data can arrive at any time and needs to be processed in the correct order. 

●​Load Balancing: In distributed computing environments, queues can help in load balancing by queuing tasks and distributing them evenly amongst multiple servers.​

## Disadvantages of Queue Data Structure

●​ Fixed Size: In static queue implementations (using arrays), the size of the queue is fixed, leading to potential overflow if the queue gets filled. This requires careful management and can lead to inefficient use of memory. 

●​ Time-consuming Operations: Operations such as searching for an element or accessing elements other than the front can be time-consuming as they require traversal of the queue.

●​ One-way Access: The queue structure only allows access from one end for addition and the other for removal, which limits flexibility compared to other data structures like deques (double-ended queues) that allow insertion and removal from both ends. 

### Practise Queue Problems 

1.​ Implement Queue using Stacks

2.​ Design Circular Queue​

3.​ Number of Recent Calls​

4.​ Moving Average from Data Stream

5.​ Time Needed to Buy Tickets​

6.​ Sliding Window Maximum (uses deque)

7.​ Rotting Oranges (BFS traversal)​

8.​ Shortest Path in Binary Matrix​

9.​ Walls and Gates​

10.​Open the Lock​

11.​Course Schedule (topological sort using queue)

12.​Zero-One Matrix​

13.​Reveal Cards In Increasing Order​

14.​Snakes and Ladders​

15.​Minimum Genetic Mutation​




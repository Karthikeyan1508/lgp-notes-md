# File Systems
A file is a structured collection of related information stored on secondary storage like a hard drive, SSD, or flash drive.

The file system is a crucial part of the operating system that manages how data is stored, organized, and retrieved efficiently from these storage devices. Its design directly affects the system’s performance, reliability, and security.

Different operating systems adopt different file system implementations to meet their requirements:

- Windows commonly uses NTFS and FAT.

- Linux systems often use ext4 and XFS.

## Components of File System Implementation
*1.File System Structure*

- Defines how files and directories are organized on the storage device.

- Includes structures like directory tables, file allocation tables (FAT), and inodes.

*2.File Allocation*

- Determines how space is assigned to files on disk.

- Techniques include:

	- Contiguous Allocation

	- Linked Allocation

	- Indexed Allocation

	- Hybrid approaches

*3.Data Retrieval*

- Handles how data is read/written efficiently.

- Uses buffering, caching, and read-ahead techniques to improve performance.

*4.Security and Permissions*

- Manages who can access or modify files.

- Uses file permissions, ownership, and Access Control Lists (ACLs).

*5.Recovery and Fault Tolerance*

- Ensures data integrity in case of crashes or failures.

- Involves journaling, snapshots, and other recovery mechanisms.

## Layers in File System
The file system in an OS is organized into multiple layers, each handling a specific function from user interaction to actual hardware operations:

![image](https://github.com/user-attachments/assets/654773e3-e008-4a69-afc8-52f7576e2784)

*1. Application Layer*

- Topmost layer where users interact with files using:

	- Text editors, file browsers, CLI tools

- Supports operations like create, delete, read, write, etc.
  

*2. Logical File System*

- Manages file metadata (not the actual content).

- Maintains File Control Block (FCB) containing:

	- File owner, size, permissions, location

- Responsible for access control and directory structure.
  

*3. File Organization Module*

- Maps logical blocks to physical blocks on disk.

- Maintains:

	- File location info

	- Logical vs. physical block mapping

	- Free space management (tracks unallocated blocks)
 

*4. Basic File System*
- Sends generic commands to device drivers.

- Manages:

	- Disk block read/write

	- Buffer cache (holds block contents)

	- Metadata cache (frequently used metadata)

*5. I/O Control Layer*

- Contains device drivers which act as intermediaries between OS and hardware.

- Converts logical commands to hardware-specific instructions.

- Transfers data between disk and main memory.

*6. Device Layer*

- Bottommost layer – includes physical storage devices:

	- Hard drives, SSDs, optical disks, etc.

- Performs actual read/write operations on hardware.

## Directory Implementation in Operating System
The directory structure is a key part of the file system, used to store and manage file metadata such as file names, locations, and attributes.

The choice of directory implementation technique affects the system's efficiency, reliability, and performance.

The below are two ways of implementing the directory in the operating system :

- Directory Implementation using Singly Linked List
- Directory Implementation using Hash Table

### Directory Implementation Using Singly Linked List
A singly linked list is one of the simplest ways to implement a directory in an operating system.
Each directory entry is a node containing the file name and a pointer to the file's data block.

![image](https://github.com/user-attachments/assets/f0403b40-4ce8-4a2e-83ce-36c09f4fce33)

*Steps to Implement the Directory Using Singly Linked List*

- To create a new file the entire list has to be checked such that the new directory does not exist previously.
  
- The new directory then can be added to the end of the list or at the beginning of the list.
  
- In order to delete a file, we first search the directory with the name of the file to be deleted. After searching we can delete that file by releasing the space allocated to it.
  
- To reuse the directory entry we can mark that entry as unused or we can append it to the list of free directories.
  
- To delete a file linked list is the best choice as it takes less time.

### Directory Implementation using Hash Table
A hash table is a more efficient alternative to linked list-based directory implementation.
It overcomes slow searching by providing constant-time average-case access.

![image](https://github.com/user-attachments/assets/a31c5ae6-6a33-47fd-86f4-78825c760508)

*Steps to Implement the Directory Using Hash Table*

- Combine a hash table with a linked list to implement the directory structure.
  
- Generate a key-value pair for each file using a hash function on the file name.
  
- Insert the file into the linked list and store the key-pointer pair in the hash table.
  
- To search, compute the key using the file name and look it up in the hash table.
  
- Fetch the file directly using the pointer from the hash table, avoiding full list traversal.
  
- This hybrid method significantly reduces search time and improves efficiency.

## Inode in Operating System
Inodes, short for index nodes, are data structures in Unix-style file systems that store metadata about files and directories. Each inode represents a file or directory and contains information like its size, ownership, permissions, and the location of its data blocks.

### Key Information Stored in an Inode

*1. Ownership Information*

- UID – User ID of the owner

- GID – Group ID of the owner

*2. File Type and Size*

- File type – Regular file, directory, device, etc.

- File size – In bytes

*3. Timestamps*

- Last modification time – When file data was last changed

- Last access time – When file was last read

- Inode change time – When inode metadata was last modified

*4. File Permissions & Metadata*
   
- Access permissions (read, write, execute)

- Access control lists (ACLs)

- Other administrative flags

*5. Data Block Pointers*
   
- 12 Direct Pointers – Point to first 12 data blocks

- 1 Single Indirect Pointer – Points to a block containing more data block addresses

- 1 Double Indirect Pointer – Points to a block of pointers to indirect blocks

- 1 Triple Indirect Pointer – Points to blocks of double indirect blocks (used for very large files)

###  Breaking Down the Inode Structure
The inode (index node) is a fundamental data structure in a file system that stores essential information about files and directories, excluding the file name and data content. It contains metadata and pointers to data blocks, enabling efficient file access and management. The inode structure is designed to handle both small and very large files using a combination of direct and indirect block references.

![image](https://github.com/user-attachments/assets/a50fceb1-e617-4e7a-97de-bdecc6a115ac)

*Direct Block*

Direct blocks are the simplest and fastest method of accessing a file's data. These are pointers stored directly in the inode that point to actual data blocks on the disk. Typically, an inode has around 12 direct block pointers. If a file is small, all its contents can be directly accessed through these pointers without any additional levels of indirection. This setup provides fast and efficient access to small files since the data blocks are immediately reachable.

*Single Indirect Block*

When a file exceeds the size that direct blocks can handle, the inode uses a single indirect block. Instead of pointing to a data block, the inode now points to an intermediate block (the indirect block), which itself contains multiple pointers to actual data blocks. This method allows the file system to accommodate larger files by adding an additional layer between the inode and the data.

*Double Indirect Block*

For even larger files, the inode utilizes a double indirect block. In this setup, the inode contains a pointer to a block that stores pointers to multiple single indirect blocks. Each single indirect block, in turn, points to the actual data blocks. This adds another level of abstraction and significantly increases the number of data blocks a file can address, thus supporting medium-to-large file sizes.

*Triple Indirect Block*

The triple indirect block mechanism is used when a file grows to a very large size. Here, the inode points to a block that references several double indirect blocks. Each double indirect block then points to multiple single indirect blocks, which finally point to the actual data blocks. This three-layer structure allows the file system to support extremely large files, making the inode highly scalable in terms of file size.

*Attribute Section*
Apart from data pointers, the inode also holds various metadata fields that describe the file. This includes:

- File size in bytes.

- Permissions, which define read, write, and execute access for users, groups, and others.

- File type, such as regular file, directory, symbolic link, or device file.

- Timestamps including the last access time, last modified time, and inode change time.

- Owner and group information, represented by the numeric UID (User ID) and GID (Group ID).

- These attributes help the operating system manage access control, auditing, and storage efficiently.

## File Access Methods in Operating System
File access methods define how data is read from and written to files stored on storage devices. Different operating systems may support one or multiple file access methods, and selecting the right method is key for optimizing data management and system performance.

There are three main ways to access files:

1.Sequential-Access

2.Direct Access

3.Index sequential Method

### Sequential Access
Sequential access is the simplest and most common method of accessing files. In this method, the information in the file is processed in a strict linear order, one record after another. This approach is typical in applications like editors and compilers, where the file is read or written sequentially from start to finish. A read operation, often called "read next," reads the next record and automatically advances a file pointer that keeps track of the current position. Similarly, a write operation appends data to the end of the file and moves the pointer forward to the newly written data. Sequential access is particularly suitable for storage devices like tapes, where data is naturally stored in a linear sequence.

![image](https://github.com/user-attachments/assets/efd7413b-ea56-401a-a751-1c4f13e8834a)

### Direct Access Method
The direct access method, also known as relative access, allows files to be read or written in any order. It treats the file as a sequence of numbered blocks or records, each of fixed length, and lets the system access any block directly by specifying its relative block number. This means that a program can jump immediately to any record without having to read through the previous ones. The numbering typically starts from zero, and there is no restriction on the sequence in which records are accessed. This method takes advantage of disk drives’ ability to perform random access, allowing rapid reading and writing at arbitrary locations within the file.

![image](https://github.com/user-attachments/assets/d57e4c5f-b272-4ef2-9fef-9e6316215af2)

### Index Sequential method
The index sequential method builds upon the sequential access method by introducing an indexing mechanism. It maintains an index that works like the index in a book, where the index entries point to various blocks or records in the file. To locate a particular record, the system first searches the index to find the approximate location and then uses sequential access from that point to find the exact record. This hybrid approach combines the straightforwardness of sequential access with the speed of direct access. By controlling pointers with the help of the index, this method supports efficient searching and retrieval, making it suitable for applications requiring both sequential and random file access.

![image](https://github.com/user-attachments/assets/300076f7-9f1c-4640-a010-8343b0394022)

## File Allocation Methods
### Contiguous Allocation
In contiguous allocation, each file occupies a set of contiguous blocks on the disk. This means that all the blocks of a file are stored one after the other in a continuous sequence. The operating system keeps track of the starting block and the length (number of blocks) of each file. This method provides excellent performance because of fast access—especially for sequential and direct access—since all blocks are physically close to each other.

However, this method suffers from external fragmentation, where free space gets scattered over time, making it difficult to find large enough contiguous blocks for new files. Also, it requires knowing the file size in advance, which is not always possible.

### Linked Allocation
In linked allocation, each file is made up of scattered disk blocks, which are linked together using pointers. Each block contains the data along with a pointer to the next block in the file. The operating system only needs to know the location of the first block of the file (called the head pointer), and from there, it can follow the pointers to access the entire file.

This method eliminates external fragmentation and doesn’t require knowing the file size in advance. However, it is not efficient for direct access, as it must follow pointers from the beginning to reach a specific block. It also incurs overhead due to the storage of pointers in each block and may be vulnerable to pointer corruption.

### Indexed Allocation
In indexed allocation, each file has its own index block that contains all the pointers to its data blocks. The index block acts like a table that lists the disk block numbers used by the file. When accessing a block, the system refers to the index block to locate the exact data block.

This method supports both sequential and direct access efficiently and eliminates external fragmentation. It also avoids the pointer overhead of linked allocation. However, it may require extra space for the index blocks, especially for large files, and the performance may degrade if the index itself becomes large and needs to be stored across multiple blocks.


# I/O System Management
I/O (Input/Output) devices are hardware that enables a computer to interact with the outside world, allowing data to be entered or received. Device drivers are software programs that facilitate communication between the operating system and these I/O devices. 

### I/O Devices
*Input devices:*

These devices allow users to input data into the computer (e.g., keyboard, mouse, microphone, scanner). 

*Output devices:*

These devices display data or information from the computer (e.g., monitor, printer, speakers). 

*Input/Output devices:*

Some devices can perform both input and output functions (e.g., touch screen, modem). 

## Device Driver and Its Purpose
Device drivers are specialized software programs that serve as intermediaries between a computer's operating system and its hardware components. These drivers play a vital role in ensuring that the hardware can function correctly and interact smoothly with the software environment. Without proper device drivers, a hardware device would be unable to perform its designated tasks, rendering it useless to the system.

### What is a Device Driver?
A device driver is a specific type of software designed to control and manage a particular hardware component. It enables the hardware to communicate effectively with the operating system by acting as a translator between the two. When hardware is connected to a computer, the operating system relies on the device driver to send and receive signals via the system’s buses or subsystems. These drivers are often referred to simply as "drivers" or sometimes "hardware drivers." They are essential for the hardware to perform its intended function properly.

![image](https://github.com/user-attachments/assets/23a36f62-ae28-4a03-85dd-54a2250e21c5)


### Working of a Device Driver
Device drivers operate by receiving instructions from the operating system and converting them into commands that the hardware can understand. Once the hardware performs the required action, the driver may also relay responses or status messages back to the operating system. This communication ensures that the OS is aware of the hardware's state and behavior. For instance, a printer driver translates the OS's printing instructions into a format the printer can interpret, while a sound card driver transforms digital data from an MP3 file into audio signals. Devices such as card readers, modems, sound cards, printers, USB drives, and more all depend on appropriate drivers to function correctly.

![image](https://github.com/user-attachments/assets/8820536c-b78f-4d2c-a1bb-aef744bec659)


### Types of Device Drivers
Device drivers can be broadly classified into two major types based on how they interact with the operating system:

*Kernel-mode Device Drivers*

Kernel-mode drivers are integrated with the operating system and are responsible for controlling core system hardware such as the BIOS, motherboard, processor, and other critical components. These drivers are loaded with the OS and are essential for the basic operation of the system. As they operate in the kernel space, they have high-level privileges and are fundamental to system stability and performance.

*User-mode Device Drivers*

User-mode drivers, on the other hand, are designed for peripheral devices that the user may add to the system after initial setup. These include plug-and-play devices such as USB drives, printers, webcams, and external audio devices. Unlike kernel-mode drivers, user-mode drivers operate in user space, meaning they have limited access to core system resources and are generally safer to manage or update without affecting system integrity.

## Spooling

Spooling, which stands for Simultaneous Peripheral Operation Online, is a technique used in operating systems to manage data by temporarily storing it in a designated area on the disk until a device is ready to process it. This approach is especially useful when multiple tasks are to be handled concurrently. The spool acts similarly to a buffer, holding data—such as jobs or requests—until the respective peripheral device, like a printer or plotter, is available to handle them.

The key idea behind spooling is that the disk serves as a large and persistent buffer that can queue numerous jobs, thereby allowing the operating system to manage tasks more efficiently. It helps in coordinating slow peripheral devices with the faster system processes, ensuring smooth and orderly task execution. A typical application of spooling is in printing, where several documents are placed in a print queue and are then printed sequentially as the printer becomes ready. This not only improves system performance but also enables better multitasking and resource sharing among users and processes.

![image](https://github.com/user-attachments/assets/b225d68b-b6eb-481c-a50a-ca9860075ad3)

## Buffering
Buffering is a technique used in operating systems where a designated area in the main memory, called a buffer, temporarily stores data that is being transferred between devices or between a device and an application. The primary purpose of buffering is to handle the speed mismatch between the sender and the receiver during data transmission. It acts as a holding area that enables smooth and efficient data flow, even when the sender and receiver operate at different speeds.

For instance, if the sender transmits data slower than the receiver can process it, the buffer at the receiver’s side accumulates incoming bytes until there's enough data to proceed with further processing. Conversely, if the sender is faster, the buffer at the sender's side temporarily holds data until the receiver is ready. This method of temporary storage ensures that no data is lost during transmission and improves the overall performance and coordination of data exchanges in the system.

![image](https://github.com/user-attachments/assets/f1598bd5-6c83-4229-a40f-f33067b922d9)

## Caching
Caching is a technique used to temporarily store data in a high-speed storage area known as a cache, which is typically faster than the main hard disk. The primary goal of caching is to reduce the time it takes to access data that is frequently used. Instead of repeatedly retrieving the same data from a slower storage device like a hard drive, the system retrieves it from the cache, significantly improving performance and efficiency.

Caching is especially useful in scenarios where the same data is accessed multiple times. For example, when a user opens a website for the first time, it may take longer to load as the data is fetched from the internet. However, the caching mechanism stores this data, and when the user visits the website again, the content loads much faster because it is served from the cache instead of being fetched again from the original source. This technique ensures quicker access, reduced latency, and smoother system operations.

## difference between Caching, Spooling, and Buffering

| Feature              | **Caching**                                            | **Spooling**                                                    | **Buffering**                                                         |
| -------------------- | ------------------------------------------------------ | --------------------------------------------------------------- | --------------------------------------------------------------------- |
| **Purpose**          | To store frequently accessed data for faster retrieval | To queue and manage multiple jobs/devices for orderly execution | To temporarily hold data during transfer between devices or processes |
| **Used In**          | Memory systems, browsers, CPU cache                    | Printers, batch processing systems                              | Input/output operations, video streaming                              |
| **Storage Location** | Fast memory (e.g., cache memory or SSD)                | Disk storage (used as a large queue)                            | Main memory (RAM)                                                     |
| **Operation Type**   | Improves read speed by storing copies of data          | Manages jobs for slow devices like printers                     | Manages speed mismatch between sender and receiver                    |
| **Data Type**        | Frequently accessed or recently used data              | Entire jobs or files waiting for execution                      | Streamed data or intermediate data                                    |
| **Persistence**      | Temporary (evicted when not needed)                    | Temporary until processed                                       | Temporary during transfer                                             |
| **Example**          | Website data, CPU instructions                         | Print jobs queued for printer                                   | Video buffering while streaming                                       |

# Disk Scheduling
Disk scheduling algorithms play a vital role in managing how data is read from and written to a computer’s hard disk. These algorithms determine the order of disk I/O (Input/Output) requests, directly affecting system performance, data retrieval speed, and overall efficiency.

### What is Disk Scheduling?
Disk Scheduling, also known as I/O Scheduling, is a technique used by the Operating System to decide the sequence in which I/O requests are serviced by the disk controller. Since only one request can be processed at a time, others must wait in a queue. Efficient scheduling ensures minimum wait time, reduced disk arm movement, and faster data access.

*Importance of Disk Scheduling*

- Multiple I/O requests may arrive simultaneously from different processes, and the disk can handle only one at a time.
- Requests might be far apart on the disk, leading to large disk arm movements (high seek time).
- Hard drives are relatively slow compared to other components, making optimization critical.
- Proper disk scheduling improves:
- Data retrieval speed
- System responsiveness
- Overall throughput

## First Come First Serve (FCFS)

FCFS is the simplest disk scheduling algorithm. It services disk I/O requests in the exact order in which they arrive. Although fair and free from starvation, FCFS often results in longer average seek times.

### Algorithm Steps:
Given:
requestQueue[]: An array of track numbers requested, in order of arrival.

initialHead: An integer representing the starting position of the disk head.

totalSeekCount: A variable to store the cumulative number of seek operations.

### Improved Algorithm:
Initialize totalSeekCount = 0

Set currentHead = initialHead

For each track in requestQueue[]:
a. Compute absolute distance:
     distance = abs(track - currentHead)
b. Add to total seek count:
     totalSeekCount += distance
c. Update head position:
     currentHead = track
Repeat until all requests in requestQueue are serviced.


Input:

requestQueue[] = {82, 170, 43, 140, 24, 16, 190}
initialHead = 50

Seek Order:

50 → 82 → 170 → 43 → 140 → 24 → 16 → 190

Seek Operations:
|50−82| + |82−170| + |170−43| + |43−140| + |140−24| + |24−16| + |16−190|

= 32 + 88 + 127 + 97 + 116 + 8 + 174 = **642**

Advantages:
Very simple and easy to implement.
No starvation; all requests are guaranteed to be served.

Disadvantages:
High average seek time.
Inefficient for large or heavily loaded queues.

## Shortest Seek Time First (SSTF)

SSTF services the disk I/O request that is closest to the current head position, minimizing the seek operations at each step. It provides better performance than FCFS by selecting the nearest track request at every stage.

### Advantages of SSTF:
Better performance and lower total seek time than FCFS.

Higher throughput in batch processing environments.

Lower average response and waiting time.

### Disadvantages of SSTF:
Starvation is possible for distant requests.

Lack of predictability due to dynamic selection of nearest tracks.

Direction switching may cause unnecessary delay.

Algorithm Steps (Improved Format):

Given:
requestQueue[]: Array containing disk track requests.

initialHead: Initial position of the disk head.

totalSeekCount: Variable to accumulate total seek operations.

visited[]: Boolean array to mark whether a track has been serviced.

### Algorithm:
Initialize totalSeekCount = 0, currentHead = initialHead, and mark all requests as unvisited.
Repeat until all requests are serviced:

a. For each unvisited track in requestQueue, compute distance = abs(track - currentHead)

b. Find the unvisited track with minimum distance

c. Add this distance to totalSeekCount

d. Update currentHead to this track

e. Mark this track as visited

Return totalSeekCount and the seek sequence

Example

Input:
requestQueue[] = {176, 79, 34, 60, 92, 11, 41, 114}
initialHead = 50

Processing:
Start at 50. Choose the nearest unvisited track at every step.

![image](https://github.com/user-attachments/assets/b0aabc60-602a-4a37-b1ef-3a2783713c01)


Seek Sequence:
50 → 41 → 34 → 11 → 60 → 79 → 92 → 114 → 176

Total Seek Operations:
204

## SCAN
SCAN, also known as the Elevator Algorithm, is a disk scheduling algorithm used to determine the order in which disk I/O requests are serviced.

Imagine a disk arm like an elevator: it moves in one direction (say towards track 0), servicing requests along the way. When it reaches the end, it reverses and services the remaining requests in the opposite direction.

*Key Concept*

-The disk arm moves in one direction and services all the requests it encounters until it reaches the end of the disk.
-Then it reverses direction and continues servicing remaining requests.

*Components*

- Request Array: List of track numbers to be accessed.
- Initial Head Position: Where the disk head starts.
- Direction: Initial direction of the disk head movement (left or right).

*How SCAN Works (Steps)*

Step 1:
Sort all the disk track requests in ascending order.

Step 2:
Split the requests into:

Those to the left of the initial head position.
Those to the right of the initial head position.
Step 3:
Move the disk head in the specified direction:

If moving left, service all smaller track numbers.
If moving right, service all larger track numbers.
Step 4:
When the head reaches the end of the disk (like track 0 or max track), it reverses direction.

Step 5:
Continue servicing requests in the new direction.

Example

Input:
Request sequence = {176, 79, 34, 60, 92, 11, 41, 114}
Initial head = 50
Direction = left
Sorted:
{11, 34, 41, 60, 79, 92, 114, 176}

Left of 50:
{11, 34, 41} → serviced in descending order: 41 → 34 → 11

After 11, the head moves to 0 (end of disk).

Then reverse:

Right side:
60 → 79 → 92 → 114 → 176

Seek Sequence:
41 → 34 → 11 → 0 → 60 → 79 → 92 → 114 → 176

*Advantages of SCAN*

- No starvation – All requests are eventually serviced.
- More efficient than FCFS in most scenarios.
- Good average response time for many types of workloads.

*Disadvantages of SCAN*

- Not completely fair – Requests just behind the head can be delayed for a long time.
- The head always goes to the end of the disk, even if no request is there (wasted movement).
- Slightly more complex to implement than FCFS.
  
*Analogy*

Think of it like this:
An elevator moves in one direction, stopping at every requested floor (track), then reverses at the bottom or top, picking up others on the way back.

## C-SCAN
C-SCAN (Circular SCAN) is a disk scheduling algorithm that is a modified version of the SCAN (Elevator) Algorithm. It solves a major limitation of SCAN: unfairness in servicing requests.

Instead of moving the head back and forth like an elevator, C-SCAN moves the disk head in only one direction (usually left to right), servicing requests. When it reaches the end of the disk, it jumps directly to the beginning (cylinder 0) without servicing any request during the return.

This is why it’s called the Circular Elevator Algorithm—it treats the disk like a circular list of cylinders.

*How C-SCAN Works*

Input:
Request sequence = {176, 79, 34, 60, 92, 11, 41, 114}
Initial head position = 50
Direction = right
Disk size (assumed max cylinder) = 199
Steps:
Sort the request sequence:
Sorted = {11, 34, 41, 60, 79, 92, 114, 176}
Separate requests into:
Right of 50: {60, 79, 92, 114, 176}
Left of 50: {11, 34, 41}
Move Right from 50:
Service 60 → 79 → 92 → 114 → 176
Go to end of disk:
Move from 176 to 199 (last track), even if no request exists
Jump to beginning (0):
Head jumps from 199 → 0 (without servicing)
Continue moving right:
Service 11 → 34 → 41

*Seek Sequence:*

60 → 79 → 92 → 114 → 176 → 199 → 0 → 11 → 34 → 41

*Seek Operations:*

Calculate total distance (seek count):

50 → 60 = 10
60 → 79 = 19
79 → 92 = 13
92 → 114 = 22
114 → 176 = 62
176 → 199 = 23 (go to end of disk)
199 → 0 = 199 (jump back to start)
0 → 11 = 11
11 → 34 = 23
34 → 41 = 7
Total Seek Count = 10 + 19 + 13 + 22 + 62 + 23 + 199 + 11 + 23 + 7 = 389

*Advantages of C-SCAN*

- Provides uniform response times for all requests.
- Avoids starvation—all requests are eventually serviced.
- Works well under heavy loads.
-Ensures fairness by treating all tracks equally regardless of position.

*Disadvantages of C-SCAN*

- Slightly less efficient in terms of total head movement compared to SCAN.
- It can result in longer jumps (like 199 → 0), especially if few requests are present.
  
*Analogy*

Imagine a circular elevator that only picks people up on the way up. Once it reaches the top, it comes back down without stopping, and then starts picking people again.

## Disk Management
Key Components of Disk Management

1. Disk Formatting

Disk formatting prepares a storage device for use by the operating system. It includes two levels:

Low-Level Formatting (Physical Format):

This process divides the disk into sectors that the disk controller can read and write. Each sector typically consists of:
- A header (with metadata)
- The actual data (commonly 512 bytes)
- An error correction code (ECC)
- Low-level formatting is performed by the manufacturer and is rarely done by users.

Logical Formatting (Creating a File System):

- This step creates the OS’s file system structures (such as allocation tables and free space maps). It enables the OS to store and manage files on the disk.
- To enhance efficiency, file systems often group multiple blocks into clusters. While disk I/O operates in terms of blocks, file I/O works in terms of clusters. - Typical sector sizes range from 256 to 1024 bytes. Larger sector sizes reduce the number of headers and trailers, allowing more space for user data.

2. Partitioning

Partitioning divides a physical disk into multiple logical units or partitions, each treated by the OS as a separate disk. These partitions are often structured around cylinder groups, allowing for better data organization, multi-boot setups, and improved fault isolation.

3. Booting from Disk

The boot process begins when the computer is powered on. A small program stored in the bootstrap ROM initiates the system:

- The ROM contains a minimal bootstrap loader that locates the full bootstrap program from the boot block on disk.
- The full bootstrap code then loads the OS kernel into memory and transfers control to it, starting the operating system.
- A disk that contains the operating system is known as a boot disk or system disk. Because ROM is non-volatile and read-only, it is safe from malware but difficult to update. Therefore, only the minimal loader resides in ROM, while the full bootstrap program can be modified and resides on disk.

4. Bad Block Recovery

Disks are prone to physical defects, often referred to as bad blocks, even when new. These can occur due to mechanical failures or manufacturing imperfections. 

They are typically managed using:

Sector Sparing (Sector Remapping):
The disk controller replaces defective sectors with spare ones.

Soft Errors:
Handled through ECC during read/write operations.

Hard Errors:
Require manual intervention and may result in data loss.

Types of disk failures include:

- Complete disk failure (requiring replacement and data restoration from backup)
- Partial sector corruption
- Factory-detected bad sectors
- Controllers maintain a list of such bad blocks to avoid using them during normal operation.

5. Raw Disk Access (Raw I/O)

Some operating systems allow special programs to bypass the file system and directly access a disk partition as a raw, sequential array of logical blocks. This approach, known as raw I/O, is particularly useful for applications like databases that require high-performance or specialized data handling.

### Additional Disk Management Techniques

Disk Space Allocation:
Determines how space is assigned to files. 

Common methods include:
- Contiguous Allocation
  
- Linked Allocation
  
- Indexed Allocation

Disk Defragmentation:
Over time, files become fragmented, spreading across different areas of the disk. Defragmentation rearranges data to store files in contiguous sectors, improving read/write performance.

*Advantages of Disk Management*
- Efficient organization and use of storage
  
- Improved data integrity and reliability
  
- Enhanced performance through techniques like clustering and defragmentation
  
- Supports advanced functionalities like multiple partitions and boot management

*Disadvantages of Disk Management*

- Increased system overhead
- Higher complexity in managing multiple partitions and file systems
- Risk of data loss during formatting, partitioning, or in case of improper management

## Data Protection and Security

Access Control: Permissions, User Roles

*What is RBAC?*

Role-Based Access Control (RBAC), also known as role-based security, is a widely-used access control mechanism that restricts system access based on users' roles within an organization. Instead of assigning permissions to each individual user, RBAC groups permissions into roles, and then assigns those roles to users based on their job responsibilities.

This model simplifies access management, enhances security, and ensures that users only have access to the data and resources necessary for their role—helping organizations enforce the principle of least privilege.

*How RBAC Works*

*RBAC consists of three main components:*

Users – Individuals who need access to system resources

Roles – Groups of permissions that reflect specific job functions

Permissions – Rules that define allowed operations (e.g., read, write, delete) on system resources

A user is assigned one or more roles, and each role is granted specific permissions. This means that managing access becomes a matter of modifying roles rather than individual user privileges—significantly reducing administrative overhead and the chance of human error.

Example:

In an HR system, roles can be defined as:

HR Manager – Can view and update all employee records

Employee – Can view only their own details

RBAC Model & Overlapping Roles
RBAC is additive in nature, meaning that if a user is assigned multiple roles, their effective permissions are the union of all permissions from those roles.

Example:

A user assigned both the Organizer (create, edit, view events) and Registrant (view, register for events) roles in an event management system will have all combined privileges—able to create, edit, view, and register for events.


*Benefits of RBAC*

- Simplified permission management through predefined roles
  
- Easier auditing of user permissions and access
  
- Consistent and repeatable access assignments
  
- Scalable management as user base grows
  
- Enhanced security by reducing the risk of excessive permissions
  
- Regulatory compliance through better access control practices
  
- Supports third-party access via predefined roles
  
RBAC in Practice: 

Truth Table Example

![image](https://github.com/user-attachments/assets/1c95ee09-d9f5-4547-a64e-22590169c9a5)

Here, the "Reader" role is a subset of the "Writer" role, demonstrating how different levels of access can be structured.

### Types of Access Control (RBAC & Alternatives)

Access control mechanisms regulate who can access or use resources in a system. RBAC is one of several models available:

*RBAC (Role-Based Access Control)*

- Assigns permissions based on roles
  
- Scalable and easy to audit
  
- Ideal for organizations with well-defined job functions

*Discretionary Access Control (DAC)*

- Resource owners decide who can access their resources
  
- Offers more flexibility but is less secure
  
- Suitable for less regulated environments
  
- Can be implemented via RBAC

*Mandatory Access Control (MAC)*

- Central authority defines access based on security levels
  
- Common in government/military contexts
  
- Provides higher security
  
- Can be enforced using RBAC with predefined classifications

*Access Control List (ACL)*

- Lists attached to each resource/object specifying user permissions
  
- Detailed but complex to manage at scale

*Practical Access Matrix Example*
![image](https://github.com/user-attachments/assets/56fb154c-dc2c-43da-8bb3-0f2f9ddc7447)

*RBAC vs Other Access Control Models*

RBAC vs ACL

RBAC provides system-wide access control based on user roles, which is easier to manage and scale. ACL is more granular and suited for object-specific permissions but becomes complex with many users or systems.

RBAC vs ABAC (Attribute-Based Access Control)

ABAC uses policies and user attributes (like department, location, or time) for more dynamic access decisions. ABAC offers finer control but requires more processing and complexity. RBAC is better for standardized, job-based access, while ABAC is used for more nuanced, condition-based access control.

*Implementing Role-Based Access Control*

Understand Business Needs
Conduct a needs analysis, identify key job functions, and assess security and regulatory requirements.

Plan Scope of Implementation
Define which systems/applications to prioritize—typically those that handle sensitive data.

Define Roles
Create roles that reflect real job functions. Avoid excessive granularity and role overlap.

Implement Gradually
Begin with a pilot group and coarse-grained roles. Refine over time based on feedback and monitoring.

# File System Integrity and Recovery

A file system is responsible for managing how data is stored and retrieved on a storage device. Ensuring its integrity means keeping the data structures and stored files consistent and correct, even in the event of system crashes, hardware failures, or power loss. File system recovery refers to the techniques used to restore a file system to a consistent state after such failures.

## What is File System Integrity?

File system integrity ensures that:

- Files are not lost or corrupted.
- Directory structures are consistent.
- Metadata (e.g., file size, timestamps, block pointers) remains accurate.
- All referenced data blocks actually exist and unreferenced blocks are not wasted.

Integrity issues may occur due to:

- Power failures  
- Software bugs  
- Hardware malfunctions  
- Improper shutdowns  

## Sources of Inconsistency

Common scenarios where file system integrity might be compromised:

- **Interrupted writes**: A system crash during file write can cause partial updates.
- **Metadata mismatch**: File size in the directory entry doesn’t match actual allocated blocks.
- **Lost blocks**: Blocks that are marked as used but aren’t referenced by any file.
- **Duplicate block allocation**: Two files point to the same physical disk block.
- **Orphaned files**: File data exists but has no entry in the directory.

## File System Consistency Techniques

### Synchronous Writes

- Critical metadata updates are done in order and forced to disk before proceeding.
- Ensures consistency but is slower due to frequent disk operations.

### Write-Ahead Logging (Journaling)

- All changes are first recorded in a log (journal) before being applied to the file system.
- If a crash occurs, the system replays or rolls back the log to reach a consistent state.
- Common in modern file systems like ext3, ext4, NTFS.

### Copy-on-Write (COW)

- Instead of overwriting data, changes are written to new blocks, and then metadata pointers are updated.
- Prevents corruption from partial writes.
- Used in file systems like ZFS and Btrfs.

### Checksums and Hashing

- Data blocks and metadata can include checksums to detect corruption.
- Helps in identifying and correcting integrity issues.

## File System Recovery

Recovery refers to restoring consistency after a crash or error. Recovery techniques vary based on the integrity method used.

### FSCK (File System Consistency Check)

- A utility that scans file system structures and metadata for inconsistencies.
- Performs actions like:
  - Reconnecting orphaned files to a `lost+found` directory
  - Releasing unreferenced blocks
  - Correcting block counts and sizes

**Examples:**

- `fsck` for ext2/ext3/ext4 (Linux)
- `chkdsk` for FAT/NTFS (Windows)

### Journaling Recovery

If the file system supports journaling:

- On reboot, it reads the journal.
- If a transaction was fully written, it replays it.
- If it was incomplete, it rolls back the changes.

This makes recovery fast and automatic.

## Examples of File Systems with Recovery Support

| File System | Integrity Feature         | Recovery Support                       |
|-------------|---------------------------|----------------------------------------|
| ext3/ext4   | Journaling                | Automatic recovery using journal       |
| NTFS        | Journaling (metadata)     | Uses logs to recover after crash       |
| ZFS         | Copy-on-write, Checksums  | Self-healing, rollback, snapshots      |
| Btrfs       | COW, Checksums            | Crash-consistent and robust recovery   |

## Best Practices to Maintain File System Integrity

- Always shut down systems properly.
- Use journaling or COW-enabled file systems.
- Regularly run `fsck` or equivalent tools.
- Maintain backups for critical data.
- Use RAID or redundant storage for hardware fault tolerance.
- Monitor SMART data for disk health.

# Data Encryption and Backup Strategies

In today’s digital world, protecting data from unauthorized access and ensuring its availability in case of failure or disaster are critical. Two fundamental aspects of data security and management are **data encryption** and **backup strategies**.

## Data Encryption

Data encryption is the process of converting plain data (plaintext) into an unreadable format (ciphertext) using algorithms and keys. Only authorized users with the correct decryption key can access the original data.

### Why Encrypt Data?

- **Confidentiality**: Protect sensitive information from unauthorized access.
- **Integrity**: Prevent data tampering or unauthorized modification.
- **Compliance**: Meet regulatory requirements (e.g., GDPR, HIPAA).
- **Secure communication**: Protect data transmitted over networks.

### Types of Encryption

- **Symmetric Encryption**
  - Uses a single key for both encryption and decryption.
  - Faster but requires secure key distribution.
  - Examples: AES (Advanced Encryption Standard), DES.

- **Asymmetric Encryption (Public-Key Cryptography)**
  - Uses a pair of keys: public key (encryption) and private key (decryption).
  - Solves the key distribution problem.
  - Examples: RSA, ECC (Elliptic Curve Cryptography).

- **Hashing (One-way encryption)**
  - Converts data into a fixed-size hash value.
  - Used for data integrity and password storage.
  - Examples: SHA-256, MD5 (not recommended due to vulnerabilities).

### Encryption in Practice

- **At Rest**: Encrypt data stored on disks or databases.
- **In Transit**: Use protocols like SSL/TLS to encrypt data sent over networks.
- **End-to-End Encryption**: Data is encrypted on the sender’s device and only decrypted on the receiver’s device (e.g., WhatsApp).

## Backup Strategies

A backup is a copy of data stored separately to restore in case of data loss, corruption, or disasters.

### Importance of Backup

- Recover data after accidental deletion or corruption.
- Protect against hardware failure.
- Defend against ransomware and cyberattacks.
- Ensure business continuity.

### Types of Backups

- **Full Backup**
  - Complete copy of all data.
  - Simple but time-consuming and requires more storage.

- **Incremental Backup**
  - Backs up only data changed since the last backup (full or incremental).
  - Faster and saves storage but recovery takes longer (needs last full + all incrementals).

- **Differential Backup**
  - Backs up data changed since the last full backup.
  - Faster than full backup but slower than incremental.
  - Recovery needs last full + last differential backup.

### Backup Storage Options

- **Local Backup**: External hard drives, tapes, NAS devices.
- **Offsite Backup**: Data stored at a different physical location.
- **Cloud Backup**: Using cloud services (AWS, Google Cloud, Azure) for scalable and reliable backup.

### Best Practices for Backup

- Follow the **3-2-1 rule**:
  - Keep at least **3 copies** of data.
  - Store on **2 different media types**.
  - Keep **1 copy offsite**.
- Regularly test backup restoration.
- Automate backups to avoid human error.
- Use encryption for backup data to protect it from theft.
- Maintain versioning to restore previous data versions.

## Relationship Between Encryption and Backup

- Encrypt backups to secure data even if backup storage is compromised.
- Encryption keys must be securely stored and managed.
- Backup solutions should support encrypted data to maintain confidentiality.

## Summary

| Topic              | Key Points                                                                 |
|--------------------|------------------------------------------------------------------------------|
| **Data Encryption** | Converts data to unreadable form to protect confidentiality and integrity. Types: Symmetric, Asymmetric, Hashing. |
| **Backup Strategies** | Copies of data stored for recovery. Types: Full, Incremental, Differential. Use local, offsite, or cloud storage. |
| **Best Practices**    | 3-2-1 rule, encryption of backups, regular testing, automation, secure key management. |






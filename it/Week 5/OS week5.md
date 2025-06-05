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


## Disk Scheduling in Operating Systems

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

```
Input:
requestQueue[] = {82, 170, 43, 140, 24, 16, 190}
initialHead = 50

Seek Order:
50 → 82 → 170 → 43 → 140 → 24 → 16 → 190

Seek Operations:
|50−82| + |82−170| + |170−43| + |43−140| + |140−24| + |24−16| + |16−190|

= 32 + 88 + 127 + 97 + 116 + 8 + 174 = **642**
```
*Advantages:*
Very simple and easy to implement.
No starvation; all requests are guaranteed to be served.

*Disadvantages:*
High average seek time.
Inefficient for large or heavily loaded queues.


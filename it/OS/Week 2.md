# Operating System Structures

System software is a category of low-level software that directly manages and controls a computer’s hardware components. It acts as a bridge between the user and the physical hardware, enabling other software (like applications) to function properly. It is essential for the basic functioning of any computer system.
## Importance
System software plays a crucial role in the functioning of a computer system for several reasons:

Hardware Communication: It acts as a bridge between hardware and application software, enabling seamless interaction and coordination between the two.

### Resource Management:
System software efficiently manages system resources such as CPU, memory, and storage, ensuring optimal performance and balanced resource allocation among tasks.

### Security: 
It implements essential security features like firewalls, antivirus programs, and data encryption to safeguard the system from unauthorized access, malware, and other threats.

### User Interface:
It provides the necessary interfaces—graphical or command-line—that allow users to interact with the system and perform various operations.

### Application Execution: 
It offers the foundation for installing, managing, and running application programs by providing essential runtime services and libraries.

### System Configuration and Customization: 
System software enables users to modify settings and configure the environment according to their preferences, offering better control and flexibility.

## Key Features of System Software
System software, particularly the operating system, is equipped with several essential features that enable efficient and secure system operation:

### Memory Management:
The operating system manages the system’s primary memory (RAM) by keeping track of each memory location and allocating memory to processes when requested. It also reclaims memory once a process terminates, ensuring optimal memory utilization.

### Processor Management:
The OS handles process scheduling and CPU allocation. It assigns CPU time to processes based on scheduling policies and deallocates it when a process completes or is interrupted.

### File Management:
The system software is responsible for managing files on storage devices. It handles the creation, deletion, reading, writing, and access permissions of files and directories, ensuring secure and efficient file operations.

### Security Management:
System software ensures the protection of data and resources from unauthorized access through authentication mechanisms such as passwords, encryption, and access control policies.

### Error Detection and Handling:
It includes features for detecting and reporting system errors. Tools like system dumps, trace logs, and diagnostic messages help identify and resolve faults, ensuring system reliability.

### Process Scheduling:
The operating system uses various scheduling algorithms (like Round Robin, Priority Scheduling, etc.) to determine the order in which processes execute, maximizing CPU efficiency and system responsiveness.

### Types of System Software
System software is essential for managing hardware and supporting the execution of application software. Below are the major types of system software:

## 1. Operating System (OS)
The Operating System is the core system software that manages hardware resources and provides services for application software. It acts as an interface between the hardware and the user.

### Key Functions:

- *Resource Management:* Manages CPU time, memory, and peripheral devices across processes.

- *Process Management:* Handles process creation, execution, scheduling, and termination.

- *Memory Management:* Optimizes allocation and deallocation of RAM for active processes.

- *File Management:* Controls how data is stored, retrieved, and organized in the file system.

- *Device Management:* Manages communication between the OS and hardware devices through drivers.

- *Security:* Implements authentication and access control mechanisms for users and data.

Examples: Windows, Linux, macOS, Android

## 2. Programming Language Translators
These tools translate high-level code into machine-level code so that it can be executed by the system.

### Types of Translators:

*Compiler:*
Translates entire high-level programs into machine code in one go.
Efficient for execution but slower in compilation.
Examples: gcc, javac, g++

*Interpreter:*
Translates and executes code line by line.
Suitable for scripting and debugging.
Examples: Python, Ruby, PHP

*Assembler:*
Converts assembly language code into machine language.
One-to-one correspondence between instructions.

Common in embedded and hardware-specific development.

### 3. Device Drivers
Device drivers are programs that enable the operating system to communicate with hardware components.
- Act as translators between the OS and hardware devices.
- Ensure proper functioning of devices like keyboards, printers, and displays.
- Most are pre-installed by manufacturers.

Examples: Printer drivers, USB drivers, Graphics drivers

### 4. Firmware
Firmware is low-level software embedded directly into hardware components. It provides the instructions needed for devices to communicate with other system components.

- Resides in non-volatile memory (ROM, Flash, EPROM).
- Essential for booting and basic device control.

*Types:*
- BIOS (Basic Input/Output System) – Initializes hardware during boot.
- UEFI (Unified Extensible Firmware Interface) – A modern, more secure replacement for BIOS.

### 5. Utility Software
Utility programs are specialized tools that help monitor, maintain, and optimize system performance.

- System Maintenance: Disk cleanup, defragmentation, backup.

- Security: Antivirus, firewall, malware detection.

- *Data Compression:* Tools like WinRAR and WinZip reduce storage usage.

- *Recovery & Partitioning:* Helps with data recovery and managing disk partitions.

Examples: CCleaner, WinZip, Norton Antivirus, Disk Management

https://www.geeksforgeeks.org/system-software/

## User Mode and Kernel Mode

User mode and kernel mode are two working states inside a laptop’s working system that determine the level of access and control, a technique can have over machine resources. Understanding the differences among these modes is critical to knowing how modern working systems manage safety and resource allocation.

### User Mode?
When a Program is booted up on an Operating system let’s say Windows, then it launches the program in user mode. When a user-mode program requests to run, a process and virtual address space (address space for that process) are created for it by Windows. User-mode programs are less privileged than kernel-mode applications and are not allowed to access the system resources directly. For instance, if an application under user mode wants to access system resources, it will have to first go through the Operating system kernel by using syscalls.  

In user mode, applications run with limited privileges to prevent direct access to hardware, ensuring system stability. In kernel mode, the operating system has unrestricted access to all hardware resources, enabling it to perform critical tasks such as memory management and process control.

**Advantages**
- Stability and Reliability
- Simplified Debugging

**Disadvantages**
- Performance Overhead
- Limited Access

## Kernel Mode?
The kernel is the core program on which all the other operating system components rely, it is used to access the hardware components and schedule which processes should run on a computer system and when, and it also manages the application software and hardware interaction. Hence it is the most privileged program, unlike other programs, it can directly interact with the hardware. When programs running under user mode need hardware access for example webcam, then first it has to go through the kernel by using a syscall, and to carry out these requests the CPU switches from user mode to kernel mode at the time of execution. After finally completing the execution of the process the CPU again switches back to the user mode.

**Advantages**
- Direct Hardware Access
- Complete Control

**Disadvantages**
- Increased Risk
- Complex Debugging

## User vs Kernel Mode

| Criteria                | Kernel Mode                                                                 | User Mode                                                                 |
|-------------------------|------------------------------------------------------------------------------|----------------------------------------------------------------------------|
| Access to Resources     | In kernel mode, the program has direct and unrestricted access to system resources. | In user mode, the application program do not have direct access to system resources. In order to access the resources, a system call must be made. |
| Interruptions           | In Kernel mode, the whole operating system might go down if an interrupt occurs | In user mode, a single process fails if an interrupt occurs.               |
| Modes                   | Kernel mode is also known as the master mode, privileged mode, or system mode. | User mode is also known as the unprivileged mode, restricted mode, or slave mode. |
| Virtual address space   | In kernel mode, all processes share a single virtual address space.          | In user mode, all processes get separate virtual address space.            |
| Level of privilege      | In kernel mode, the applications have more privileges as compared to user mode. | While in user mode the applications have fewer privileges.                 |
| Restrictions            | As kernel mode can access both the user programs as well as the kernel programs there are no restrictions. | While user mode needs to access kernel programs as it cannot directly access them. |
| Mode bit value          | The mode bit of kernel-mode is 0.                                            | While the mode bit of user-mode is 1.                                      |
| Memory References       | It is capable of referencing both memory areas.                              | It can only make references to memory allocated for user mode.             |
| System Crash            | A system crash in kernel mode is severe and makes things more complicated.   | In user mode, a system crash can be recovered by simply resuming the session. |
| Access                  | Only essential functionality is permitted to operate in this mode.           | User programs can access and execute in this mode for a given system.      |
| Functionality           | The kernel mode can refer to any memory block in the system and can also direct the CPU for the execution of an instruction, making it a very potent and significant mode. | The user mode is a standard and typical viewing mode, which implies that information cannot be executed on its own or reference any memory block; it needs an Application Protocol Interface (API) to achieve these things. |

## Role of a Shell and Interpreter in user interaction
In user interaction, a shell acts as a command-line interpreter, enabling users to interact with the operating system by typing commands and having them executed. An interpreter, on the other hand, is a computer language interface that executes code line by line on user demand. The shell provides the interactive environment, while the interpreter handles the actual execution of the user's instructions. 
*Shell:*
The shell is the interface between the user and the operating system's kernel. It takes user input in the form of commands, interprets them, and translates them into instructions the OS can understand and execute. Essentially, it acts as a command-line interpreter, allowing users to navigate the file system, run programs, and interact with the system. 
*Interpreter:*
An interpreter is a program that executes code (e.g., Python, JavaScript) line by line. It translates the source code into a form that the computer can understand and execute. Many programming languages provide an interactive shell interface, allowing users to directly execute code snippets within the shell.

## Process Management
*Process Management:* OS function that handles the creation, scheduling, and termination of processes.

### In Single-tasking/Batch Systems:
Only one process active at a time.
Process management is simple.

### In Multiprogramming/Multitasking Systems:
Multiple processes active at the same time.
OS must share CPU among them efficiently.
*Requires:*
CPU scheduling
Process synchronization
Resource sharing
Inter-process communication (IPC)

### Types of Processes:
*1. CPU-bound Process:*
Requires more CPU time
Spends most time in Running state
Example: Heavy calculations

*2. I/O-bound Process:*
Requires more I/O time
Spends most time in Waiting state
Example: File or network operations

## States of a Process in Operating Systems

New: This state represents a newly created process that hasn’t started running yet. It has not been loaded into the main memory, but its process control block (PCB) has been created, which holds important information about the process.
Ready: A process in this state is ready to run as soon as the CPU becomes available. It is waiting for the operating system to give it a chance to execute.
Running: This state means the process is currently being executed by the CPU. Since we’re assuming there is only one CPU, at any time, only one process can be in this state.
Blocked/Waiting: This state means the process cannot continue executing right now. It is waiting for some event to happen, like the completion of an input/output operation (for example, reading data from a disk).
Exit/Terminate: A process in this state has finished its execution or has been stopped by the user for some reason. At this point, it is released by the operating system and removed from memory.

https://media.geeksforgeeks.org/wp-content/uploads/20241017162800402546/five-state-model.png

## Process Control Block (PCB) 
Process Control Block (PCB) is a data structure used by the Operating System to store all information about a process.
It is essential for process management and scheduling.

### Primary Terminologies Related to PCB 
https://media.geeksforgeeks.org/wp-content/uploads/20230702175558/Add-a-subheading(1).png
The Process State is a crucial component stored in the PCB that indicates the current status of a process. A process may be in different states such as running, waiting, ready, or terminated. This helps the operating system in efficiently managing and scheduling the execution of multiple processes.

The Process ID (PID) is a unique identifier assigned by the operating system when a process is created. It helps the OS distinguish and manage different processes independently.

The Program Counter holds the address of the next instruction to be executed. During a context switch, the current value of the program counter is saved in the PCB, allowing the process to resume execution from the point it was interrupted.

The CPU Registers contain important data and intermediate values required by the process while it's running. When a context switch occurs, the contents of these registers are saved into the PCB to preserve the process's state.

The Memory Information in the PCB includes details such as the base address and the size of memory allocated to the process. This information is critical for memory management and ensuring that each process operates within its assigned memory boundaries.

The Process Scheduling Information includes data like process priority, scheduling algorithms being used, and pointers to scheduling queues. This information helps the operating system make decisions on which process to execute next.

Lastly, the Accounting Information in the PCB tracks resource usage metrics such as CPU time used, memory consumed, and execution time. This data is essential for monitoring performance and implementing billing or logging mechanisms in multi-user systems.

## Context Switching
Context Switching is a fundamental mechanism in an operating system that allows the CPU to switch from one process to another, enabling multitasking and efficient resource utilization. It involves saving the current state (context) of an active process and restoring the state of another process that is ready to run. This switching ensures that multiple processes can progress over time, even if only one CPU is available.

The OS maintains each process's state information in its Process Control Block (PCB). When a context switch occurs, the OS saves the state (such as CPU registers, program counter, etc.) of the currently running process into its PCB and then loads the saved state of the new process from its PCB into the CPU. This allows the new process to resume execution as if it had never been interrupted.

Need for Context Switching
- A mechanism that allows the CPU to switch from one process to another.
- Saves the state of the current process and loads the state of the next scheduled process.
- Enables multitasking on a single CPU system.

### 1.CPU Sharing
-Allows multiple processes to share a single CPU.
-Enables fair execution and progress of all processes.

### 2.Process Continuity
-Stores the current execution state (context) of a process.
-When resumed, the process continues from where it left off.

### 3.Resource Management
-Helps OS to efficiently use CPU time by switching to ready processes while others are waiting (e.g., for I/O).

### 4.No Direct Process Switching
-One process cannot directly transfer control to another.
-OS uses context switching to manage this indirect control transfer.

### 5.Simulated Parallelism
-Allows a single CPU to handle multiple processes simultaneously (in a time-shared manner).
-No need for multiple processors.

### Context Switching Triggers 
Triggers are events or conditions that cause the operating system to perform a context switch—i.e., switch the CPU from one process to another.

## Main Categories of Triggers:
### 1. Interrupts
Occur when external or internal hardware signals need immediate CPU attention (e.g., I/O device requests).
Example: If a process requests data from disk and an interrupt occurs, the CPU switches to an interrupt handler.
The current process state is saved, and after handling the interrupt, the system resumes the previous process.

### 2. Multitasking
In multitasking environments, context switching is triggered to allocate CPU time fairly among processes.
The OS uses scheduling algorithms to decide when to switch.
The state of the currently running process is saved so it can continue later from the same point.

### 3. User/Kernel Mode Switch
Triggered when the system switches between user mode and kernel mode.
Common during system calls or when a process requests an OS-level service.
Requires context switch to switch the privilege level and handle the request securely.

## Monolithic Kernel vs Microkernel:
Monolithic kernels and microkernels are distinct approaches to operating system design. Monolithic kernels, like Linux, combine all kernel functions into a single executable, offering faster performance and easier implementation. Microkernels, on the other hand, separate kernel services into distinct processes, prioritizing security and modularity at the cost of some performance. 

### Monolithic Kernel:
*Pros:*
Simpler Design and Implementation:Monolithic kernels are easier to design and implement because all kernel functions are tightly integrated. 
Direct Access to Resources:They provide direct access to system resources, potentially leading to faster performance. 
Higher Performance:Communication between kernel components is more efficient due to their execution in the same address space. 
*Cons:*
Security Risks: A larger codebase can increase the risk of security vulnerabilities. 
System-Wide Failures: If a single component fails, the entire system may crash. 
Limited Modularity: Extending or modifying a monolithic kernel can be complex. 

### Microkernel:
*Pros:*
Improved Security: Separating kernel components into distinct processes enhances security by isolating faults. 
Enhanced Modularity: Adding or removing services is easier because microkernels are modular, allowing for easier extensibility. 
High Reliability: Faults in one process are less likely to affect other parts of the system. 
*Cons:*
Slower Performance: Communication between processes, often via message passing, can introduce overhead and latency. 
Increased Complexity: Microkernels are more complex to design and implement. 
More Code: Implementing a microkernel requires more code than a monolithic kernel.

## Modular Structure in Operating Systems
-Modular structure is a design approach for the operating system where the kernel is divided into core components and additional services are added as dynamically loadable modules.
-This approach allows modules to be added or removed during runtime or boot time, enhancing flexibility and scalability.

https://media.geeksforgeeks.org/wp-content/uploads/20241122132346739251/modular---------os---------structure-768.webp

Key Features:
### 1. Core Kernel
-The kernel consists of a minimal set of core components that manage basic functionalities like memory management, process scheduling, and hardware interaction.

### 2. Dynamically Loadable Modules
-Additional functionalities or services are provided through modules that can be loaded and unloaded dynamically without the need to restart the system.
-Modules can include device drivers, filesystems, networking protocols, etc.

### 3. Flexibility Over Layered Structure
-Unlike layered structure, where each layer has fixed interactions, a modular structure allows any module to interact with any other module.
-This loose coupling makes the system more flexible and adaptable.

### 4. Defined and Protected Interfaces
-Although modules can interact freely, each module is designed with protected interfaces to ensure system stability and security.
-This approach maintains the integrity of the core kernel while providing flexibility to add new features.

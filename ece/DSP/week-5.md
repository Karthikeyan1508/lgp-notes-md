# INTRODUCTION OF SIGNALS, SYSTEMS & SIGNAL PROCESSING
## Signal: 
A signal is defined as any physical quantity that varies with time, space or any
other independent variable or variables. 
## Signal Processing:
The operation which one carried out in the signal by the system
one called as signal processing. 
## System: 
It is defined as the physical device that performs an operation upon the signal
## Basic elements of digital signal processing.
1. Most of the signals encountered in science and engineering are analog in nature. 
2. That is, the signals are functions of a continuous variable, such as time or space. And 
    usually take on values in a continuous range. 
3. Such signals are processed directly by appropriate analog systems.
![image](https://github.com/user-attachments/assets/a4575abc-1df0-4f53-ba84-f37f40baf082)

## ADC (Analog to digital converter)
1. It is the interface between analog signal and digital signal processor. 
2. It converts analog signal to digital data.

## Digital signal processor 
1. It is nothing only a programmable microprocessor programmed to perform the desired 
   operation on the inputted signal. 
2. The digital signal processor may be a large programmable digital computer or a small 
microprocessor programmed to perform the desired operations on the input signal. 
3. It may also be a hardwired digital processor configured to perform a specified Set of 
operations on the input signal.

## DAC (digital to Analog converter) 
  It is the interface between processed digital data and output analog signal. 
  Digital Signal Processing 
 ## Classify signals 

1. Continuous time signal  
    The signal which can be defined for every point of time in an interval is called as 
    continuous time signal. 
    Example: X (t) = cosπt.

![image](https://github.com/user-attachments/assets/04350446-cc22-4316-821c-6ad7366e7c18)

2. Discrete time signal  
    The signal which is only defined on specific point of time is called discrete time signal. 
    Example: X(n) = 2n , n≥ 0 
                  = 1 ,   n< 0 
![image](https://github.com/user-attachments/assets/6a64c4af-d3ea-4407-825f-bb04d35465f9)

3. Continuous valued signal: 
    The signal which takes on all possible values on a finite or an infinite range is called as 
continuous valued signal. 

4. Discrete valued signal: 
   The signal which takes on values from a finite set of possible values is called as discrete
valued signal. 

# DISCRETE TIME SIGNALS & SYSTEMS 

## Some elementary discrete time signals. 

  ![image](https://github.com/user-attachments/assets/e5aa5a4a-057a-4e37-a239-192ced9ec99c)

## Classify discrete time signal.

Depending upon the various characteristics of the signals the discrete time signals are can be classified as:

1. Energy signal & process signals. 
2. Periodic and a periodic singles.
3. Symmetric (even) and antisymmetric (odd) signals.  

# Energy signal & process signals 
  The signal which has finite energy and zero average process.  
  𝑥(𝑡) is an energy signals if 0<𝐸<∞ and 𝑝=0 where 𝐸→ energy and 𝑃→process 
  of the signals 𝑥(𝑡).  

![image](https://github.com/user-attachments/assets/7e79c322-c6c4-4ada-8930-e37a305d2908)

 Energy of 0 signals must be finite
 Non periodic signals are energy signals

Power signal.  These signals are fine limited  
          Power energy signal is Zero
The signal which has finite average power and infinite energy. 
𝑥(𝑡) is a power signal of 0<𝑝<∞  and 𝐸= ∞ 

![image](https://github.com/user-attachments/assets/45f1887f-5f04-4625-8073-cd91918b6f47)

Practical periodic signals are power signals. 
These signals can exist over infinite time.  
Energy of the power signal is infinite.   

# Block diagram representation of discrete time system. 
![image](https://github.com/user-attachments/assets/0179ea98-aa99-44a8-b82d-e14ea2474470)

# Multiplication
It is a memoryless operation where a constant is multiplied into every sample and depicted as 
follows.  

![image](https://github.com/user-attachments/assets/77feb0e1-3efe-414f-a321-ac6f0ab4019e)

## Classify  discrete time system 

** Static systems and dynamic system. **

If output of a discrete time system at any instant ‘𝑛’ depends only  on that the sample of 
input at that instant not on future or past input samples in called static system.  
Ex.:-  𝑦(𝑛) = 𝑎𝑥(𝑛) 
y(𝑛) = 5𝑥(𝑛)+𝑏𝑥3(𝑛)  

** Dynamic System: (System With Memory) **

If output of a discrete time system at any instant ‘𝑛’ depends upon future or past input 
samples then the system is called as dynamic system or system with memory.  
Ex.  𝑦(𝑛) = 𝑥(𝑛 −1)+3𝑥(𝑛+1) 

** Time Invariant System: (Shift Invariant System) **

If input-output characteristic of a system does not change with time is called time invariant 
system or shift invariant system. 

**  Linear System.  **

A linear system is the type of the system which satisfies the superposition principle. 

**Superposition principle** 







  
 




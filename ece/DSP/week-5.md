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

**Static systems and dynamic system.**

If output of a discrete time system at any instant ‘𝑛’ depends only  on that the sample of 
input at that instant not on future or past input samples in called static system.  
Ex.:-  𝑦(𝑛) = 𝑎𝑥(𝑛) 
y(𝑛) = 5𝑥(𝑛)+𝑏𝑥3(𝑛)  

**Dynamic System: (System With Memory)**

If output of a discrete time system at any instant ‘𝑛’ depends upon future or past input 
samples then the system is called as dynamic system or system with memory.  
Ex.  𝑦(𝑛) = 𝑥(𝑛 −1)+3𝑥(𝑛+1) 

**Time Invariant System: (Shift Invariant System)**

If input-output characteristic of a system does not change with time is called time invariant 
system or shift invariant system. 

**Linear System.**

A linear system is the type of the system which satisfies the superposition principle. 

**Superposition principle** 
    Superposition principle  
It states that response of the system to a weighted sum of signals be equal to the 
corresponding weighted sum of the responses of the system to each of the individual 
input signals.  

[𝑎,𝑥,(𝑛) + 𝑎2𝑥2(𝑛)] = 𝑎1𝑇 [𝑥1(𝑛)]+𝑎2𝑇 [𝑥2(𝑛)] 
Where 𝑎1& 𝑎2 are the arbitrary constants and 𝑥1(𝑛) & 𝑥2(𝑛) are the arbitrary input 
sequences. 

**Non liner system:** 
  The system which does not satisfy the superposition principle is called as nonlinear system. 

**Causal system & Non-Causal System**
    The signal 𝑥(𝑛) is said to be causal if it’s value is zero for 𝑛 < 0 otherwise the 
signal is non causal.

** Non-Causal Signal**

  The signal 𝑥(𝑛) is said to be non-causal if it’s value is zero for 𝑛 > 0 
otherwise the signal is  causal.  

## convolution and interconnection of LTI system
 
* → Symbol for convolution  

![image](https://github.com/user-attachments/assets/46d3a5e0-8aef-4246-aedd-aa174aa83a8a)


![image](https://github.com/user-attachments/assets/e5e22d72-f65d-4cda-b7de-28eecba81b78)

## Linear time – invariant system one classified as two types depending on response towards impulse 

## 1. FIR System 

    The LTI System which response a finite duration inpulse sequence is called as FIR 
system.  
    The response or output to such sequence is given by 


![image](https://github.com/user-attachments/assets/2bef4b2e-ae74-4c21-b7f6-2655aaf0121c)
FIR System has a finite memory of length –M samples.

## IIR (Infinite-duration impulse response LTI) system  
  
 The LTI system which responds to infinite duration impulse sequence is called as IIR 
system. 

The response or output to such sequence is given by

![image](https://github.com/user-attachments/assets/d683b0e7-4752-4c0f-acce-40fae022d418)
 IIR system has infinite memory length

## Recursive and non-recursive discrete time system

Recursive- Involving a process that is applied repeatedly  

**Recursive system: **
 The system whose output / response 𝑦(𝑛) at time 𝑛 depends on any number of 
post output values like 𝑦(𝑛 − 1),𝑦(𝑛 − 2)…. and also presented post inputs are 
called as recursive system.  
 Response or output of a recursive system can be given by  


![image](https://github.com/user-attachments/assets/278557a9-7a6f-43ec-a543-8448fb2b5b9d)
The recursive system consists of a loop and delay element  
 The output of a recursive system can only be computed in order like 𝑦(𝑛),𝑦(1),…… . 
 Memory cant required  

Non recursive system:- 

 The system whose output or response 𝑦(𝑛) at time n. depends on only past and present 
input voters are called as non recursive system.  
 Output of non recursive system can be given by  

f(𝑛) = 𝐹[𝑥(𝑛),𝑥(𝑛 −1),…𝑥(𝑛 −𝑚)] 

  All non recursive system  are causal FIR system.  
 The basic realization of non recursive system is 


![image](https://github.com/user-attachments/assets/ccf4747b-e3a9-4097-83aa-a5019eef824c)

There is no delay and feedback in non delay and feedback in non recursive system.  
Output of a non recursive system can be computed in any order like 𝑦(20),𝑦(15)….. 
Memory less.  

## Z-transform 

Z-transform is a mathematical tool which transformer changes time domain desire the time signal 

x(𝑛). Into Z-domain.  

![image](https://github.com/user-attachments/assets/7991b26b-5cdd-47d7-8d2d-684b6565f442)

## ROC (Region of convergence) 

ROC of 𝑥(𝑍). Is defined as the regional set of values of z for which 𝑥(𝑍) attains a finite value.  

1. 𝑥(𝑛)=𝛿(𝑛) 


![image](https://github.com/user-attachments/assets/66544df1-6f5d-493e-9952-20fcd48738aa)


 ## Properties of Z-Transform 

Linearity Property 

![image](https://github.com/user-attachments/assets/bfbcd28f-43f0-4dcd-9bea-a14110feba0c)

Time Reversal 

![image](https://github.com/user-attachments/assets/06e15eb9-cd86-41e6-8ffc-a8471280489f)

Time shifting  


![image](https://github.com/user-attachments/assets/aafe670e-8b50-4d7e-a88d-64eec188958c)

 Scaling Property:  

![image](https://github.com/user-attachments/assets/4e567719-8296-4f02-9c31-d702ee163aa4)

Differentiation property  

![image](https://github.com/user-attachments/assets/18613072-f5d7-43e7-a7f0-28cf63d198fe)

Convolution property


![image](https://github.com/user-attachments/assets/c5e4cf5b-4208-4a81-90ba-4c7c337d385a)

##  Poles and Zores:

x(𝑍) is a national function if this is ratio of two polynomials in 𝑍−1𝑜𝑟𝑍


![image](https://github.com/user-attachments/assets/28ec4644-a5df-435f-887c-4e3b78657094)

Zeros : The values of Z at which 𝑥(𝑍)𝑄=0 are eared as Zero  
Poles: The values of z at which 𝑥(𝑍)=∞ are called as poles  
In representation of 𝑥(𝑧)graphically by a pole –Zero plot (pattern) in the complier which shows 
the location of poles by crosses (x) and zeros by circles (0)  
Roc should not contain any pole.  

## DISCUSS FOURIER TRANSFORM

Discrete Fourier Transform is a computational or mathematical tool for analyzing discreet time signal 
in frequency domain.  
DFT consents 𝑥(𝑛) (Discrete time domain signal of infinite length to discrete frequency sequence 
x(𝐾) of finite length.  
DFT is obtained by sampling one period of the Fourier transform at finite number of frequency points. 

![image](https://github.com/user-attachments/assets/74732960-1bdd-4ecb-b09f-53d4e489e34d)

## Property of DFT

Periodicity linearity & symmetry property 


![image](https://github.com/user-attachments/assets/0dce8557-5d02-482c-b603-5a0cb2c5f7fb)

**Multiplication of tow DFTS:**

![image](https://github.com/user-attachments/assets/5d4099f8-378a-4b95-a8f5-ead5c77d70b4)

## Multiplication of two DFT. & circular convolution

 Let 𝑥1(𝑛) & 𝑥2(𝑛) one finite duration sequence both of length 𝑁. 
X(𝐾) & 𝑥2(𝐾) be DFTs of 𝑥1(𝑛) & 𝑥2(𝑛) respecivally  
Let 𝑥3(𝑛) be another sequence whose DFT is 𝑋3 (𝐾) 
Where 𝑋3(𝐾)=𝑋1(𝐾)𝑥2(𝐾)


![image](https://github.com/user-attachments/assets/4df36773-36d9-4b71-beab-a03e77331745)

## FAST FOURIER TRANSFORM ALGORITHM & DIGITAL FILTERS 

** DFT & FFT. Algorithm**

FFT is a providence for computing  
DFT of a finite series easily  
It is nothing only set of algorithm 
It is used in digital spectral analysis filter simulation, auto connection and pattern recognition.  
FFT is based on decomposition and breaking the transform into smaller transforms and combining 
them to get the total transform.  

FFT algorithm basically bits two properties of twiddle factor.  


![image](https://github.com/user-attachments/assets/bdc0c854-4ac2-4db1-84cb-57779c52a5e8)


There are two types of FFT algorithms 

(i) Decimation in –time 
(ii) Decimation in frequency  


In decimation –in time algorithm, the sequence for which we need the DFT is successively divided 
into smaller sequences and the DFTs of these entire sequences are combined in a certain portion to 
obtain the required DFT of entire sequence.  
 In Decimation –in- frequency algorithm the frequency sample of the DFT are decomposed into smaller 
and smaller subsequences in a certain pattern.  

**Direct computation of DFT.  
**


![image](https://github.com/user-attachments/assets/28297cba-794a-44ac-96f5-ced9c86ca311)

 **Radix – 2 algorithm** 

Radix -2 algorithm is also known as radix -2 decimation –in-time (DIT) algorithm.  
In Radix-2 algorithm number of output points (N). can be expressed as power of 2. i.e. 𝑁=2𝑀 we 
have 𝑀 is an integer 


![image](https://github.com/user-attachments/assets/3918553a-3479-49bd-9d6a-29460fae4d54)


![image](https://github.com/user-attachments/assets/d4684fa9-f2b8-44dc-ad4b-5c373db76fba)


![image](https://github.com/user-attachments/assets/bca9e596-9597-4cad-b18d-be6a36a95594)

**Butterworth Filters**

Butterworth filters are characterized by the property that the magnitude characteristic is
maximally flat at the origin, and there are no ‘ripples’, either in the pass band or in the stop
band. The sequence of topics covered is as follows:
 The Butterworth filter, its specifications
 The nth order Low-pass Butterworth filter with unity cut-off
 Design steps in obtaining the transfer function of the filter to meet the specifications
 Frequency transformation to obtain high-pass, band-pass and band-elimination filters
 Practical realization of Butterworth filters
 Practical realization of Butterworth filters
 Simulation results of few implementations (using the Multisim circuit simulation tool)
 Matlab code used in obtaining the results

Butterworth filters are characterized by the property that the magnitude characteristic is
maximally flat at the origin of the s plane. The transfer function of an nth
order Low-passButterworth filter is given by:


![image](https://github.com/user-attachments/assets/4f34bd9c-138f-4177-a7a5-5ab02aa49cd5)


![image](https://github.com/user-attachments/assets/346dfe86-0676-4840-8294-678bef2f9679)

The poles lie on the left half of the s-plane
 They have the 3 dB cut-off at 1rad/sec
 The complete filter is specified by the order n
 Through frequency transformation, it is possible to transform the above transfer
function to another filter of specified cut-off or type
 The attenuation at a given frequency for a given order is given by


![image](https://github.com/user-attachments/assets/d1a0afe5-83b3-4954-96fe-ecc65fe755ca)

The design steps for obtaining the transfer function of the Butterworth filter are as
follows:
1. Given the frequency specifications, obtain the equivalent specifications of the
low-pass filter (need two frequencies with desired attenuation)
2. Assume we need to have attenuation of As, Ap at frequencies fs and fp
respectively. Then this corresponds to the specifications of low-pass filter


![image](https://github.com/user-attachments/assets/f66eda33-b213-4f4b-a8e0-891d45d135bc)

The order n, of the desired filter is a smallest integer that satisfies the equation
given below: 


![image](https://github.com/user-attachments/assets/a1311f5e-0d68-43f0-8652-2253a87f8989)


![image](https://github.com/user-attachments/assets/4964e6fc-d226-4ea7-a632-f2b68d5cdeee)

The continuous frequency transformation is given by:


![image](https://github.com/user-attachments/assets/2806809b-5ff6-4a7b-b727-d971c3b10af0)


























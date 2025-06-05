
# Control Systems

A control system manages commands, directs or regulates the behavior of other devices or systems using control loops. It can range from a single home heating controller using 
a thermostat controlling a domestic boiler to large Industrial control systems which are used for controlling processes or machines. A control system is a system, which provides the 
desired response by controlling the output. The following figure shows the simple block diagram of a control system.

![image](https://github.com/user-attachments/assets/dce388d6-618f-4931-8ee7-a48df44619f0)

## Classification of Control Systems

Based on different parameters, we can classify the control systems into the following ways. 
### Continuous time and Discrete-time Control Systems 
- Control Systems can be classified as continuous time control systems and discrete 
time control systems based on the type of the signal used. 
- In continuous time control systems, all the signals are continuous in time. But, 
in discrete time control systems, there exists one or more discrete time signals.

### SISO and MIMO Control Systems 
- Control Systems can be classified as SISO control systems and MIMO control systems 
based on the number of inputs and outputs present. 
- SISO (Single Input and Single Output) control systems have one input and one output. 
Whereas, MIMO (Multiple Inputs and Multiple Outputs) control systems have more than one input and more than one output.

### Open Loop and Closed Loop Control Systems
- Control Systems can be classified as open loop control systems and closed loop control 
systems based on the feedback path. 
- In open loop control systems, output is not fed-back to the input. So, the control action is 
independent of the desired output.
The following figure shows the block diagram of the open loop control system. 

![image](https://github.com/user-attachments/assets/bdbe5fb9-95d3-47cb-bcf4-71ae95409dd0)

 In closed loop control systems, output is fed back to the input. So, the control action
 is dependent on the desired output.
  The following figure shows the block diagram of negative feedback closed loop control
 system.

 ![image](https://github.com/user-attachments/assets/4998cbba-adc6-47a6-8059-0eeae01230b9)

The error detector produces an error signal, which is the difference between the input and the feedback signal. This feedback signal is obtained from the block (feedback elements) by 
considering the output of the overall system as an input to this block. Instead of the direct input, the error signal is applied as an input to a controller. 
So, the controller produces an actuating signal which controls the plant. In this combination, the output of the control system is adjusted automatically till we get the desired response. 
Hence, the closed loop control systems are also called the automatic control systems. Traffic lights control system having sensor at the input is an example of a closed loop control system. 
The differences between the open loop and the closed loop control systems are mentioned in the following table:

 ![image](https://github.com/user-attachments/assets/bc776372-9738-46c3-81f5-668fda9dbf2d)

 ## Types of Feedback
  There are two types of feedback:
- Positive feedback
- Negative feedback
### Positive Feedback
The positive feedback adds the reference input, R(s)R(s) and feedback output. The following figure shows the block diagram of positive feedback control system 

![image](https://github.com/user-attachments/assets/981b9bd7-5f69-4867-8e7b-36e7396296a9)

The concept of transfer function will be discussed in later chapters. For the time being, consider the transfer function of positive feedback control system is,

![image](https://github.com/user-attachments/assets/6ba1fdaf-fade-4f0d-989d-8baecba9af85)

Where, 
- T is the transfer function or overall gain of positive feedback control system.
- G is the open loop gain, which is function of frequency. 
- H is the gain of feedback path, which is function of frequency.

### Negative Feedback
Negative feedback reduces the error between the reference input, R(s)R(s) and system  output. The following figure shows the block diagram of the negative feedback control 
system.

![image](https://github.com/user-attachments/assets/5b1fda0d-87fa-4863-8623-6ffa1c4b74a6)
Transfer function of negative feedback control system is,

![image](https://github.com/user-attachments/assets/b10dfc17-1bab-4bca-afcd-cf54d1aad9c3)
Where, 
- T is the transfer function or overall gain of negative feedback control system. 
- G is the open loop gain, which is function of frequency. 
- H is the gain of feedback path, which is function of frequency.
- 
## Representataion of Transfer Function

### Block Diagrams
Block diagrams consist of a single block or a combination of blocks. These are used to represent the control systems in pictorial form.

### Basic Elements of Block Diagram 
The basic elements of a block diagram are a block, the summing point and the take-off point. Let us consider the block diagram of a closed loop control system as shown in the following 
figure to identify these elements.

![image](https://github.com/user-attachments/assets/5506b128-d3cd-4f41-b616-6159fd452413)

The above block diagram consists of two blocks having transfer functions G(s) and H(s). It is also having one summing point and one take-off point. Arrows indicate the direction of the 
flow of signals. Let us now discuss these elements one by one. 

### Block
The transfer function of a component is represented by a block. Block has single input and single output. 
The following figure shows a block having input X(s), output Y(s) and the transfer function G(s).

![image](https://github.com/user-attachments/assets/1d122e28-5461-489f-9c68-86cc7abbdb82)

### Summing Point 
The summing point is represented with a circle having cross (X) inside it. It has two or more inputs and single output. It produces the algebraic sum of the inputs. It also performs the 
summation or subtraction or combination of summation and subtraction of the inputs based on the polarity of the inputs. Let us see these three operations one by one. 
The following figure shows the summing point with two inputs (A, B) and one output (Y). Here, the inputs A and B have a positive sign. So, the summing point produces the output, Y 
as sum of A and B i.e. = A + B.

![image](https://github.com/user-attachments/assets/403b49fb-e5d4-4aa5-b6a4-0eadffbdc651)

The following figure shows the summing point with two inputs (A, B) and one output (Y). Here, the inputs A and B are having opposite signs, i.e., A is having positive sign and B is 
having negative sign. So, the summing point produces the output Y as the difference of A and B i.e 
Y = A + (-B) = A - B. 

![image](https://github.com/user-attachments/assets/dd923b3f-31cb-42d3-8c1d-b918cc909f5c)

The following figure shows the summing point with three inputs (A, B, C) and one output (Y). Here, the inputs A and B are having positive signs and C is having a negative sign. So, the 
summing point produces the output Y as Y = A + B + (−C) = A + B − C.

![image](https://github.com/user-attachments/assets/44d9458e-a2b2-42c3-9296-853a821b15c7)

### Take-off Point 
The take-off point is a point from which the same input signal can be passed through more than one branch. That means with the help of take-off point, we can apply the same input 
to one or more blocks, summing points.In the following figure, the take-off point is used to connect the same input, R(s) to two more blocks. 

![image](https://github.com/user-attachments/assets/5920247b-163d-4473-b067-4bb8a8a5d37e)

## Basic Connections for Blocks 
 There are three basic types of connections between two blocks.

### Series Connection
Series connection is also called cascade connection. In the following figure, two blocks having transfer functions G1(s)G1(s) and G2(s)G2(s) are connected in series.

 ![image](https://github.com/user-attachments/assets/44323b8d-38da-43aa-af22-802b2fa384d9)

That means we can represent the series connection of two blocks with a single block. The transfer function of this single block is the product of the transfer functions of those two 
blocks. The equivalent block diagram is shown below.

![image](https://github.com/user-attachments/assets/24ff7fef-66df-4892-b3f1-6c3f4851bfc2)

Similarly, you can represent series connection of ‘n’ blocks with a single block. The transfer function of this single block is the product of the transfer functions of all those ‘n’ blocks.

### Parallel Connection 
The blocks which are connected in parallel will have the same input. In the following figure, two blocks having transfer functions G1(s)G1(s) and G2(s)G2(s) are connected in parallel. 
The outputs of these two blocks are connected to the summing point. 

![image](https://github.com/user-attachments/assets/d5e05ed5-1517-4eae-a32d-1364cbee608e)

That means we can represent the parallel connection of two blocks with a single block. The transfer function of this single block is the sum of the transfer functions of those two blocks. 
The equivalent block diagram is shown below. 

![image](https://github.com/user-attachments/assets/c5d1e098-0e5b-40d3-8ab7-494db95ca7cd)
Similarly, you can represent parallel connection of ‘n’ blocks with a single block. The transfer 
function of this single block is the algebraic sum of the transfer functions of all those ‘n’ 
blocks.

### Feedback Connection 
As we discussed in previous chapters, there are two types of feedback — positive feedback and negative feedback. The following figure shows negative feedback control system. Here, 
two blocks having transfer functions G(s)G(s) and H(s)H(s) form a closed loop. 

![image](https://github.com/user-attachments/assets/d05da72a-06b2-4560-b0a0-387807d2a854)

This means we can represent the negative feedback connection of two blocks with a single block. The transfer function of this single block is the closed loop transfer function of the 
negative feedback. The equivalent block diagram is shown below.

![image](https://github.com/user-attachments/assets/27d7d2b5-2270-4725-a9f9-8216078b86ea)

Similarly, you can represent the positive feedback connection of two blocks with a single block. The transfer function of this single block is the closed loop transfer function of the positive feedback, i.e.,

![image](https://github.com/user-attachments/assets/8b815280-dcca-490f-8c0a-013a7321a6bd)

### Block Diagram Reduction Rules 

Follow these rules for simplifying (reducing) the block diagram, which is having many blocks, summing points and take-off points. 
- Rule 1 − Check for the blocks connected in series and simplify.
- Rule 2 − Check for the blocks connected in parallel and simplify.
- Rule 3 − Check for the blocks connected in feedback loop and simplify.
- Rule 4 − If there is difficulty with take-off point while simplifying, shift it towards right.
- Rule 5 − If there is difficulty with summing point while simplifying, shift it towards left.
- Rule 6 − Repeat the above steps till you get the simplified form, i.e., single block.
  
Note − The transfer function present in this single block is the transfer function of the overall 
block diagram. 
Note − Follow these steps in order to calculate the transfer function of the block diagram 
having multiple inputs.

Step 1 − Find the transfer function of block diagram by considering one input at a 
time and make the remaining inputs as zero.
Step 2 − Repeat step 1 for remaining inputs. 
Step 3 − Get the overall transfer function by adding all those transfer functions. 

The block diagram reduction process takes more time for complicated systems because; we have to draw the (partially simplified) block diagram after each step. So, to overcome this 
drawback, use signal flow graphs (representation).

### Signal Flow Graph
Signal flow graph is a graphical representation of algebraic equations. In this chapter, let us discuss the basic concepts related signal flow graph and also learn how to draw signal flow graphs.

### Basic Elements of Signal Flow Grap
Nodes and branches are the basic elements of signal flow graph. 
**Node**
 Node is a point which represents either a variable or a signal. There are three types of
 nodes — input node, output node and mixed node.
- Input Node − It is a node, which has only outgoing branches. 
- Output Node − It is a node, which has only incoming branches. 
- Mixed Node − It is a node, which has both incoming and outgoing branches.
Example 
Let us consider the following signal flow graph to identify these nodes.

![image](https://github.com/user-attachments/assets/3be556da-49f7-4fb2-a7f7-9b24d1d47bc8)
**Branch** 
Branch is a line segment which joins two nodes. It has both gain and direction. For example, there are four branches in the above signal flow graph. These branches have gains of a, b, c and -d.

## Construction of Signal Flow Graph 
Let us construct a signal flow graph by considering the following algebraic equations −

![image](https://github.com/user-attachments/assets/af23e3ea-96fc-4fe5-bcf5-919fe06cbb04)

![image](https://github.com/user-attachments/assets/52d87824-5892-48ae-9fbd-63ef207b7b91)

![image](https://github.com/user-attachments/assets/c35d8395-18c4-4994-9e5f-a0ab172f6daf)

### Conversion of Block Diagrams into Signal Flow Graphs 
Follow these steps for converting a block diagram into its equivalent signal flow graph. 
- Represent all the signals, variables, summing points and take-off points of block diagram as nodes in signal flow graph.
- Represent the blocks of block diagram as branches in signal flow graph.
- Represent the transfer functions inside the blocks of block diagram as gains of the branches in signal flow graph. 
- Connect the nodes as per the block diagram. If there is connection between two nodes (but there is no block in between), then represent the gain of the branch as one. For example, between summing points, between summing point and takeoff point, between input and summing point, between take-off point and output. 

Example
Let us convert the following block diagram into its equivalent signal flow graph. 

![image](https://github.com/user-attachments/assets/036c9b3b-34a4-4251-b710-59135842b5a4)

Represent the input signal R(s) and output signal C(s) of block diagram as input node R(s) and output node C(s) of signal flow graph. Just for reference, the remaining nodes (y1 to y9) are labeled in the block diagram. There are nine nodes other than input and output nodes. That is four nodes for four summing points, four nodes for four take-off points and one node for the variable between blocks G1and G2. 

The following figure shows the equivalent signal flow graph. 

![image](https://github.com/user-attachments/assets/90f9e464-9f9a-44ab-bf70-48d3d0041509)

Let us now discuss the Mason’s Gain Formula. Suppose there are ‘N’ forward paths in a signal flow graph. The gain between the input and the output nodes of a signal flow graph is nothing but the transfer function of the system. It can be calculated by using Mason’s gain formula. 

### Mason’s gain formula:

![image](https://github.com/user-attachments/assets/142dcc2a-922b-4792-94a4-f01424c2025e)
Where, 
- C(s) is the output node 
- R(s) is the input node 
- T is the transfer function or gain between R(s) and C(s) 
- Pi is the ith forward path gain 
Δ=1−(sum of all individual loop gains) +(sum of gain products of all possible two 
nontouching loops)−(sum of gain products of all possible three nontouching loops) 
+…. 
Δi is obtained from Δ by removing the loops which are touching the ith forward path.

### Calculation of Transfer Function using Mason’s Gain Formula
Let us consider the same signal flow graph for finding transfer function. 

![image](https://github.com/user-attachments/assets/bc7d6cfa-8442-4463-8feb-49c623542a6d)

![image](https://github.com/user-attachments/assets/981899da-4c68-4544-8ee0-a2fa2c88df1a)

![image](https://github.com/user-attachments/assets/afa0c35c-141b-464c-bc96-8e0bcdc32d3e)

### Calculating steady-state errors
Before talking about the relationships between steady-state error and system type, we will show how to calculate error regardless of system type or input. Then, we will start deriving formulas we can apply when the system has a specific structure and the input is one of our standard functions. Steady state error can be calculated from the open- or closed-loop transfer function for unity feedback systems. For example, let's say 
that we have the system given below. 

![image](https://github.com/user-attachments/assets/fb5836f8-f42f-4954-b357-e929fb37abfc)

This is equivalent to the following system, where T(s) is the closed-loop transfer function.

![image](https://github.com/user-attachments/assets/9287cf18-e974-4c84-ba4c-c7d81dccf2d5)

We can calculate the steady-state error for this system from either the open- or closed-loop transfer function using the Final Value Theorem. Recall that this theorem can only be applied if the 
subject of the limit (sE(s) in this case) has poles with negative real part.

![image](https://github.com/user-attachments/assets/aab4be95-1552-4ab1-b2b9-7668386e173d)

### Types of controllers:
- Proportional Control 
With proportional control, the actuator applies a corrective force that is proportional o the amount  of error: 
Outputp = Kp × E
Outputp = system output due to proportional control
 Kp = proportional constant for the system called gain.

- Derivative  Controller 
The derivative controller produces an output, which is derivative of the error signal.

![image](https://github.com/user-attachments/assets/4b2ef541-0f8c-4a44-9142-11540c94b3f7)

Therefore, the transfer function of the derivative controller is KDs. 
Where, KD is the derivative constant. 
The block diagram of the unity negative feedback closed loop control system along with the 
derivative controller is shown in the following figure.

![image](https://github.com/user-attachments/assets/a4f5910d-793c-4087-ac63-865e947bb3ff)

The derivative controller is used to make the unstable control system into a stable one.
- Integral Controller
The integral controller produces an output, which is integral of the error signal. 

![image](https://github.com/user-attachments/assets/53677f78-69a2-4f3e-ae68-4f7dc4b34e3d)

Where, KIKI is the integral constant. 

The block diagram of the unity negative feedback closed loop control system along with the integral controller is shown in the following figure.

![image](https://github.com/user-attachments/assets/4402bab0-90b3-4299-8f82-71b67aa13c05)

The integral controller is used to decrease the steady state error.
- Proportional Derivative (PD) Controller 
The proportional derivative controller produces an output, which is the combination of the 
outputs of proportional and derivative controllers.

![image](https://github.com/user-attachments/assets/9744854f-2206-4edc-b0c0-3dc0d316ac22)

Therefore, the transfer function of the proportional derivative controller is KP+KDs. The block diagram of the unity negative feedback closed loop control system along with the 
proportional derivative controller is shown in the following figure.

![image](https://github.com/user-attachments/assets/7d60f610-d53c-4f64-a1d2-44b1a23d0f7e)

The proportional derivative controller is used to improve the stability of control system without affecting the steady state error.
- Proportional  Integral (PI)  Controller 
The proportional integral controller produces an output, which is the combination of outputs 
of the proportional and integral controllers.

![image](https://github.com/user-attachments/assets/fbfe2e99-f276-463b-bb97-ad0e71e582e6)

The block diagram of the unity negative feedback closed loop control system along with the 
proportional integral controller is shown in the following figure. 

![image](https://github.com/user-attachments/assets/a77a7667-fdb3-4a88-bec8-e1d76b55be6e)

The proportional integral controller is used to decrease the steady state error without 
affecting the stability of the control system.
- Proportional I ntegral Derivative (PID) Controller
The proportional integral derivative controller produces an output, which is the combination 
of the outputs of proportional, integral and derivative controllers. 

![image](https://github.com/user-attachments/assets/9c73aa8a-9864-4312-a2eb-1602183f3442)

The block diagram of the unity negative feedback closed loop control system along with the 
proportional integral derivative controller is shown in the following figure.

![image](https://github.com/user-attachments/assets/c5c80d45-e042-45a7-afce-d39bcc2c79ca)

## STABILITY ANALYSIS
A system is said to be stable, if its output is under control. Otherwise, it is said to be unstable. 
A stable system produces a bounded output for a given bounded input.

### Types of Systems based on Stability
We can classify the systems based on stability as follows. 
- Absolutely stable system 
- Conditionally stable system 
- Marginally stable system

### Absolutely Stable System
If the system is stable for all the range of system component values, then it is known as 
the absolutely stable system. The open loop control system is absolutely stable if all the 
poles of the open loop transfer function present in left half of ‘s’ plane. Similarly, the closed loop control system is absolutely stable if all the poles of the closed loop transfer function present in the left half of the ‘s’ plane. 

### Conditionally Stable System 
If the system is stable for a certain range of system component values, then it is known 
as conditionally stable system.

### Marginally Stable System 
If the system is stable by producing an output signal with constant amplitude and constant 
frequency of oscillations for bounded input, then it is known as marginally stable system. 
The open loop control system is marginally stable if any two poles of the open loop transfer 
function is present on the imaginary axis. Similarly, the closed loop control system is 
marginally stable if any two poles of the closed loop transfer function is present on the 
imaginary axis. In this chapter, let us discuss the stability analysis in the ‘s’ domain using the Routh-Hurwitz stability criterion. In this criterion, we require the characteristic equation to find the stability of the closed loop control systems.

### Root Locus

Follow these rules for constructing a root locus. 
Rule 1 − Locate the open loop poles and zeros in the‘s’ plane. 
Rule 2 − Find the number of root locus branches. 
We know that the root locus branches start at the open loop poles and end at open loop 
zeros. So, the number of root locus branches N is equal to the number of finite open loop 
poles P or the number of finite open loop zeros Z, whichever is greater.
Mathematically, we can write the number of root locus branches N as 
N=P if P≥Z 
N=Z if P<Z
Rule 3 − Identify and draw the real axis root locus branches. 
If the angle of the open loop transfer function at a point is an odd multiple of 1800, then that 
point is on the root locus. If odd number of the open loop poles and zeros exist to the left 
side of a point on the real axis, then that point is on the root locus branch. Therefore, the 
branch of points which satisfies this condition is the real axis of the root locus branch. 
Rule 4 − Find the centroid and the angle of asymptotes. 
- If P=Z, then all the root locus branches start at finite open loop poles and end at finite 
open loop zeros. 
- If P>Z, then Z number of root locus branches start at finite open loop poles and end 
at finite open loop zeros and P−Z number of root locus branches start at finite open 
loop poles and end at infinite open loop zeros. 
- If P<Z , then P number of root locus branches start at finite open loop poles and end 
at finite open loop zeros and Z−P number of root locus branches start at infinite open 
loop poles and end at finite open loop zeros. 
So, some of the root locus branches approach infinity, when P≠Z. Asymptotes give the 
direction of these root locus branches. The intersection point of asymptotes on the real axis 
is known as centroid.
We can calculate the centroid α by using this formula,

![image](https://github.com/user-attachments/assets/1e121c94-045a-408b-95fa-eb0c159cb2bf)

Rule 5 − Find the intersection points of root locus branches with an imaginary axis. 
We can calculate the point at which the root locus branch intersects the imaginary axis and 
the value of K at that point by using the Routh array method and special case (ii). 
- If all elements of any row of the Routh array are zero, then the root locus branch 
intersects the imaginary axis and vice-versa. 
- Identify the row in such a way that if we make the first element as zero, then the 
elements of the entire row are zero. Find the value of K for this combination. 
- Substitute this K value in the auxiliary equation. You will get the intersection point of 
the root locus branch with an imaginary axis. 
Rule 6 − Find Break-away and Break-in points. 
- If there exists a real axis root locus branch between two open loop poles, then there 
will be a break-away point in between these two open loop poles. 
- If there exists a real axis root locus branch between two open loop zeros, then there 
will be a break-in point in between these two open loop zeros. 
Note − Break-away and break-in points exist only on the real axis root locus branches. 
Follow these steps to find break-away and break-in points. 
- Write K in terms of s from the characteristic equation 1+G(s)H(s)=0. 
- Differentiate K with respect to s and make it equal to zero. Substitute these values 
of ss in the above equation. 
- The values of ss for which the K value is positive are the break points. 
Rule 7 − Find the angle of departure and the angle of arrival. 
The Angle of departure and the angle of arrival can be calculated at complex conjugate open 
loop poles and complex conjugate open loop zeros respectively.  
The formula for the angle of departure ϕd is

![image](https://github.com/user-attachments/assets/8fc16c2c-b86e-4a2e-8e0d-0527f2741649)

Example 
Let us now draw the root locus of the control system having open loop transfer 
function,

![image](https://github.com/user-attachments/assets/a2c5717d-ad0d-43e1-8f85-c991cfa58501)

Step 1 − The given open loop transfer function has three poles at  s = 0, 
s = -1, s = -5. It doesn’t have any zero. Therefore, the number of root locus branches is equal 
to the number of poles of the open loop transfer function.

![image](https://github.com/user-attachments/assets/731d8437-b10f-4d73-a517-f06d0bbe7676)

The three poles are located are shown in the above figure. The line segment between s=−1, 
and s=0 is one branch of root locus on real axis. And the other branch of the root locus on 
the real axis is the line segment to the left of s=−5. 
Step 2 − We will get the values of the centroid and the angle of asymptotes by using the 
given formulae.

**Centroid**  
The angle of asymptotes are

![image](https://github.com/user-attachments/assets/3eccb936-5816-485f-b555-7d3d318d0f43)

The centroid and three asymptotes are shown in the following figure.

![image](https://github.com/user-attachments/assets/2de0b38c-1cad-4553-a2d5-5dafff82a1b2)

Step 3 − Since two asymptotes have the angles of 600600 and 30003000, two root locus 
branches intersect the imaginary axis. By using the Routh array method and special case(ii), 
the root locus branches intersects the imaginary axis at 

![image](https://github.com/user-attachments/assets/95ef99bf-6d20-4e0b-a4b5-aa5238e0f16d)

There will be one break-away point on the real axis root locus branch between the poles  s 
=−1 and  s=0. By following the procedure given for the calculation of break-away point, we 
will get it as s =−0.473. 
The root locus diagram for the given control system is shown in the following figure.

![image](https://github.com/user-attachments/assets/8d826796-c162-4cc2-96c9-b5f4d748b384)

![image](https://github.com/user-attachments/assets/4071e772-fe0d-4f60-9aa7-5a6e4131b589)

## FREQUENCY RESPONSE ANALYSIS

The response of a system can be partitioned into both the transient response and the steady 
state response. We can find the transient response by using Fourier integrals. The steady 
state response of a system for an input sinusoidal signal is known as the frequency response. 
In this chapter, we will focus only on the steady state response. 
If a sinusoidal signal is applied as an input to a Linear Time-Invariant (LTI) system, then it 
produces the steady state output, which is also a sinusoidal signal. The input and output 
sinusoidal signals have the same frequency, but different amplitudes and phase angles. Let 
the input signal be 

![image](https://github.com/user-attachments/assets/b6f5c64d-4621-48f0-ba6f-97058ee89642)

Where, 
- A is the amplitude of the input sinusoidal signal. 
- ω0 is angular frequency of the input sinusoidal signal. 
We can write, angular frequency ω0 as shown below. 
ω0=2πf0 
Here, f0 is the frequency of the input sinusoidal signal. Similarly, you can follow the same 
procedure for closed loop control system.

### Stability Analysis using Bode Plots 

From the Bode plots, we can say whether the control system is stable, marginally stable or 
unstable based on the values of these parameters. 
- Gain cross over frequency and phase cross over frequency 
- Gain margin and phase margin

### Phase Cross over Frequency

The frequency at which the phase plot is having the phase of -1800 is known as phase cross 
over frequency. It is denoted by ωpc. The unit of phase cross over frequency is rad/sec.

### Gain Cross over Frequency

The frequency at which the magnitude plot is having the magnitude of zero dB is known as gain cross over frequency. It is denoted by ωgc. The unit of gain cross over frequency is rad/sec. 
The stability of the control system based on the relation between the phase cross over 
frequency and the gain cross over frequency is listed below. 
- If the phase cross over frequency ωpc is greater than the gain cross over 
frequency ωgc, then the control system is stable. 
- If the phase cross over frequency ωpc is equal to the gain cross over frequency ωgc, 
then the control system is marginally stable. 
- If the phase cross over frequency ωpcis less than the gain crosses over frequency ωgc, 
then the control system is unstable.

### Gain Margin
Gain margin GMGM is equal to negative of the magnitude in dB at phase cross over 
frequency. 
GM=20log(1Mpc)=20logMpc
Where, MpcMpc is the magnitude at phase cross over frequency. The unit of gain margin 
(GM) is dB. 
Phase Margin 
The formula for phase margin PMPM is 
PM=1800+ϕgc 
Where, ϕgc is the phase angle at gain cross over frequency. The unit of phase margin 
is degrees.

NOTE:
The stability of the control system based on the relation between gain margin and phase 
margin is listed below. 

- If both the gain margin GM and the phase margin PM are positive, then the control 
system is stable.

- If both the gain margin GM and the phase margin PM are equal to zero, then the 
control system is marginally stable. 
If the gain margin GM and / or the phase margin PM are/is negative, then the control 
system is unstable. 

## Routh-Hurwitz Stability Criterion

Routh-Hurwitz stability criterion is having one necessary condition and one sufficient
condition for stability. If any control system doesn’t satisfy the necessary condition, then we
can say that the control system is unstable. But, if the control system satisfies the necessary
condition, then it may or may not be stable. So, the sufficient condition is helpful for knowing
whether the control system is stable or not.

### Necessary Condition for Routh-Hurwitz Stability

The necessary condition is that the coefficients of the characteristic polynomial should be
positive. This implies that all the roots of the characteristic equation should have negative
real parts.

Consider the characteristic equation of the order ‘n’ is -

![image](https://github.com/user-attachments/assets/94dfc100-c8f8-4c81-8542-229d25a5034a)

Note that, there should not be any term missing in the nth order characteristic equation. This means that the nth order characteristic equation should not have any coefficient that is of zero value.

### Sufficient Condition for Routh-Hurwitz Stability

The sufficient condition is that all the elements of the first column of the Routh array should
have the same sign. This means that all the elements of the first column of the Routh array
should be either positive or negative.

### Routh Array Method

If all the roots of the characteristic equation exist to the left half of the ‘s’ plane, then the
control system is stable. If at least one root of the characteristic equation exists to the right
half of the ‘s’ plane, then the control system is unstable. So, we have to find the roots of the
characteristic equation to know whether the control system is stable or unstable. But, it is
difficult to find the roots of the characteristic equation as order increases.
So, to overcome this problem there we have the Routh array method. In this method, there
is no need to calculate the roots of the characteristic equation. First formulate the Routh
table and find the number of the sign changes in the first column of the Routh table. The
number of sign changes in the first column of the Routh table gives the number of roots of
characteristic equation that exist in the right half of the ‘s’ plane and the control system is
unstable.
Follow this procedure for forming the Routh table.
- Fill the first two rows of the Routh array with the coefficients of the characteristic
polynomial as mentioned in the table below. Start with the coefficient of sn and
continue up to the coefficient of s0.
- Fill the remaining rows of the Routh array with the elements as mentioned in the table
below. Continue this process till you get the first column element of row s0s0 is an.
Here, an is the coefficient of s0 in the characteristic polynomial.

Note − If any row elements of the Routh table have some common factor, then you can
divide the row elements with that factor for the simplification will be easy.
The following table shows the Routh array of the nth order characteristic polynomial.

![image](https://github.com/user-attachments/assets/3e0770c0-4b12-46c8-85eb-0dc1535cb78c)

Example:
Let us find the stability of the control system having characteristic equation,

![image](https://github.com/user-attachments/assets/b254f414-5eed-4991-89a1-35e0f7e1b3ed)

![image](https://github.com/user-attachments/assets/d8a14371-e013-4adc-bb1e-225e1ad1cc31)

Special Cases of Routh Array
We may come across two types of situations, while forming the Routh table. It is difficult to
complete the Routh table from these two situations.
The two special cases are −
- The first element of any row of the Routh’s array is zero.
- All the elements of any row of the Routh’s array are zero.
Let us now discuss how to overcome the difficulty in these two cases, one by one.
First Element of any row of the Routh’s array is zero:
If any row of the Routh’s array contains only the first element as zero and at least one of the
remaining elements have non-zero value, then replace the first element with a small positive
integer, ϵ. And then continue the process of completing the Routh’s table. Now, find the
number of sign changes in the first column of the Routh’s table by substituting ϵϵ tends to
zero.
Example:

Let us find the stability of the control system having characteristic equation,

![image](https://github.com/user-attachments/assets/9b54cbe9-febd-41bd-94b3-b3f5df84d69a)

![image](https://github.com/user-attachments/assets/20a44ee0-ddb0-4d69-a6ef-29c3d29b6992)

![image](https://github.com/user-attachments/assets/6eabd7b4-7f53-40c6-8ba1-f4a5a9f24a09)

![image](https://github.com/user-attachments/assets/1de53500-7092-4713-b675-35dffc4954c4)

All the Elements of any row of the Routh’s array are zero
In this case, follow these two steps −
- Write the auxilary equation, A(s) of the row, which is just above the row of zeros.
- Differentiate the auxiliary equation, A(s) with respect to s. Fill the row of zeros with
these coefficients.

![image](https://github.com/user-attachments/assets/58160a11-222c-484b-8141-ea183cdbddfe)

![image](https://github.com/user-attachments/assets/cf0f715e-abc8-42b1-9214-63856b81173e)

![image](https://github.com/user-attachments/assets/3b2eabd8-ad12-4af4-ae96-7f696e14259f)

Step 3 − Verify the sufficient condition for the Routh-Hurwitz stability.
There are two sign changes in the first column of Routh table. Hence, the control system is
unstable.
In the Routh-Hurwitz stability criterion, we can know whether the closed loop poles are in
on left half of the ‘s’ plane or on the right half of the ‘s’ plane or on an imaginary axis. So, we
can’t find the nature of the control system. To overcome this limitation, there is a technique
known as the root locus.


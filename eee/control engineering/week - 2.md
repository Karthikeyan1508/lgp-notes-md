#Control Systems
A control system manages commands, directs or regulates the behavior of other devices or 
systems using control loops. It can range from a single home heating controller using 
a thermostat controlling a domestic boiler to large Industrial control systems which are used 
for controlling processes or machines. A control system is a system, which provides the 
desired response by controlling the output. The following figure shows the simple block 
diagram of a control system. 
![image](https://github.com/user-attachments/assets/dce388d6-618f-4931-8ee7-a48df44619f0)
##Classification of Control Systems
Based on different parameters, we can classify the control systems into the following ways. 
###Continuous time and Discrete-time Control Systems 
- Control Systems can be classified as continuous time control systems and discrete 
time control systems based on the type of the signal used. 
- In continuous time control systems, all the signals are continuous in time. But, 
in discrete time control systems, there exists one or more discrete time signals.
###SISO and MIMO Control Systems 
- Control Systems can be classified as SISO control systems and MIMO control systems 
based on the number of inputs and outputs present. 
- SISO (Single Input and Single Output) control systems have one input and one output. 
Whereas, MIMO (Multiple Inputs and Multiple Outputs) control systems have more 
than one input and more than one output.
###Open Loop and Closed Loop Control Systems
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
 The error detector produces an error signal, which is the difference between the input and 
the feedback signal. This feedback signal is obtained from the block (feedback elements) by 
considering the output of the overall system as an input to this block. Instead of the direct 
input, the error signal is applied as an input to a controller. 
So, the controller produces an actuating signal which controls the plant. In this combination, 
the output of the control system is adjusted automatically till we get the desired response. 
Hence, the closed loop control systems are also called the automatic control systems. Traffic 
lights control system having sensor at the input is an example of a closed loop control system. 
The differences between the open loop and the closed loop control systems are
 mentioned in the following table:

 ![image](https://github.com/user-attachments/assets/bc776372-9738-46c3-81f5-668fda9dbf2d)
 ##Types of Feedback
  There are two types of feedback:
- Positive feedback
- Negative feedback
### Positive Feedback
The positive feedback adds the reference input, R(s)R(s) and feedback output. The following 
figure shows the block diagram of positive feedback control system 

![image](https://github.com/user-attachments/assets/981b9bd7-5f69-4867-8e7b-36e7396296a9)
The concept of transfer function will be discussed in later chapters. For the time being,
 consider the transfer function of positive feedback control system is,

 ![image](https://github.com/user-attachments/assets/6ba1fdaf-fade-4f0d-989d-8baecba9af85)
Where, 
- T is the transfer function or overall gain of positive feedback control system.
- G is the open loop gain, which is function of frequency. 
- H is the gain of feedback path, which is function of frequency.
###Negative Feedback 
Negative feedback reduces the error between the reference input, R(s)R(s) and system 
output. The following figure shows the block diagram of the negative feedback control 
system.

![image](https://github.com/user-attachments/assets/5b1fda0d-87fa-4863-8623-6ffa1c4b74a6)
Transfer function of negative feedback control system is,

![image](https://github.com/user-attachments/assets/b10dfc17-1bab-4bca-afcd-cf54d1aad9c3)
Where, 
- T is the transfer function or overall gain of negative feedback control system. 
- G is the open loop gain, which is function of frequency. 
- H is the gain of feedback path, which is function of frequency.
##Representataion of Transfer Function
###Block Diagrams
Block diagrams consist of a single block or a combination of blocks. These are used to 
represent the control systems in pictorial form.
###Basic Elements of Block Diagram 
The basic elements of a block diagram are a block, the summing point and the take-off point. 
Let us consider the block diagram of a closed loop control system as shown in the following 
figure to identify these elements.

![image](https://github.com/user-attachments/assets/5506b128-d3cd-4f41-b616-6159fd452413)
The above block diagram consists of two blocks having transfer functions G(s) and H(s). It is 
also having one summing point and one take-off point. Arrows indicate the direction of the 
flow of signals. Let us now discuss these elements one by one. 
###Block
The transfer function of a component is represented by a block. Block has single input and 
single output. 
The following figure shows a block having input X(s), output Y(s) and the transfer function 
G(s).

![image](https://github.com/user-attachments/assets/1d122e28-5461-489f-9c68-86cc7abbdb82)
###Summing Point 
The summing point is represented with a circle having cross (X) inside it. It has two or more 
inputs and single output. It produces the algebraic sum of the inputs. It also performs the 
summation or subtraction or combination of summation and subtraction of the inputs based 
on the polarity of the inputs. Let us see these three operations one by one. 
The following figure shows the summing point with two inputs (A, B) and one output (Y). 
Here, the inputs A and B have a positive sign. So, the summing point produces the output, Y 
as sum of A and B i.e. = A + B.

![image](https://github.com/user-attachments/assets/403b49fb-e5d4-4aa5-b6a4-0eadffbdc651)
The following figure shows the summing point with two inputs (A, B) and one output (Y). 
Here, the inputs A and B are having opposite signs, i.e., A is having positive sign and B is 
having negative sign. So, the summing point produces the output Y as the difference of A 
and B i.e 
Y = A + (-B) = A - B. 

![image](https://github.com/user-attachments/assets/dd923b3f-31cb-42d3-8c1d-b918cc909f5c)
The following figure shows the summing point with three inputs (A, B, C) and one output (Y). 
Here, the inputs A and B are having positive signs and C is having a negative sign. So, the 
summing point produces the output Y as 
Y = A + B + (−C) = A + B − C.

![image](https://github.com/user-attachments/assets/44d9458e-a2b2-42c3-9296-853a821b15c7)
###Take-off Point 
The take-off point is a point from which the same input signal can be passed through more 
than one branch. That means with the help of take-off point, we can apply the same input 
to one or more blocks, summing points.In the following figure, the take-off point is used to 
connect the same input, R(s) to two more blocks. 

![image](https://github.com/user-attachments/assets/5920247b-163d-4473-b067-4bb8a8a5d37e)
##Basic Connections for Blocks 
 There are three basic types of connections between two blocks.
###Series Connection
Series connection is also called cascade connection. In the following figure, two
 blocks having transfer functions G1(s)G1(s) and G2(s)G2(s) are connected in series.

 ![image](https://github.com/user-attachments/assets/44323b8d-38da-43aa-af22-802b2fa384d9)
That means we can represent the series connection of two blocks with a single block. The 
transfer function of this single block is the product of the transfer functions of those two 
blocks. The equivalent block diagram is shown below.

![image](https://github.com/user-attachments/assets/24ff7fef-66df-4892-b3f1-6c3f4851bfc2)
Similarly, you can represent series connection of ‘n’ blocks with a single block. The transfer 
function of this single block is the product of the transfer functions of all those ‘n’ blocks.
###Parallel Connection 
The blocks which are connected in parallel will have the same input. In the following figure, 
two blocks having transfer functions G1(s)G1(s) and G2(s)G2(s) are connected in parallel. 
The outputs of these two blocks are connected to the summing point. 

![image](https://github.com/user-attachments/assets/d5e05ed5-1517-4eae-a32d-1364cbee608e)
That means we can represent the parallel connection of two blocks with a single block. The 
transfer function of this single block is the sum of the transfer functions of those two blocks. 
The equivalent block diagram is shown below. 

![image](https://github.com/user-attachments/assets/c5d1e098-0e5b-40d3-8ab7-494db95ca7cd)
Similarly, you can represent parallel connection of ‘n’ blocks with a single block. The transfer 
function of this single block is the algebraic sum of the transfer functions of all those ‘n’ 
blocks.
###Feedback Connection 
As we discussed in previous chapters, there are two types of feedback — positive feedback 
and negative feedback. The following figure shows negative feedback control system. Here, 
two blocks having transfer functions G(s)G(s) and H(s)H(s) form a closed loop. 

![image](https://github.com/user-attachments/assets/d05da72a-06b2-4560-b0a0-387807d2a854)
This means we can represent the negative feedback connection of two blocks with a single 
block. The transfer function of this single block is the closed loop transfer function of the 
negative feedback. The equivalent block diagram is shown below.

![image](https://github.com/user-attachments/assets/27d7d2b5-2270-4725-a9f9-8216078b86ea)
Similarly, you can represent the positive feedback connection of two blocks with a single 
block. The transfer function of this single block is the closed loop transfer function of the 
positive feedback, i.e.,

![image](https://github.com/user-attachments/assets/8b815280-dcca-490f-8c0a-013a7321a6bd)
###Block Diagram Reduction Rules 
Follow these rules for simplifying (reducing) the block diagram, which is having many blocks, 
summing points and take-off points. 
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
The block diagram reduction process takes more time for complicated systems because; we 
have to draw the (partially simplified) block diagram after each step. So, to overcome this 
drawback, use signal flow graphs (representation).
###Signal Flow Graph
Signal flow graph is a graphical representation of algebraic equations. In this chapter, let us 
discuss the basic concepts related signal flow graph and also learn how to draw signal flow 
graphs.
###Basic Elements of Signal Flow Grap
Nodes and branches are the basic elements of signal flow graph. 
Node
 Node is a point which represents either a variable or a signal. There are three types of
 nodes — input node, output node and mixed node.
- Input Node − It is a node, which has only outgoing branches. 
- Output Node − It is a node, which has only incoming branches. 
- Mixed Node − It is a node, which has both incoming and outgoing branches.
Example 
Let us consider the following signal flow graph to identify these nodes.

![image](https://github.com/user-attachments/assets/3be556da-49f7-4fb2-a7f7-9b24d1d47bc8)
Branch 
Branch is a line segment which joins two nodes. It has both gain and direction. For example, 
there are four branches in the above signal flow graph. These branches have gains of a, b, 
c and -d.
##Construction of Signal Flow Graph 
Let us construct a signal flow graph by considering the following algebraic equations −

![image](https://github.com/user-attachments/assets/af23e3ea-96fc-4fe5-bcf5-919fe06cbb04)

![image](https://github.com/user-attachments/assets/52d87824-5892-48ae-9fbd-63ef207b7b91)


 ![image](https://github.com/user-attachments/assets/c35d8395-18c4-4994-9e5f-a0ab172f6daf)
###Conversion of Block Diagrams into Signal Flow Graphs 
Follow these steps for converting a block diagram into its equivalent signal flow graph. 
- Represent all the signals, variables, summing points and take-off points of block 
diagram as nodes in signal flow graph.
- Represent the blocks of block diagram as branches in signal flow graph.
- Represent the transfer functions inside the blocks of block diagram as gains of the 
branches in signal flow graph. 
- Connect the nodes as per the block diagram. If there is connection between two 
nodes (but there is no block in between), then represent the gain of the branch as 
one. For example, between summing points, between summing point and takeoff 
point, between input and summing point, between take-off point and output. 
Example 
Let us convert the following block diagram into its equivalent signal flow graph. 

![image](https://github.com/user-attachments/assets/036c9b3b-34a4-4251-b710-59135842b5a4)
Represent the input signal R(s) and output signal C(s) of block diagram as input 
node R(s) and output node C(s) of signal flow graph. 
Just for reference, the remaining nodes (y1 to y9) are labeled in the block diagram. There are 
nine nodes other than input and output nodes. That is four nodes for four summing points, 
four nodes for four take-off points and one node for the variable between blocks G1and G2. 

The following figure shows the equivalent signal flow graph. 

![image](https://github.com/user-attachments/assets/90f9e464-9f9a-44ab-bf70-48d3d0041509)
Let us now discuss the Mason’s Gain Formula. Suppose there are ‘N’ forward paths in a signal 
flow graph. The gain between the input and the output nodes of a signal flow graph is nothing but the transfer function of the system. It can be calculated by using Mason’s gain 
formula. 
###Mason’s gain formula:

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
###Calculation of Transfer Function using Mason’s Gain Formula
Let us consider the same signal flow graph for finding transfer function. 

![image](https://github.com/user-attachments/assets/bc7d6cfa-8442-4463-8feb-49c623542a6d)

![image](https://github.com/user-attachments/assets/981899da-4c68-4544-8ee0-a2fa2c88df1a)

![image](https://github.com/user-attachments/assets/afa0c35c-141b-464c-bc96-8e0bcdc32d3e)
###Calculating steady-state errors
Before talking about the relationships between steady-state error and system type, we will show how to calculate error regardless of system type or input. Then, we will start deriving formulas we can apply when the system has a specific structure and the input is one of our standard functions. Steady state error can be calculated from the open- or closed-loop transfer function for unity feedback systems. For example, let's say that we have the system given below. 
![image](https://github.com/user-attachments/assets/fb5836f8-f42f-4954-b357-e929fb37abfc)
This is equivalent to the following system, where T(s) is the closed-loop transfer function.
![image](https://github.com/user-attachments/assets/9287cf18-e974-4c84-ba4c-c7d81dccf2d5)
We can calculate the steady-state error for this system from either the open- or closed-loop transfer 
function using the Final Value Theorem. Recall that this theorem can only be applied if the 
subject of the limit (sE(s) in this case) has poles with negative real part.
![image](https://github.com/user-attachments/assets/aab4be95-1552-4ab1-b2b9-7668386e173d)
###Types of controllers:
- Proportional Control 
With proportional control, the actuator applies a corrective force that is proportional o the amount  of error: 
Outputp = Kp × E
Outputp = system output due to proportional control
 Kp = proportional constant for the system called gain.














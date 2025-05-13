## Number System:
A number system is defined as a system of writing to express numbers. A number system is a 
mathematical system with base n, where n represents total numbers present in that system. 

Eg: In decimal number system, the number of digits is 10
## Radix Point:
Radix point is a base point used to separate the integer part and the fractional part of a number. 
## Base or radix:
The number of symbols used in a number system is called base or radix of the number system. 

Eg: In decimal number system – Base is 10

In Binary number system – Base is 2

In Hexadecimal number system – Base is 16 etc.
## Most significant bit (MSB):  
The left most bit of a binary number which has the highest place value is called most significant bit. 
## Least significant bit (LSB):  
The right most bit of a binary number which has the least place value is called least significant bit. 
## Bit:
 A binary digit is called a bit.
 
Example: 0 or 1
## Nibble:
A group of four bits is called a Nibble.

Example: 0110, 1110 etc. 
## Byte:  
A group of eight bits is called a byte. 

Example: 01101101, 11010011 etc.
## Types of number systems 
1.Binary number system 

2.Octal number system 

3.Decimal number system

4.Hexadecimal number system
## Binary number system:  
The base of binary number system is 2. The digits used are 0 and 1. 

Example: 11001(2), 0101(2)
## Octal number system:  
The base of octal number system is 8.

The digits used are 0, 1, 2, 3, 4, 5, 6 and 7. 

Example: 157(8), 2312(8), 110(8) 
## Table representing decimal, Octal  and binary number:
![image](https://github.com/user-attachments/assets/f7178afd-2bcb-40d7-9806-f585fe21e55c)
## Decimal number system:  
The base of decimal number system is 10.  

The digits used are 0, 1, 2, 3, 4, 5, 6, 7, 8 and 9. 

Example: 0157(10), 6587(10), 0110(10)
## Hexadecimal number system:  
The base of hexadecimal number system is 16. 

The digits used are 0, 1, 2, 3, 4, 5, 6, 7, 8 9, A, B, C, D, E and F.

Example: 0157(16), 2312(16), 0110(16), ABC5(16), BDEF(16)
## Table representing decimal, hexadecimal and binary number:
![image](https://github.com/user-attachments/assets/b134d606-d551-4f10-b894-959ccb006f07)
## Binary Arithmetic:
Binary arithmetic includes the basic arithmetic operations of addition, subtraction, multiplication 
and division.
## Binary Addition:
The rules to perform binary addition are

0 + 0 = 0 

 0 + 1 = 1 
 
 1 + 0 = 1 
 
 1 + 1 = 0 with a carry 1
## Binary Subtraction: 
The rules to perform binary subtraction are 

 0 – 0 = 0 
 
 0 – 1 = 1 with a borrow 1 
 
 1 – 0 = 1 
 
 1 – 1 = 0
 ## Binary Multiplication:
 The rules to perform binary multiplication are 
 
 0 X 0 = 0 
 
 0 X 1 = 0 
 
 1 X 0 = 0 
 
 1 X 1 = 1
## Binary Division: 
 The rules to perform binary division are 
 
 0 ÷ 0 = not defined 
 
 0 ÷ 1 = 0 
 
 1 ÷ 0 = not defined 
 
 1 ÷ 1 = 1
 ## 1’s Complement of binary numbers:  
The 1’s complement of a binary number is obtained by changing each 0 to 1 and 1 to 0. 

Eg: The 1’s complement of  (101101)2 is (010010)2 
## 2’S Complement of binary numbers:
 The 2’S complement of a binary number is obtained by adding 
1 to the 1’s complement of the number. 

Eg: The 2’s complement of  (101101)2 is (010010)2 + 1 = (010011)2

# Binary Codes
## Digital Codes or Binary Codes: 
 A group of binary digits is known as a binary code or a digital code. 
## Numeric Code:  
Digital code represented by the number is known as a numeric code. 
## Classification: 
The codes are broadly classified into  

1. Weighted code 
2. Non-weighted code 
3. Reflective code 
4. Sequential code 
5. Error detecting and correcting codes
![image](https://github.com/user-attachments/assets/56e7e011-321d-4212-b7d0-426e3d280089)

## Weighted codes: 
The weighted codes are those where  the position of each number represent a specific weight. In these 
codes each decimal digit is represented by a group of four bits. 

In weighted codes, each digit is assigned a specific weight according to its position. For example, in 
8421/BCD code, 1001 the weights of 1, 1, 0, 1 (from left to right) are 8, 4, 2 and 1 respectively.

Examples:8421, 2421. 
![image](https://github.com/user-attachments/assets/3e4358f4-d0a3-4c8f-ba43-3778d9f2b2f9)
## Non-weighted codes: 
The non-weighted codes are not positionally weighted. In other words,  codes that are not assigned 
with any weight to each digit position.

Example: Excess-3(XS-3) and Gray Codes.
## Excess-3 code:
Excess-3 codes are Non-weighted and can be obtained by adding 3 to each decimal digit then it can be 
represented by using 4 bit binary number for each digit. An Excess-3 equivalent of a given binary 
number is obtained using the following steps: 

1. Find the decimal equivalent of the given binary number.
   
2. Add +3 to each digit of decimal number. 

3. Convert the newly obtained decimal number back to binary number to get required excess-3 
equivalent. 

4. These are following excess-3 codes for decimal digits.
![image](https://github.com/user-attachments/assets/494639ae-c6bb-4ddb-842a-2b776cb9656d)
## Gray code: 
Gray code is non weighted code, which means there is no specific weight assigned to the bit position. 
## Applications: 
1. It is used in analog to digital conversion, input / output devices.
  
2. It is used to reduce errors that occur in data transmission.
## Binary to gray code conversion:
1. The MSB of the gray code is the MSB of the binary number.
   
2. Perform XOR operation between the MSB and the second significant bit of the binary number.
  
3. XOR the second and third significant bits of the binary, the result is the third significant bit of 
the gray code.

4. Repeat the process till the end of the LSB of the binary number 
![image](https://github.com/user-attachments/assets/6f37b7ec-acbf-48f8-9727-50637d358f74)

![image](https://github.com/user-attachments/assets/6731cc08-65c3-407e-858c-1e6882120696)

## Gray code to binary conversion:
1. The MSB of the binary is same as the MSB of gray code.

2. Perform the XOR operation between the MSB of the binary and the second significant bit of 
gray code the result is the second significant bit of binary.

3. Perform the XOR operation between the second significant bit of binary and the third 
significant bit of gray code the result is the third significant bit of binary. 

4. Repeat the process until all the gray code bits are XOR.
![image](https://github.com/user-attachments/assets/296658ba-3da3-4957-a683-6aee882ba8e7)

## Decimal to Binary conversion:
Example: Convert the decimal number 13(10) to binary.

Solution: We will start dividing the given number (13) repeatedly by 2 until we get the quotient as 0. We will note the remainders in order.

![image](https://github.com/user-attachments/assets/d5b177cf-ede1-4581-84fc-27eac7634d7f)

## Binary to Decimal Conversion:
Example: Convert the binary number 1011012 to a decimal number.

Solution: Observe the following steps to understand the binary to decimal conversion. In any binary number, the rightmost digit is called the 'Least Significant Bit' (LSB) and the left-most digit is called the 'Most Significant Bit' (MSB). For a binary number with 'n' digits, the least significant bit has a weight of 20 and the most significant bit has a weight of 2^n - 1.

![image](https://github.com/user-attachments/assets/5a40d2d0-ff27-4e83-896d-147160148d47)

![image](https://github.com/user-attachments/assets/6b04d3f4-5aa3-4040-8b6e-8c5630be325f)

![image](https://github.com/user-attachments/assets/1cccd58d-3e5e-4b39-af1a-61b27886732b)

![image](https://github.com/user-attachments/assets/23f54410-548c-4f3e-8696-d516ee10f8c6)

## Reflective codes: 
A code is said to be reflective when the code for 9 is the complement  for the code 0, 8 for 1, 7 for 2, 6 
for 3 and 5 for 4.  

Eg:  2421 code and Excess-3 code 
![image](https://github.com/user-attachments/assets/f4c569e2-396c-418e-a527-aa68064cac4e)

## Sequential codes: 
A code is said to be sequential when each succeeding code is binary number greater than its preceding 
code. 

Eg:  8421 code and Excess-3 code 
## Parity codes:  
The parity code is used for the purpose of detecting errors during the transmission of binary 
information. The parity code is a bit that is included with the binary data to be transmitted. 

The inclusion of a parity bit will make the number of 1’s either odd or even. Based on the number of 
1’s in the transmitted data, the parity code is of two types.

1. Even parity code 
2. Odd parity code

## Even parity code: 
If the total number of 1 bits in the word including parity bit is Even, then such a parity code is said to 
be Even parity code. 
## Odd parity code: 
If the total number of 1 bits in the word including parity bit is odd, then such a parity code is said to be 
odd parity code.

The following table shows the even and odd parity bits for 4 bit data word  

![image](https://github.com/user-attachments/assets/ea82caa4-75dc-43dc-8bc8-d0ae0090a1fd)

# Logic Gates

 Logic gate is an electronic circuit that performs a Boolean logical operation. A logic gate 
has one or more inputs but only one output.  
 
1. The basic gates are AND gate, OR gate and NOT gate. 

2. The universal gates are NAND gate and NOR gate. 

3. The special gates are XOR and XNOR.

## OR gate:
OR gate is a basic gate which has two or more input but only one output. The output is high if 
any one of the input is high.

![image](https://github.com/user-attachments/assets/bc0762cb-8c09-43dd-abb6-2ec68a992617)

## AND gate: 
AND gate is a basic gate which has two or more input but only one output. The output is high if 
all the inputs are high.

![image](https://github.com/user-attachments/assets/136b5c5f-12c5-46e9-9c40-40308fa1f6b6)

## NOT gate: 
 It is a basic gate which complements the input signal value. It is also called as an inverter. It is a 
logic gate with only one input and one output.

![image](https://github.com/user-attachments/assets/b4cd4b80-7ba6-4a29-b89c-474b106e0f0e)

## NAND gate: 
NAND gate is a universal gate which performs complement of AND logic. NAND gate has two or 
more input but only one output. The output is high only when any of the input is low. 

![image](https://github.com/user-attachments/assets/e6e6fee1-6524-4051-9217-898fe89ac2a8)

## NOR gate:  
NOR gate is a universal gate which performs complement of OR logic. NOR gate has two or 
more input but only one output. The output is high if and only if all the inputs are low. 

![image](https://github.com/user-attachments/assets/6a47f2b6-bd4b-4733-881d-3306e8511877)

## Exclusive OR (XOR) gate: 
XOR gate is a special gate which has two or more input but only one output. The output is high 
only when odd numbers of input are high. 

XOR gate is also called as Inequality detector.

![image](https://github.com/user-attachments/assets/dca97288-69ff-4a8c-bc22-639399588851)

## Realization of NOT, AND, OR and XOR gates using NAND gate. 

![image](https://github.com/user-attachments/assets/389fb254-748d-42e2-8946-09c0b1217cdd)

## Realization of NOT, AND, OR and XNOR gates using NOR gate. 

![image](https://github.com/user-attachments/assets/c5cfbfd8-df35-4c10-9373-b4516e16fa42)

![image](https://github.com/user-attachments/assets/a9411b13-1364-4991-822f-175dc57e3bac)

## Simplification of Boolean expressions:
## Product term: 
 The logical product of Boolean variables, complemented or uncomplemented form is a 
product term.

![image](https://github.com/user-attachments/assets/220be4a6-4434-4aff-836b-9f46ad56020d)

## Sum term: 
 The logical sum of Boolean variables, complemented or uncomplemented form is a sum 
term. 

![image](https://github.com/user-attachments/assets/2dbf7480-a2b4-4e51-b1ec-a35b462b3f9a)

## Sum of products (SOP):
 The logical sum of two or more logical product terms is known as sum of 
products. 

![image](https://github.com/user-attachments/assets/d2d3f748-9138-486d-ae22-86ea3c1d5e07)

## Product of sum (POS): 
 The logical product of two or more logical sum terms is known as product of 
sum. 

![image](https://github.com/user-attachments/assets/531286f9-280f-4bbe-9619-c30e287fa784)

## Sum of Product (SOP) form:
The Boolean Expressions in which the product of input variables are summed together for output 
high. 

Example: Consider a truth table

![image](https://github.com/user-attachments/assets/cc889676-0f15-4775-b093-fc124375d2e1)

![image](https://github.com/user-attachments/assets/62cff016-c826-43cc-b16e-e8749cb14aa7)

![image](https://github.com/user-attachments/assets/7fdd4216-9d55-4b7d-9f20-f0b74f7bb528)

NOTE:  
1. Canonical SOP form to minimal SOP form and vice versa can also be derived using truth table.
   
2. Each product terms of SOP form is called minterms.
 
3. Canonical SOP form of Boolean expressions can also be written using decimal equivalent of 
input variables for the output high.

Example: for the Boolean expression (1), the output is high for ABC=001, ABC=010 ABC=100, 
ABC=101 and ABC=111. 

The decimal equivalent of ABC=001 is '1', ABC=010 is '2', ABC=100 is '4', ABC=101 is '5' and 
ABC=111 is '7' 

Therefore, Y can also be expressed as 

![image](https://github.com/user-attachments/assets/0ed70937-5cd3-4ea8-8459-5c63a0f21e14)

## Product of Sum (POS) form:
The Boolean Expressions in which the Sum of input variables are multiplied together for output 
low. 

Example: Consider a truth table

![image](https://github.com/user-attachments/assets/f131cb20-b3c2-4e0a-963d-9e2304fd8648)

![image](https://github.com/user-attachments/assets/3c952dd6-3aac-4d1d-9225-0e0db313f4d8)

NOTE: 

1. Canonical POS form to minimal POS form and vice versa can also be derived using truth table.
   
2. Each Sum terms of POS form is called maxterm.
   
3. Canonical POS form of Boolean expressions can also be written using decimal equivalent of 
input variables for the output high.

Example: for the Boolean expression (1), the output is low for ABC=000, ABC=011 and 
ABC=110. 

The decimal equivalent of ABC=000 is '0', ABC=011 is '3', and ABC=110 is '6' 

Therefore, Y can also be expressed as 

![image](https://github.com/user-attachments/assets/706c15d2-2b68-4d91-9305-8c1944fed20a)

# K-Map simplification (Karnaugh Map simplification) 
The simplification of Boolean expressions using Boolean algebraic rules is not unique and 
most of the cases, the resultant expression is not in minimal form. In order to get the uniqueness 
and final minimal form, K-map technique will be used.

**NOTE:** 
Number of cells in K-map = number of possible cases 
No. of possible cases=2^n
N is the number of input variables.

Example: Number of input variables=2, then the number of cells in K-map is 4. 

**NOTE:** K-maps can take wither POS form or SOP form, in SOP form 1's are need to be grouped
**NOTE:** Only adjacent cells will be considered for grouping, diagonal cells should not be grouped. 
**NOTE:** grouping can be done using 2 variables, 4 variables, 8 variables, 16 variables etc.., highest 
priority for grouping maximum variables in the above denomination. Variables are 0's for POS 
form and 1's for SOP form.

**Procedure:** 
1. Select the number of cells according to the number of input variables.
2. Identify whether the given problem is SOP or POS form, minterms for SOP form and 
maxterms for POS form.
**NOTE:** In SOP form, fill the cells by 1's at corresponding minterms and otherwise 
fill with 0's. 
**NOTE:** In POS form, fill the cells by 0's at corresponding maxterms and otherwise 
fill with 1's.
**NOTE:** In POS form, take the complement of the output variable to get the 
resultant expression. 
3. Group the terms in the form of rectangular, the total number of terms is 2, 4, 8, etc.., try to 
cover as many elements as you can in one group.
4. from the groups, find the Product terms for SOP from and sum terms for POS form.
     
**Example:**
Simplify the following canonical SOP form of Boolean expression using K-map technique.

![image](https://github.com/user-attachments/assets/231d1e93-1e81-4df7-adeb-d5a664f0c9ac)

# Combinational Circuits:

The digital system consists of two types of circuits, namely 

(i) Combinational circuits 

(ii) Sequential circuits 

**Combinational circuit** consists of logic gates whose output at any time is 
determined from the present combination of inputs. The logic gate is the most basic 
building block of combinational logic. The logical function performed by a 
combinational circuit is fully defined by a set of Boolean expressions. 

**Sequential logic circuit** comprises both logic gates and the state of storage 
elements such as flip-flops. As a consequence, the output of a sequential circuit depends 
not only on present value of inputs but also on the past state of inputs. 
In the previous chapter, we have discussed binary numbers, codes, Boolean 
algebra and simplification of Boolean function and logic gates.

A combinational circuit consists of input variables, logic gates, and output 
variables. The logic gates accept signals from inputs and output signals are generated 
according to the logic circuits employed in it. Binary information from the given data 
transforms to desired output data in this process. Both input and output are obviously 
the binary signals, i.e., both the input and output signals are of two possible states, logic 
1 and logic 0.

![image](https://github.com/user-attachments/assets/9fb15df1-4767-4f7e-a3d1-297550ad0c05)

For n number of input variables to a combinational circuit, 2n possible 
combinations of binary input states are possible. For each possible combination, there is 
one and only one possible output combination. A combinational logic circuit can be 
described by m Boolean functions and each output can be expressed in terms of n input 
variables.

## Half-Adder: 
A half-adder is a combinational circuit that can be used to add two binary bits. It 
has two inputs that represent the two bits to be added and two outputs, with one 
producing the SUM output and the other producing the CARRY.

![image](https://github.com/user-attachments/assets/9e5b81d8-0493-40b8-9744-e69269030ea4)

## Full-Adder: 
A full adder is a combinational circuit that forms the arithmetic sum of three 
input bits. It consists of 3 inputs and 2 outputs. 
Two of the input variables, represent the significant bits to be added. The third 
input represents the carry from previous lower significant position. The block diagram 
of full adder is given by,

![image](https://github.com/user-attachments/assets/ab79d4f9-3739-4d1d-8d54-191f2b148e76)

![image](https://github.com/user-attachments/assets/4eda487c-a631-4a92-b758-67bdca085253)

![image](https://github.com/user-attachments/assets/73f3083c-1cb2-428e-b791-0804ead0c6d5)

## Half Subtractor:
Half Subtractor is used for subtracting one single bit binary digit from another single bit 
binary digit.The truth table of Half Subtractor is shown below.

![image](https://github.com/user-attachments/assets/ae49509a-1e59-4034-84ed-c3c979007d3f)

## Full Subtractor:
A logic Circuit Which is used for Subtracting Three Single bit Binary digit is 
known as Full Subtractor.The inputs are A,B, Bin and the outputs are D and Bout. 

![image](https://github.com/user-attachments/assets/f65292e5-b6ca-4cf4-a94f-9b1aa867cb60)

## Four bit Parallel binary Adder:
In practical situations it is required to add two data each containing more than 
one bit. Two binary numbers each of n bits can be added by means of a full adder 
circuit. Consider the example that two 4-bit binary numbers B 4B 3B 2B 1 and A 4A 3A 2A 
1are to be added with a carry input C 1. This can be done by cascading four full adder 
circuits. The least significant bits A 1, B 1, and C 1 are added to the produce sum output 
S1 and carry output C 2. Carry output C 2 is then added to the next significant bits A2 and 
B2 producing sum output S 2 and carry output C 3. C 3 is then added to A3 and B3 and so 
on. Thus finally producing the four-bit sum output S 4S 3S 2S 1 and final carry output 
Cout.

![image](https://github.com/user-attachments/assets/f488b478-c560-4a4e-85d8-f891298445ed)

## Parallel binary Adder – Subtractor:
The addition and subtraction operations can be perform using a common adder 
circuit, where a EX-OR gate is connected in the second input along with the mode 
selection bit M. if M=0 the circuit act as a adder, M=1 then substractor. If M=0 then 
output of the EX-OR gate is B act as adder, if M=1 then B’ act as a subtractor.

![image](https://github.com/user-attachments/assets/9f1fdb28-52cb-46a1-8049-49c129b92e34)

## Carry look ahead Adder:
In the parallel adder the carry input of each stage is depends on the carry output 
of the previous stage. This processes leads to time delay in addition.This delay is called 
propagation delay. The process can be speeding up by eliminating the inter stage carry 
delay called look ahead carry addition. In uses two functions carry generate and carry 
propagate.

![image](https://github.com/user-attachments/assets/704c4a4f-4e1f-4bdf-a810-f4f8dc080f9a)

![image](https://github.com/user-attachments/assets/e679bfb7-8b81-4ed1-b1e4-d1e7bef54cfd)

# Decoder
Decoder is a combinational circuit. 
It has N inputs and 2^N outputs. 

![image](https://github.com/user-attachments/assets/46791da2-2f69-457c-a5fa-a118c6f6a82c)


## 2 to 4 Decoder:
A binary decoder has ‗n‘ bit binary input and a one activated output out of 2n 
outputs. A binary decoder is used when it is necessary to activate exactly one of 2n 
outputs based on an n-bit input value.

![image](https://github.com/user-attachments/assets/1a1d09ef-b22c-4747-b710-a95beee056a5)

![image](https://github.com/user-attachments/assets/a58dbaaf-b73e-4abc-b928-95f2ec79b3c7)

## 3- to-8 Line Decoder: 
A 3-to-8 line decoder has three inputs (A, B, C) and eight outputs (Y0- Y7). Based 
on the 3 inputs one of the eight outputs is selected. 
The three inputs are decoded into eight outputs, each output representing one of 
the minterms of the 3-input variables. This decoder is used for binary-to-octal 
conversion. The input variables may represent a binary number and the outputs will 
represent the eight digits in the octal number system. The output variables are mutually 
exclusive because only one output can be equal to 1 at any one time. The output line 
whose value is equal to 1 represents the minterm equivalent of the binary number 
presently available in the input lines. 

![image](https://github.com/user-attachments/assets/15f533fd-389c-4083-85ad-26bb0ba6521c)

![image](https://github.com/user-attachments/assets/5651c6ad-b1bc-44b3-a1e8-d8b270863cfb)

## Applications of decoders:
1. Decoders are used in counter system. 
2. They are used in analog to digital converter. 
3. Decoder outputs can be used to drive a display system.

# Encoder
 An encoder is a digital circuit that performs the inverse operation of a decoder. 
Hence, the opposite of the decoding process is called encoding. An encoder is a 
combinational circuit that converts binary information from 2n input lines to a 
maximum of ‗n‘ unique output lines. 
The general structure of encoder circuit is 

![image](https://github.com/user-attachments/assets/42f19015-06a7-460e-adcc-88ab2165fa64)

## 4 to 2 Encoder:

![image](https://github.com/user-attachments/assets/cad38936-4a90-498b-96c3-d35ee064aeb9)

![image](https://github.com/user-attachments/assets/9158e441-8df2-4301-a840-d764bea92b24)

## Priority Encoder: 
A priority encoder is an encoder circuit that includes the priority function. In 
priority encoder, if two or more inputs are equal to 1 at the same time, the input having 
the highest priority will take precedence. 

In addition to the two outputs x and y, the circuit has a third output, V (valid bit 
indicator). It is set to 1 when one or more inputs are equal to 1. If all inputs are 0, there 
is no valid input and V is equal to 0.

The higher the subscript number, higher the priority of the input. Input D3, has 
the highest priority. So, regardless of the values of the other inputs, when D3 is 1, the 
output for xy is 11. 

D2 has the next priority level. The output is 10, if D2= 1 provided D3= 0. The 
output for D1 is generated only if higher priority inputs are 0, and so on down the 
priority levels.

![image](https://github.com/user-attachments/assets/e60b7bae-1c60-447d-a3d7-1d33153048f5)

![image](https://github.com/user-attachments/assets/578c4422-c1b1-48ca-8523-14a172cd4c30)

![image](https://github.com/user-attachments/assets/89324bc9-65b1-4a8a-adf9-43406da8cdd6)

# MULTIPLEXER: (Data Selector) 
A multiplexer or MUX, is a combinational circuit with more than one input line, 
one output line and more than one selection line. A multiplexer selects binary 
information present from one of many input lines, depending upon the logic status of 
the selection inputs, and routes it to the output line. Normally, there are 2n input lines 
and n selection lines whose bit combinations determine which input is selected. The 
multiplexer is often labeled as MUX in block diagrams. 

A multiplexer is also called a data selector, since it selects one of many inputs 
and steers the binary information to the output line.

![image](https://github.com/user-attachments/assets/a8ebd20d-5aff-412b-9231-08bd9a951a65)

## 2-to-1- line Multiplexer: 
The circuit has two data input lines, one output line and one selection line, S. 
When S= 0, the upper AND gate is enabled and I0 has a path to the output. 
When S=1, the lower AND gate is enabled and I1 has a path to the output.

![image](https://github.com/user-attachments/assets/b02f6f3f-88d2-43a4-92f4-9fe8500855cd)

![image](https://github.com/user-attachments/assets/09447bc6-4a88-4092-a1bb-fbcd82d47e6d)

## 4-to-1-line Multiplexer: 
A 4-to-1-line multiplexer has four (2n) input lines, two (n) select lines and one 
output line. It is the multiplexer consisting of four input channels and information of 
one of the channels can be selected and transmitted to an output line according to the 
select inputs combinations. Selection of one of the four input channel is possible by two 
selection inputs.

Each of the four inputs I0 through I3, is applied to one input of AND gate. 
Selection lines S1 and S0 are decoded to select a particular AND gate. The outputs of the 
AND gate are applied to a single OR gate that provides the 1-line output.

![image](https://github.com/user-attachments/assets/a0cadb4d-712d-488c-81ae-3b7de610fbd7)

## 8-to-1 Multiplexer:
8:1 multiplexer circuit having 8 input lines I0, I1, I2…………..I7 , one enable input (E) , single output line (Y) and three select line (S0, S1,S2).

![image](https://github.com/user-attachments/assets/c888c7db-3f20-4746-b519-e12d0cead3e6)

The truth table of 8:1 mux

![image](https://github.com/user-attachments/assets/ba116b85-9144-4455-a21d-6ab91f285614)

![image](https://github.com/user-attachments/assets/542e4eae-a177-43c6-a7b2-6e7ea6fc416e)

# DEMULTIPLEXER:
Demultiplex means one into many. Demultiplexing is the process of taking 
information from one input and transmitting the same over one of several outputs.

A demultiplexer is a combinational logic circuit that receives information on a 
single input and transmits the same information over one of several (2n) output lines.

![image](https://github.com/user-attachments/assets/ba04e8c6-21f1-427b-9412-0411f176dd38)

The block diagram of a demultiplexer which is opposite to a multiplexer in its 
operation is shown above. The circuit has one input signal, ‗n‘ select signals and 2n 
output signals. The select inputs determine to which output the data input will be 
connected. As the serial data is changed to parallel data, i.e., the input caused to appear 
on one of the n output lines, the demultiplexer is also called a ―data distributer‖ or a ―serial-to-parallel converter

## 1-to-4 Demultiplexer: 
A 1-to-4 demultiplexer has a single input, Din, four outputs (Y0 to Y3) and two 
select inputs (S1 and S0).

![image](https://github.com/user-attachments/assets/737e7363-7221-490f-ac68-d807da524580)

![image](https://github.com/user-attachments/assets/05160bd6-02ab-4545-997d-ca462fa0d790)

## 1-to-8 Demultiplexer: 
A 1-to-8 demultiplexer has a single input, Din, eight outputs (Y0 to Y7) and three 
select inputs (S2, S1 and S0). It distributes one input line to eight output lines based on 
the select inputs. The truth table of 1-to-8 demultiplexer is shown below. 

![image](https://github.com/user-attachments/assets/fa36fcab-3c8d-44aa-bce3-c64b32702c31)

![image](https://github.com/user-attachments/assets/2aa0c976-ddb0-4faa-85f5-a08ae6726aee)

# Sequential circuits: 
Sequential circuits are those which are time dependent (Clock cycles) and depends on 
present as well previous outputs to generate any output. Figure (2) shows the block diagram of 
sequential circuit. 

![image](https://github.com/user-attachments/assets/aa1ffaae-eee1-47cd-a768-798a31e48668)

Sequential circuits are classified into two types, 
**a. Synchronous sequential circuits** – These circuits generate the output only at discrete 
time instants. These circuits require clock pulse (Master clock generator) to sample the inputs and 
determine the system behavior. These circuits are also called clocked sequential circuits.

**b. Asynchronous sequential circuits** – These circuits generate the output instantly, once 
the input variables change. These circuits are also called unclocked sequential circuits. 

**Features of Sequential circuits:** 

1. Output depends on present as well as past data. 
2. Positive feedback is present to make dependent on past/previous output. 
3. Speed is slow. 
4. Complex design. 
5. Time dependent, hence need clock for triggering. 
6. Designed to storing the data. 
7.  Basic element is flip-flop.
   
Example: Counters, Registers etc...

**Concept of Flip-Flops **
The elementary building block of any sequential circuits is Flip-flop, the flip-flop itself is 
a simple sequential circuit. Basically sequential circuits have feedback, and it is seen that feedback 
is present in flip-flops also. 

Flip-flops have two stable conditions; each stable condition is called a state. The state 
represents the storage of binary symbols. The state of a system is also called as content or internal 
state or secondary state.

**Latches:**
 The basic difference between a latch & flipflop is, Storage elements that operate with signal levels (rather than 
signal transitions) are referred to as latches; those controlled by a clock transition are flip-flops. Latches are 
said to be level sensitive devices; flipflops are edgesensitive devices. 

## TYPES OF FLIP-FLOPS:
There are different types of flipflops depending on how their inputs and clock pulses cause transition between 
two states. We will discuss four different types of flipflops in this chapter, viz., SR, D, JK, and T. Basically 
D, JK, and T are three different modifications of the SR flipflop.

## S-R (Set-Reset) Flip-flop:
An SR flipflop has two inputs named Set (S) and Reset (R), and two outputs Q and Q'. The outputs are 
complement of each other, i.e., if one of the outputs is 0 then the other should be 1. This can be implemented 
using NAND or NOR gates. The block diagram of an SR flipflop is shown in Figure below: 

![image](https://github.com/user-attachments/assets/fa50c826-1890-4f7c-bbbf-d18f44c0810f)

## S-R Flip-flop Based on NOR Gates:

An SR flipflop can be constructed with NOR gates at ease by connecting the NOR gates back to back as 
shown in Figure below. The crosscoupled connections from the output of gate 1 to the input of gate 2 constitute 
a feedback path. This circuit is not clocked and is classified as an asynchronous sequential circuit. The truth 
table for the SR flipflop based on a NOR gate is shown in the table below

![image](https://github.com/user-attachments/assets/115bbd40-4c59-40e9-a49e-0f68fb8f2540)

![image](https://github.com/user-attachments/assets/96b9980a-ef49-4c86-bc12-45ad0ed4b887)

## CLOCKED S-R FLIP-FLOP:
Generally, synchronous circuits change their states only when clock pulses are present. The operation of the 
basic flipflop can be modified by including an additional input to control the behavior of the circuit. Such a 
circuit is shown below: 

![image](https://github.com/user-attachments/assets/8de3ae7e-9fe0-44ab-9da7-f34047c1fd00)

The circuit shown above consists of two AND gates. The clock input is connected to both of the AND gates, 
resulting in LOW outputs when the clock input is LOW. In this situation the changes in S and R inputs will not 
affect the state (Q) of the flipflop. On the other hand, if the clock input is HIGH, the changes in S and R will be 
passed over by the AND gates and they will cause changes in the output (Q) of the flipflop. This way, any 
information, either 1 or 0, can be stored in the flipflop by applying a HIGH clock input and be retained for any 
desired period of time by applying a LOW at the clock input. This type of flipflop is called a clocked S-R flip
flop. Such a clocked SR flipflop made up of two AND gates and two NOR gates is shown in Figure below: 

![image](https://github.com/user-attachments/assets/fd2cc3bc-cb49-4ee5-b2fa-bd844eba3995)

![image](https://github.com/user-attachments/assets/58d4d3a5-19e8-4c13-bafc-241c49c5f03b)

![image](https://github.com/user-attachments/assets/a5ba34f4-0571-4a12-9e9f-759c187f366b)

## Characteristic Table of an S-R Flip-flop:

![image](https://github.com/user-attachments/assets/75fb0390-d87c-49d9-a47f-9ca8b1fefb37)

![image](https://github.com/user-attachments/assets/76b97e38-1b97-4ad3-9abe-a643e816c8b3)

## CLOCKED D FLIP-FLOP:
One way to eliminate the undesirable condition of the indeterminate state in the SR latch is to ensure that inputs 
S and R are never equal to 1 at the same time. This is done in the D latch. The D flipflop has only one input 
referred to as the D (data) input & two outputs as usual Q and Q'. It transfers the data at the input after the delay 
of one clock pulse at the output Q. So in some cases the input is referred to as a delay input and the flipflop 
gets the name delay (D) flipflop. It can be easily constructed from an SR flipflop by simply incorporating an 
inverter between S and R such that the input of the inverter is at the S end & the output of the inverter is at the R 
end. We can get rid of the undefined condition, i.e., S = R = 1 condition, of the SR flipflop in the D flip flop. 
The D flipflop is either used as a delay device or as a latch to store one bit of binary information. The truth 
table of D flipflop is given in the table below. The structure of the D flipflop is shown in Figure below, which 
is being constructed using NAND gates. The same structure can be constructed using only NOR gates.

![image](https://github.com/user-attachments/assets/0cd15289-f494-4742-858f-774c2a4aa5ec)

**Case 1.** If the CLK input is low, the value of the D input has no effect, since the S and R inputs of the basic 
NAND flipflop are kept as 1. 
**Case 2.** If the CLK = 1 and D = 1, the NAND gate 1 produces 0, which forces the output of NAND gate 3 as 1. 
On the other hand, both the inputs of NAND gate 2 are 1, which gives the output of gate 2 as 0. Hence, output 
of NAND gate 4 is forced to be 1, i.e., Q = 1, whereas both the inputs of gate 5 are 1 and the output is 0, i.e.,   
Q' = 0. Hence, we find that when D = 1, after one clock pulse passes Q = 1, which means the output follows D. 
**Case 3.** If the CLK = 1, and D = 0, the NAND gate 1 produces 1. Hence both the inputs of NAND gate 3 are 1, 
which gives the output of gate 3 as 0. On the other hand, D = 0 forces the output of NAND gate 2 to be 1. 
Hence the output of NAND gate 5 is forced to be 1, i.e., Q' = 1, whereas both the inputs of gate 4 are 1 and the 
output is 0, i.e., Q = 0. Hence, we find that when D = 0, after one clock pulse passes Q = 0, which means the 
output again follows D. 

A simple way to construct a D flipflop using an SR flipflop is shown in Figure below. The logic symbol of a 
D flipflop is shown in Figure below. A D flipflop is most often used in the construction of sequential circuits 
like registers.

![image](https://github.com/user-attachments/assets/7999050b-67fc-4ab5-bfba-f2181378ca4f)

## Characteristic Table of a D Flip-flop:

![image](https://github.com/user-attachments/assets/8196303f-a759-40ae-9be3-35b215840c67)

## J-K FLIP-FLOP:
A JK flipflop has very similar characteristics to an SR flipflop. The only difference is that the undefined 
condition for an SR flipflop, i.e., Sn = Rn = 1 condition, is also included in this case. Inputs J and K behave 
like inputs S and R to set and reset the flipflop respectively. When J = K = 1, the flipflop is said to be in a 
toggle state, which means the output switches to its complementary state every time a clock passes.

The data inputs are J and K, which are ANDed with Q' and Q respectively to obtain the inputs for S and R 
respectively. A JK flipflop thus obtained is shown in Figure below. 
An SR flipflop converted into a JK flipflop:


![image](https://github.com/user-attachments/assets/9e1e1544-8eeb-4552-af83-af905e503bb4)

![image](https://github.com/user-attachments/assets/b242f17f-d1a1-4fb8-a3cc-0e593eb49329)

**Case 1.** When the clock is applied and J = 0, whatever the value of Q'n (0 or 1), the output of NAND gate 1 is 1. 
Similarly, when K = 0, whatever the value of Qn (0 or 1), the output of gate 2 is also 1. Therefore, when J = 0 
and K = 0, the inputs to the basic flipflop are S = 1 and R = 1. This condition forces the flipflop to remain in 
the same state. 

**Case 2.** When the clock is applied and J = 0 and K = 1 & the previous state of the flipflop is reset (i.e., Qn = 0 
and Q'n = 1), then S = 1 and R = 1. Since S = 1 and R = 1, the basic flipflop does not alter the state and remains 
in the reset state. But if the flipflop is in set condition (i.e., Qn = 1 & Q'n = 0), then S = 1 and R = 0. Since S = 1 
and R = 0, the basic flipflop changes its state and resets. 

**Case 3.** When the clock is applied and J = 1 and K = 0 and the previous state of the flipflop is reset (i.e., Qn = 0 
and Q'n = 1), then S = 0 and R = 1. Since S = 0 and R = 1, the basic flipflop changes its state and goes to the set 
state. But if the flipflop is already in set condition (i.e., Qn = 1 and Q'n = 0), then S = 1 and R = 1. Since S = 1 
and R = 1, the basic flipflop does not alter its state and remains in the set state. 

**Case 4.** When the clock is applied and J = 1 and K = 1 and the previous state of the flipflop is reset (i.e., Qn = 0 
and Q'n = 1), then S = 0 and R = 1. Since S = 0 and R = 1, the basic flipflop changes its state and goes to the set 
state. But if the flipflop is already in set condition (i.e., Qn = 1 and Q'n = 0), then S = 1 and R = 0. Since S = 1 
and R = 0, the basic flipflop changes its state and goes to the reset state. So we find that for J = 1 and K = 1, the 
flipflop toggles its state from set to reset and vice versa. Toggle means to switch to the opposite state. 

## Characteristic Table of a J-K Flip-flop

![image](https://github.com/user-attachments/assets/26c62aca-e775-4a46-96d8-eaddf57a7f30)

## Race-around Condition of a J-K Flip-flop:
The inherent difficulty of an SR flipflop (i.e., S = R = 1) is eliminated by using the feedback connections from 
the outputs to the inputs of gate 1 and gate 2 as discussed in JK flipflop. Truth tables JK flipflop were formed 
with the assumption that the inputs do not change during the clock pulse (CLK = 1). But the consideration is not 
true because of the feedback connections. Consider, for example, that the inputs are J = K = 1 and Q = 1, and a 
pulse as shown in Figure below is applied at the clock input.

![image](https://github.com/user-attachments/assets/4d1813da-b66d-4fbe-8c40-f54b2dd3044d)

Consider, for example, that the inputs are J = K = 1 and Q = 1, and a pulse as shown  above is  applied at the 
clock input. After a time interval ∆t equal to the propagation delay through two NAND gates  in  series,  the 
outputs will change to Q = 0. So now we have J = K = 1 and Q = 0. After another time interval of ∆t the output 
will change back to Q = 1. Hence, we conclude that for the time duration of tp of the clock pulse, the output 
will oscillate between 0 and 1. Hence, at the end of the clock pulse, the value of the output is not certain. This 
situation is referred to as a race-around condition. 
Qn+1 = JQ'n + K'Qn 
Generally, the propagation delay of TTL gates is of the order of nanoseconds. So if the clock pulse is of the 
order of microseconds, then the output will change thousands of times within the clock pulse. This racearound 
condition can be avoided if tp < ∆t < T. Due to the small propagation delay of the ICs it may be difficult to 
satisfy the above condition. A more practical way to avoid the problem is to use the masterslave (MS)

## Master-Slave J-K Flip-flop:
 A masterslave (MS) flipflop is shown in Figure below. Basically, a masterslave flipflop is a system of two 
flipflops—one being designated as master and the other is the slave. From the figure below we see that a clock 
pulse is applied to the master and the inverted form of the same clock pulse is applied to the slave. 

When CLK = 1, the first flipflop (i.e., the master) is enabled and the outputs Qm and Q'm respond to the inputs J 
and K according to the table shown in Figure 7.13. At this time the second flipflop (i.e., the slave) is disabled 
because the CLK is LOW to the second flipflop. Similarly, when CLK becomes LOW, the master becomes 
disabled and the slave becomes active, since now the CLK to it is HIGH. Therefore, the outputs Q and Q' follow 
the outputs Qm and Q'm respectively. Since the second flipflop just follows the first one, it is referred to as a 
slave and the first one is called the master. Hence, the configuration is referred to as a masterslave (MS) flip
 flop.
 
![image](https://github.com/user-attachments/assets/90b21517-15dc-485a-8e9c-762a4c7c8693)

In this type of circuit configuration the inputs to the gates 5 and 6 do not change at the time of application of the 
clock pulse. Hence the racearound condition does not exist. The state of the masterslave flipflop, shown in 
above Figure, changes at the negative transition (trailing edge) of the clock pulse. Hence, it becomes negative 
triggering a masterslave flipflop. This can be changed to a positive edge triggering flipflop by adding two 
inverters to the system—one before the clock pulse is applied to the master and an additional one in between the 
master and the slave. The logic symbol of a negative edge masterslave is shown in Figure below.   

![image](https://github.com/user-attachments/assets/b24e95d8-2da4-48a4-87c6-49800b513395)


The system of masterslave flipflops is not restricted to JK master
 slave only. There may be an SR masterslave or a D masterslave, etc., 
in all of them the slave is an SR flipflop, whereas the master changes 
to JK or SR or D flipflops.

## T Flip-flop:
 With a slight modification of a JK flipflop, we can construct a new flipflop called a T flipflop. If the two 
inputs J and K of a JK flipflop are tied together it is referred to as a T flipflop. Hence, a T flipflop has only 
one input T and two outputs Q and Q'. The name T flipflop actually indicates the fact that the flipflop has the 
ability to toggle. It has actually only two states—toggle state and memory state. Since there are only two states, 
a T flipflop is a very good option to use in counter design and in sequential circuits design where switching an 
operation is required. The truth table of a T flipflop is given below: 

![image](https://github.com/user-attachments/assets/c1acfe10-ef17-4ea8-9473-e5e15da7b54a)

If the T input is in 0 state (i.e., J = K = 0) prior to a clock pulse, the Q output will not change with the clock 
pulse. On the other hand, if the T input is in 1 state (i.e., J = K = 1) prior to a clock pulse, the Q output will 
change to Q' with the clock pulse. In other words, we may say that, if T = 1 and the device is clocked, then the 
output toggles its state. 

The truth table shows that when T = 0, then Qn+1 = Qn, i.e., the next state is the same as the present state and no 
change occurs. When T = 1, then Qn+1 = Q'n, i.e., the state of the flipflop is complemented. The circuit diagram 
of a T flipflop and the block diagram of the T flipflop is shown below:

![image](https://github.com/user-attachments/assets/60786405-2323-476e-aea3-fd2e9788aa34)

## Characteristic Table of a T Flip-flop:

![image](https://github.com/user-attachments/assets/2fd40eeb-fcf6-4c6f-962b-143f46706c06)

![image](https://github.com/user-attachments/assets/2885c9f1-7b70-4d2a-b76c-55cd25abdf11)

## EXCITATION TABLE OF A FLIP-FLOP:

![image](https://github.com/user-attachments/assets/e14941be-c9c9-4207-9c0f-0f1031017c40)

# INTERCONVERSION OF FLIP-FLOPS
 In many applications, we are being given a type of flipflop, whereas we may require some other type. In such 
cases we may have to convert the given flipflop to our required flipflop. Now we may follow a general model 
for such conversions of flipflops. The model is shown in below From the model we see that it is required to 
design the conversion logic for converting new input definitions into input codes that will cause the given flip
 flop to work like the desired flipflop. To design the conversion logic we need to combine the excitation table 
for both flipflops and make a truth table with data input(s) and Q as the inputs and the input(s) of the given 
flipflop as the output(s).

![image](https://github.com/user-attachments/assets/4c6eea82-d4ce-4312-a188-666a9d67812e)

## Conversion of an S-R Flip-flop to a D Flip-flop:

![image](https://github.com/user-attachments/assets/0b659ad9-126e-4014-9922-b05e34ee283a)

## Conversion of an S-R Flip-fl op to a J-K Flip-flop:

![image](https://github.com/user-attachments/assets/cf99b6d2-065b-4163-a25a-ca892d764394)

![image](https://github.com/user-attachments/assets/c891347a-97c1-463a-92bd-181d705beee3)

## Conversion of an S-R Flip-flop to a T Flip-flop:

![image](https://github.com/user-attachments/assets/60511e18-4f08-432a-b62c-78b0a277f29d)

![image](https://github.com/user-attachments/assets/e208ec82-2bda-4ea7-86d9-b1f0a0c26d98)

## Conversion of a D Flip-flop to an S-R Flip-flop :

![image](https://github.com/user-attachments/assets/1f33670b-e077-4ffe-9889-110aaf089f94)

# REGISTERS
 A register is a group of binary storage cells capable of holding binary information. A group of flipflops 
constitutes a register, since each flipflop can work as a binary cell. An nbit register, has n flipflops and is 
capable of holding nbits information. In addition to flipflops a register can have a combinational part that 
performs dataprocessing tasks.
Register: 
• A set of n flipflops 
• Each flipflop stores one bit 
• Two basic functions: data storage and data movement. 
**Shift Register:** A register that allows each of the flipflops to pass the stored information to its adjacent 
neighbor. 
**Counter:** A register that goes through a predetermined sequence of states.

## Shift Register 

A shift register is a storage device that used to store binary data. When a number of flip flop are connected in 
series it is called a register. A single flip flop is supposed to stay in one of the two stable states 1 or 0 or in other words the flip flop contains a number 1 or 0 depending upon the state in which it is. A register will thus contain a series of bits which can be termed as a word or a byte. 

If in these registers the connection is done in such a way that the output of one of the flip flop forms in input to 
other, it is known as a shift register. The data in a shift register is moved serially (one bit at a time). 

The shift register can be built using RS, JK or D flipflops various types of shift registers are available some of 
them are given as under. 

1. Shift Left Register 
2. Shift Right Register 
3. Shift Around Register 
4. Bidirectional Shift Register
   
There are two ways to shift data into a register (serial or parallel) and similarly two ways to shift the data out of 
the register. This leads to the construction of four basic types of registers: 

1. Serial in/Serial out (SISO)  
2. Serial in/Parallel out (SIPO)  
3. Parallel in/Serial out (PISO)  
4. Parallel in/Parallel out (PIPO)

## 1. Serial input serial output (SISO) unidirectional shift register  









# Digital Electronics
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

##

# Basic C program structure

#include "STM32L1xx.h" /* I/O port/register names/addresses for the STM32L1xx microcontrollers */

/* Global variables – accessible by all functions */

int count, bob; //global (static) variables – placed in RAM

/* Function definitions*/

int function1(char x) { //parameter x passed to the function, function returns an integer value

int i,j; //local (automatic) variables – allocated to stack or registers

-- instructions to implement the function

}
/* Main program */

void main(void) {

unsigned char sw1; //local (automatic) variable (stack or registers)

int k; //local (automatic) variable (stack or registers)

/* Initialization section */

-- instructions to initialize variables, I/O ports, devices, function registers

/* Endless loop */

while (1) { //Can also use: for(;;) {

-- instructions to be repeated

} /* repeat forever */

}

![image](https://github.com/user-attachments/assets/73fa55a5-2217-490f-a881-8a51e21da900)

## Microcontroller “header file”

Keil MDK-ARM provides a derivative-specific “header file” for each microcontroller, which defines memory addresses and symbolic labels for CPU and peripheral function register addresses. 

#include "STM32L1xx.h“ /* target uC information */

// GPIOA configuration/data register addresses are defined in STM32L1xx.h

void main(void) {

uint16_t PAval; //16-bit unsigned variable

GPIOA->MODER &= ~(0x00000003); // Set GPIOA pin PA0 as input

PAval = GPIOA->IDR; // Set PAval to 16-bits from GPIOA

for(;;) {} /* execute forever */

}

## C compiler data types

Always match data type to data characteristics!

Variable type indicates how data is represented

• #bits determines range of numeric values

• signed/unsigned determines which arithmetic/relational operators are to be used by the compiler

• non-numeric data should be “unsigned”

Header file “stdint.h” defines alternate type names for standard C data types

• Eliminates ambiguity regarding #bits

• Eliminates ambiguity regarding signed/unsigned

## C compiler data types

![image](https://github.com/user-attachments/assets/70add961-fb0b-40cb-91cb-1c474a9c0f9c)

## Data type examples

• Read bits from GPIOA (16 bits, non-numeric)

– uint16_t n; n = GPIOA->IDR; //or: unsigned short n;

• Write TIM2 prescale value (16-bit unsigned)

– uint16_t t; TIM2->PSC = t; //or: unsigned short t;

• Read 32-bit value from ADC (unsigned)

– uint32_t a; a = ADC; //or: unsigned int a;

• System control value range [-1000…+1000]

– int32_t ctrl; ctrl = (x + y)*z; //or: int ctrl;

• Loop counter for 100 program loops (unsigned)

– uint8_t cnt; //or: unsigned char cnt;

– for (cnt = 0; cnt < 20; cnt++) { 

## Constant/literal values

• **Decimal** is the default number format

int m,n; //16-bit signed numbers
m = 453; n = -25;

• **Hexadecimal:** preface value with 0x or 0X

m = 0xF312; n = -0x12E4;

• **Octal:** preface value with zero (0)

m = 0453; n = -023;
Don’t use leading zeros on “decimal” values. They will be interpreted as octal.

• **Character:** character in single quotes, or ASCII value following “slash”

m = ‘a’; //ASCII value 0x61
n = ‘\13’; //ASCII value 13 is the “return” character

• **String (array) of characters:**

unsigned char k[7];
strcpy(m,“hello\n”); //k[0]=‘h’, k[1]=‘e’, k[2]=‘l’, k[3]=‘l’, k[4]=‘o’,

//k[5]=13 or ‘\n’ (ASCII new line character),
//k[6]=0 or ‘\0’ (null character – end of string)

## Program variables

• A variable is an addressable storage location to information to be used by the program

– Each variable must be declared to indicate size and type of information to be stored, plus name to be used to reference the information.

int x,y,z; //declares 3 variables of type “int”

char a,b; //declares 2 variables of type “char”

– Space for variables may be allocated in registers, RAM, or ROM/Flash (for constants)

– Variables can be automatic or static

## Variable arrays

- An array is a set of data, stored in consecutive memory locations, beginning at a named address
  - Declare array name and number of data elements, N 
  - Elements are “indexed”, with indices [0 .. N-1]

int n[5]; //declare array of 5 “int” values

n[3] = 5; //set value of 4th array element

![image](https://github.com/user-attachments/assets/3a232c93-b4a9-4f14-800f-eec17cdc2d54)

Note: Index of first element is always 0. n+16

## Automatic variables

- Declare within a function/procedure

- Variable is visible (has scope) only within that function
  - Space for the variable is allocated on the system stack when the procedure is entered
    - Deallocated, to be re-used, when the procedure is exited
   
  - If only 1 or 2 variables, the compiler may allocate them to registers within that procedure, instead of allocating 
    memory.

   - Values are not retained between procedure calls
    
## Automatic variable example

![image](https://github.com/user-attachments/assets/e8359d96-3885-46fc-81b9-39433f181612)

## Static variables

- Retained for use throughout the program in RAM locations that are not reallocated during program execution.

- Declare either within or outside of a function
  - If declared outside a function, the variable is global in scope, i.e. known to all functions of the program
    - Use “normal” declarations. Example: int count;

  - If declared within a function, insert key word static before the variable definition. The variable is local in scope, i.e. known only within this function.

static unsigned char bob;

static int pressure[10];

## Static variable example

<pre><code>
unsigned char count; //global variable is static – allocated a fixed RAM location
//count can be referenced by any function
void math_op () {
    int i; //automatic variable – allocated space on stack when function entered
    static int j; //static variable – allocated a fixed RAM location to maintain the value
    if (count == 0) //test value of global variable count
        j = 0; //initialize static variable j first time math_op() entered
    i = count; //initialize automatic variable i each time math_op() entered
    j = j + i; //change static variable j – value kept for next function call
} //return & deallocate space used by automatic variable i

void main(void) {
    count = 0; //initialize global variable count
    while (1) {
        math_op();
        count++; //increment global variable count
    }
}
</code></pre>

## C statement types

- Simple variable assignments
  - Includes input/output data transfers

- Arithmetic operations

- Logical/shift operations

- Control structures
  - IF, WHEN, FOR, SELECT  

- Function calls
  - User-defined and/or library functions

## Arithmetic operations

- C examples – with standard arithmetic operators

<pre><code>
int i, j, k; // 32-bit signed integers
uint8_t m,n,p; // 8-bit unsigned numbers
i = j + k; // add 32-bit integers
m = n - 5; // subtract 8-bit numbers
j = i * k; // multiply 32-bit integers
m = n / p; // quotient of 8-bit divide
m = n % p; // remainder of 8-bit divide
i = (j + k) * (i - 2); // arithmetic expression
</code></pre>

*, /, % are higher in precedence than +, - (higher precedence applied 1st)

Example: j * k + m / n = (j * k) + (m / n)

Floating-point formats are not directly supported by Cortex-M3 CPUs.

## Bit-parallel logical operators

Bit-parallel (bitwise) logical operators produce n-bit results of the corresponding logical operation:

& (AND) | (OR) ^ (XOR) ~ (Complement)

![image](https://github.com/user-attachments/assets/df58a994-3e84-4211-a605-9d359d59093b)

## Bit set/reset/complement/test

- Use a “mask” to select bit(s) to be altered

![image](https://github.com/user-attachments/assets/75ff476c-9ca5-42ed-985a-1a8f96dfeab2)

## Bit examples for input/output

- Create a “pulse” on bit 0 of PORTA (assume bit is initially 0)

PORTA = PORTA | 0x01; //Force bit 0 to 1

PORTA = PORTA & 0xFE; //Force bit 0 to 0

- Examples

<pre><code>
if ( (PORTA & 0x80) != 0 ) //Or: ((PORTA & 0x80) == 0x80)
    bob(); // call bob() if bit 7 of PORTA is 1

c = PORTB & 0x04; // mask all but bit 2 of PORTB value

if ((PORTA & 0x01) == 0) // test bit 0 of PORTA
    PORTA = c | 0x01; // write c to PORTA with bit 0 set to 1
</code></pre>

## Example: I/O port bits (using bottom half of GPIOB)

![image](https://github.com/user-attachments/assets/e9811f11-bbd6-4c00-86f6-2dfa17e1fea1)

## Shift operators
Shift operators: 

x >> y (right shift operand x by y bit positions)

x << y (left shift operand x by y bit positions)

Vacated bits are filled with 0’s.

Shift right/left fast way to multiply/divide by power of 2

![image](https://github.com/user-attachments/assets/f38cff29-eb8a-4ed6-9031-1a66775f9cba)

## C control structures

- Control order in which instructions are executed (program flow)

- Conditional execution
  - Execute a set of statements if some condition is met
  - Select one set of statements to be executed from several options, depending on one or more conditions

- Iterative execution
  - Repeated execution of a set of statements
    - A specified number of times, or
    - Until some condition is met, or
    - While some condition is true

## IF-THEN structure
- Execute a set of statements if and only if some condition is met

![image](https://github.com/user-attachments/assets/42df5fc1-21ee-4ec0-a27c-fa91fae00691)

## Relational Operators

- Test relationship between two variables/expressions

![image](https://github.com/user-attachments/assets/9837c587-a72a-43cf-a8f2-2c11ccfea1f4)

## Boolean operators

- Boolean operators && (AND) and || (OR) produce TRUE/FALSE results when testing multiple TRUE/FALSE conditions
  - if ((n > 1) && (n < 5)) //test for n between 1 and 5
  - if ((c = ‘q’) || (c = ‘Q’)) //test c = lower or upper case Q

- Note the difference between Boolean operators &&, || and bitwise logical operators &, |
  - if ( k && m) //test if k and m both TRUE (non-zero values)
  - if ( k & m) //compute bitwise AND between m and n,
  
               //then test whether the result is non-zero (TRUE)

## Common error

- Note that == is a relational operator,
- whereas = is an assignment operator.

if ( m == n) //tests equality of values of variables m and n

if (m = n) //assigns value of n to variable m, and then

//tests whether that value is TRUE (non-zero)

The second form is a common error (omitting the second equal sign), and usually produces unexpected results, namely a TRUE condition if n is 0 and FALSE if n is non-zero.

## IF-THEN-ELSE structure

- Execute one set of statements if a condition is met and an
alternate set if the condition is not met.


![image](https://github.com/user-attachments/assets/37cd15cb-e295-4c70-a4e5-3f1e545fe943)







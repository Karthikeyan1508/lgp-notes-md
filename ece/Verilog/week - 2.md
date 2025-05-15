# What is verilog?
Verilog has a variety of constructs as part of it. All are aimed at providing a functionally tested
and a verified design description for the target FPGA or ASIC. 

# Design Methodologies
1. top-down design methodology
2. bottom-up design methodology

## top-down design methodology
![image](https://github.com/user-attachments/assets/a44bdea4-f6c6-462e-96cd-c4abce0ab071)

 In a top-down design
methodology, we define the top-level block and identify the sub-blocks necessary
to build the top-level block. We further subdivide the sub-blocks until we come to
leaf cells, which are the cells that cannot further be divided.

## bottom-up design methodology
![image](https://github.com/user-attachments/assets/759aa08f-414d-4e10-b839-99bdb22cbf84)

In a bottom-up design methodology, we first identify the building blocks that are
available to us. We build bigger cells, using these building blocks. These cells are
then used for higher-level blocks until we build the top-level block in the design.

# Modules
 A module is the basic building block in Verilog. А module can be an element or
 a collection of lower-level design blocks. Typically,elements are grouped into
 modules to provide common functionality that is usedat many places in the design.
 A module provides the necessary functionality tothe higher-level block through its
 port interface (inputs and outputs), but hides the internal implementation. This
 allows the designer to modify module internals without affecting the rest of the design.

#  Instances
A module provides a template from which you can create actual objects. When a
module is invoked, Verilog creates a unique object from the template. Each object
has its own name, variables, parameters and I/O interface. The process of
creating objects from a module template is called instantiation, and the objects are
called instances. 

In Verilog, it is illegal to nest modules. One module definition cannot contain
another module definition within the module and endmodule statements. Instead,
a module definition can incorporate copies of other modules by instantiating
them. It is important not to confuse module definitions and instances of a
module. Module definitions simply specify how the module will work, its
internals, and its interface. Modules must be instantiated for use in the design.

# level of abstraction
## Behavioral or algorithmic level
This is the highest level of abstraction provided by Verilog HDL. A modulecan be implemented in terms of the desired design algorithm without
concern for the hardware implementation details. Designing at this level is
very similar to C programming.
## Dataflow level
At this level the module is designed by specifying the data flow. The
designer is aware of how data flows between hardware registers and how
the data is processed in the design.
## Gate level
The module is implemented in terms of logic gates and interconnections
between these gates. Design at this level is similar to describing a design interms of a gate-level logic diagram.
## Switch level
This is the lowest level of abstraction provided by Verilog. A module can beimplemented in terms of switches, storage nodes, and the interconnections
between them. 

## Lexical Conventions
The basic lexical conventions used by Verilog HDL are similar to those in the C
programming language. Verilog contains a stream of tokens. Tokens can be
comments, delimiters, numbers, strings, identifiers, and keywords. Verilog HDL
is a case-sensitive language. All keywords are in lowercase.

## Whitespace
Blank spaces (\b), tabs (\t) and newlines (\n) comprise the whitespace.
Whitespace is ignored by Verilog except when it separates tokens. Whitespace is
not ignored in strings.

## Comments
Comments can be inserted in the code for readability and documentation. There
are two ways to write comments. A one-line comment starts with "//". Verilog
skips from that point to the end of line. A multiple-line comment starts with "/*"and ends with "*/". Multiple-line comments cannot be nested.

**Example:**

a = b && C; // This is a one-line comment
/* This is a multiple line
comment */
/* This is /* an illegal */ comment */

## Operators
Operators are of three types, unary, binary, and ternary. Unary operators precede
the operand. Binary operators appear between two operands. Ternary operators
have two separate operators that separate three operands.

**Example:**

a =~ b; // ~ is a unary operator. b is the operand
a = b && C; // && is a binary operator. b and c are operands
a = b ? c : d; // ?: is a ternary operator. b, c and d are operands

## Number Specification
There are two types of number specification in Verilog: sized and unsized.

**Sized numbers**
Sized numbers are represented as <size> •<base format> <number>.
<size> is written only in decimal and specifies the number of bits in the number.
Legal base formats are decimal ('d or 'D), hexadecimal ('h or 'H), binary ('b or 'B)and octal ('o or 'O). The number is specified as consecutive digits from 0, 1, 2, 3,4, 5, 6, 7, 8, 9, a, b, c, d, e, f. Only a subset of these digits is legal for a particular base. Uppercase letters are legal for number specification.

4'b1111 // This is a 4-bit binary number
12'habc // This is a 12-bit hexadecimal number
16'd255 // This is a 16-bit decimal number.

**Unsized numbers**
Numbers that are specified without a <base format> specification are decimal
numbers by default. Numbers that are written without a <size> specification have
a default number of bits that is simulator- and machine-specific (must be at least
32).

23456 // This is a 32-bit decimal number by default
'hc3 // This is a 32-bit hexadecimal number
'021 // This is a 32-bit octal number

**X or Z values**

Verilog has two symbols for unknown and high impedance values. These values
are very important for modeling real circuits. An unknown value is denoted by
an x. A high impedance value is denoted by z.

12'h13x //Thisis a 12-bit hex number; 4 least significant bits unknown
6'hx //This is a 6-bit hex number
32'bz//This is a 32-bit high impedance number

An x or z sets four bits for a number in the hexadecimal base, three bits for a
number in the octal base, and one bit for a number in the binary base. If the most
significant bit of a number is 0, x, or z, the number is automatically extended to
fill the most significant bits, respectively, with 0, x, or z. This makes it easy to
assign x or z to whole vector. If the most significant digit is 1, then it is also zero
extended.

**Negative numbers**
Negative numbers can be specified by putting a minus sign before the size for a
constant number. Size constants are always positive. It is illegal to have a minus
sign between <base format> and <number>.

-6'd3// 8-bit negative number stored as 2's complement of 3
4'd-2// Illegal specification

**Underscore characters and question marks**
An underscore character "" is allowed anywhere in a number except the first
character. Underscore characters are allowed only to improve readability of
numbers and are ignored by Verilog.

A question mark "?" is the Verilog HDL alternative for in the context of numbers. The ? is used to enhance readability in the casex and casez statements discussed in Chapter 7, Behavioral Modeling, where the high impedance value is don't care condition. (Note that ? has a different meaning in the context of userdefined primitives, which are discussed in Chapter 12, User-Defined Primitives.)

12'b1111_0000_1010 // Use of underline characters for readability
4'b10?? // Equivalent of a 4'b10zz

 **Strings**
A string is a sequence of characters that are enclosed by double quotes. The
restriction on a string is that it must be contained on a single line, that is, withouta carriage return. It cannot be on multiple lines. Strings are treated as a sequence
of one-byte ASCII values.

**Example:**

"Hello Verilog World" // is a string
"a/ b" // is a string

**Identifiers and Keywords**
Keywords are special identifiers reserved to define the language constructs.
Keywords are in lowercase. A list of all keywords in Verilog is contained in
Appendix C, List of Keywords, System Tasks, and Compiler Directives.

Identifiers are names given to objects so that they can be referenced in the design.
Identifiers are made up of alphanumeric characters, the underscore (_) and the
dollar sign ( $ ) and are case sensitive. Identifiers start with an alphabetic
character or an underscore. They cannot start with a number or a $ sign (The $
sign as the first character is reserved for system tasks, which are explained later in
the book).

**Example:**
reg value; // reg is a keyword; value is an identifier
input clk; // input is a keyword, clk is an identifier

**Escaped Identifiers**
Escaped identifiers begin with the backslash (\ ) character and end with
whitespace (space, tab, or newline). All characters between backslash and
whitespace are processed literally. Any printable ASCII character can be included
in escaped identifiers. The backslash or whitespace is not considered a part of the
identifier.

\a+b-c
\ **my_name**

# Data Types

## Value Set
Verilog supports four values and eight strengths to model the functionality of real
hardware. The four value levels are listed in Table

![image](https://github.com/user-attachments/assets/3a45957c-31be-4353-815e-0e26b82d40cd)

In addition to logic values, strength levels are often used to resolve conflicts
between drivers of different strengths in digital circuits. Value levels 0 and 1 can
have the strength levels listed in Table

![image](https://github.com/user-attachments/assets/74922dfc-a059-47e3-a5bd-0723c286edcd)

If two signals of unequal strengths are driven on a wire, the stronger signal
prevails. For example, if two signals of strength strong1 and weak0 contend, the
result is resolved as a strong1. If two signals of equal strengths are driven on a
wire, the result is unknown. If two signals of strength strong1 and strong0
conflict, the result is an x. Strength levels are particularly useful for accurate
modeling of signal contention, MOS devices, dynamic MOS, and other low-level
devices. Only trireg nets can have storage strengths large, medium, and smal1.
Detailed information about strength modeling is provided in Appendix A,
Strength Modeling and Advanced Net Definitions.

## Nets
Nets represent connections between hardware elements. Just as in real circuits, nets
have values continuously driven on them by the outputs of devices that they are
connected to. In Figure 3-1 net a is connected to the output of and gate g1. Net a
will continuously assume the value computed at the output of gate g1, which is b &
C.

![image](https://github.com/user-attachments/assets/4a48aa66-aded-4685-85a0-b865892c68b2)

Nets are declared primarily with the keyword wire. Nets are one-bit values by
default unless they are declared explicitly as vectors. The terms wire and net are
often used interchangeably. The default value of a net is z (except the trireg net,
which defaults to x). Nets get the output value of their drivers. If a net has no
driver, it gets the value z.

**Example:**
wire a; // Declare net a for the above circuit
wire b, c; // Declare two wires b,c for the above circuit
wire d = 1'b0; // Net d is fixed to logic value 0 at declaration.

Note that net is not a keyword but represents a class of data types such as wire,
wand, wor, tri, triand, trior, trireg, etc. The wire declaration is used most
frequently. Other net declarations are discussed in Appendix A, Strength Modeling
and Advanced Net Definitions.

## Registers
Registers represent data storage elements. Registers retain value until another
value is placed onto them. Do not confuse the term registers in Verilog with
hardware registers built from edge-triggered flip-flops in real circuits. In Verilog,
the term register merely means a variable that can hold a value. Unlike a net, a
register does not need a driver. Verilog registers do not need a clock as hardware
registers do. Values of registers can be changed anytime in a simulation by
assigning a new value to the register.
Register data types are commonly declared by the keyword reg. The default
value for a reg data type isx. An example of how registers are used is shown in example:

reg reset; // declare a variable reset that can hold its value
initial // this construct will be discussed later
begin
reset = 1'bl; //initialize reset to 1 to reset the digital circuit.
#100 reset = 1'b0; // after 100 time units reset is deasserted.
end

##  Vectors
Nets or reg data types can be declared as vectors (multiple bit widths). If bit
width is not specified, the default is scalar (1-bit).

**Example code:**
wire a; // scalar net variable, default
wire [7:0] bus; // 8-bit bus
wire [31:0] busA, busB, busC; // 3 buses of 32-bit width.
reg clock; // scalar register, default
reg [0:40] virtual_addr; // Vector register, virtual address 41bits wide

Vectors can be declared at [high# : low#] or [low#: high#], but the left number in
the squared brackets is always the most significant bit of the vector. In the
example shown above, bit 0 is the most significant bit of vector virtual_addr.
For the vector declarations shown above, it is possible to address bits or parts of
vectors.

**Example code:**
busA [7] // bit # 7 of vector busA
bus [2:0] // Three least significant bits of vector bus,
// using bus [0:2] is illegal because the significant bit should
// always be on the left of a range specification
virtual_addr [0:1] // Two most significant bits of vector virtual_addr

##  Integer, Real, and Time Register Data Types
Integer, real, and time register data types are supported in Verilog.

**Integer**
An integer is a general purpose register data type used for manipulating
quantities. Integers are declared by the keyword integer. Although it is possibleto use reg as a general-purpose variable, it is more convenient to declare an
integer Variable for purposes such as counting. The default width for an integer
is the host-machine word size, which is implementation specific but is at least 32
bits. Registers declared as data type reg store values as unsigned quantities,
whereas integers store values as signed quantities.

**Example code:**
integer counter; // general purpose variable used as a counter.
initial
counter = -1; // A negative one is stored in the counter

**Real**
Real number constants and real register data types are declared with the keyword
real. They can be specified in decimal notation (e.g., 3.14) or in scientific notation
(e.g., 3e6, which is 3 x 106). Real numbers cannot have a range declaration, and
their default value is 0. When a real value is assigned to an integer, the real
number is rounded off to the nearest integer.

**Example code:**
real delta; // Define a real variable called delta
initial
begin
end
delta = 4e10; // delta is assigned in scientific notation
delta = 2.13; // delta is assigned a value 2.13
integer i; // Define an integer i
initial
i = delta; // i gets the value 2 (rounded value of 2.13)

**Time**
Verilog simulation is done with respect to simulation time. A special time register
data type is used in Verilog to store simulation time. A time variable is declared
with the keyword time. The width for time register data types is implementation
specific but is at least 64 bits.The system function $time is invoked to get the
current simulation time.

**Example code:**
time save_sim_time; // Define a time variable save_sim_time
initial
save_sim_time = $time; // Save the current simulation time

Simulation time is measured in terms of simulation seconds. The unit is denoted by
s, the same as real time. However, the relationship between real time in the digital
circuit and simulation time is left to the user. 

**Arrays**
Arrays are allowed in Verilog for reg, integer, time, and vector register data
types. Arrays are not allowed for real variables. Arrays are accessed by
<array_name>[<subscript>1. Multidimensional arrays are not permitted in Verilog.

**Example code:**
integer count[0:7]; // An array of 8 count variables
reg bool[31:0]; // Array of 32 one-bit boolean register variables
time chk_point [1:100]; // Array of 100 time checkpoint variables
reg [4:0] port_id[0:7]; // Array of 8 port_ids;each port_id is 5 bits wide
integer matrix[4:0][4:0]; // Illegal declaration. Multidimensional
array

count [5] //5th element of array of count variables
chk_point[100] //100th time check point value
port_id[3] // 3rd element of port_id array. This is a 5-bit value.

It is important not to confuse arrays with net or register vectors. A vector is a
single element that is n-bits wide. On the other hand, arrays are multiple
elements that are 1-bit or n-bits wide.

**Memories**
In digital simulation, one often needs to model register files, RAMs, and ROMs.
Memories are modeled in Verilog simply as an array of registers. Each element of
the array is known as a word. Each word can be one or more bits. It is important
to differentiate between n 1-bit registers and one n-bit register. A particular word
in memory is obtained by using the address as a memory array subscript.

**Example code:**
reg mem1bit [0:1023]; // Memory memlbit with 1K 1-bit words
reg [7:0] membyte[0:1023];// Memory membyte with 1K 8-bit words (bytes)
membyte[511] // Fetches 1 byte word whose address is 511.

**Рarameters**
Verilog allows constants to be defined in a module by the keyword parameter.
Parameters cannot be used as variables. Parameter values for each module
instance can be overridden individually at compile time. This allows the module
instances to be customized. This aspect is discussed later.

**Example code:**
parameter port_id = 5; // Defines a constant port_id
parameter cache_line_width =256; //Constant defines width of cache line

Module definitions may be written in terms of parameters. Hardcoded numbers
should be avoided. Parameters can be changed at module instantiation or by
using the defparam statement, which is discussed in detail in Chapter 9, Useful
Modeling Techniques. Thus, use of parameters makes the module definition
flexible. Module behavior can be altered simply by changing the value of a
parameter.

**Strings**
Strings can be stored in reg. The width of the register variables must be large
enough to hold the string. Each character in the string takes up 8 bits (1 byte). If
the width of the register is greater than the size of the string, Verilog fills bits to
the left of the string with zeros. If the register width is smaller than the string
width, Verilog truncates the leftmost bits of the string. It is always safe to declare
a string that is slightly wider than necessary.

**Example code:**
reg [8*18:1] string_value; // Declare a variable that is 18 bytes
wide
initial
string_value = "Hello Verilog World"; // String can be stored
// in variable

Special characters serve a special purpose in displaying strings, such as newline,tabs and displaying argument values. Special characters can be displayed in
strings only when they are preceded by escape characters, as shown in Table

![image](https://github.com/user-attachments/assets/b096eb4b-3814-4f58-b631-2254d1ba8eb7)

# System Tasks and Compiler Directives

##  System Tasks
Verilog provides standard system tasks to do certain routine operations. All
system tasks appear in the form $<keyword>. Operations such as displaying on
the screen, monitoring values of nets, stopping, and finishing are done by system
tasks. We will discuss only the most useful system tasks. Other tasks are listed in
Verilog manuals provided by your simulator vendor or in the Verilog HDL
Language Reference Manual.

**Displaying information**
$display is the main system task for displaying values of variables or strings or
expressions. This is one of the most useful tasks in Verilog.
Usage: $aisplay(pl, p2, p3,....., pn);
p1, p2, p3,..., pn can be quoted strings or variables or expressions. The format of
$display is very similar to printf in C. A $display inserts a newline at the end
of the string by default. A $display without any arguments produces a newline.

**Example code:**
//Display the string in quotes
$display("Hello Verilog World");
-- Hello Verilog World
//Display value of current simulation time 230
$display($time);
-- 230
//Display value of 41-bit virtual address 1fe0000001c and time 200
reg [0:40] virtual_addr;
$display("At time &d virtual address is %h", $time, virtual_addr);
-- At time 200 virtual address is 1fe0000001c
//Display value of port_id 5 in binary
reg [4:0] port_id;
$display("ID of the port is %b", port_id);
-- ID of the port is 00101
//Display x characters
//Display value of 4-bit bus 10xx (signal contention) in binary
reg [3:0] bus;
$display("Bus value is %b", bus)
-- Bus value is 10xx
//Display the hierarchical name of instance p1 instantiated under
//the highest-level module called top. No argument is required. This
//is a useful feature)
$display("This string is displayed from %m level of hierarchy");
-- This string is displayed from top.p1 level of hierarchy

**Monitoring information**
Verilog provides a mechanism to monitor a signal when its value changes. This
facility is provided by the $monitor task.
Usage: $monitor(p1,p2,p3,....,.pn):
The parameters p1, p2, ..., pn can be variables, signal names, or quoted strings. A
format similar to the $display task is used in the $monitor task. $monitor
continuously monitors the values of the variables or signals specified in the
parameter list and displays all parameters in the list whenever the value of any
one variable or signal changes. Unlike $display, $monitor needs to be invoked
only once.

Only one monitoring list can be active at a time. If there is more than one
$monitor statement in your simulation, the last $monitor statement will be the
active statement. The earlier $monitor statements will be overridden.
Two tasks are used to switch monitoring on and off.
Usage: $monitoron;
       $monitoroff;
The $monitoron tasks enables monitoring, and the $monitoroff task disables
monitoring during a simulation. Monitoring is turned on by default at the
beginning of the simulation and can be controlled during the simulation with the
$monitoron and $monitoroff tasks. Examples of monitoring statements are
given in Example 3-4. Note the use of $time in the $monitor statement.

**Example code:**
//Monitor time and value of the signals clock and reset
//Clock toggles every 5 time units and reset goes down at 10 time units
initial
begin
end
$monitor($time,
" Value of signals clock = %b reset = %b", clock, reset);
Partial output of the monitor statement:
-- 0 Value of signals clock = 0 reset = 1
-- 5 Value of signals clock = 1 reset = 1
-- 10 Value of signals clock = 0 reset = 0

**Stopping and finishing in a simulation**
The task $stop is provided to stop during a simulation.
Usage: $stop;
The $stop task puts the simulation in an interactive mode. The designer can then
debug the design from the interactive mode. The $stop task is used whenever the
designer wants to suspend the simulation and examine the values of signals in
the design.
The $finish task terminates the simulation.
Usage: $tinish;

**Example code:**
// Stop at time 100 in the simulation and examine the results
// Finish the simulation at time.
initial // to be explained later. time = 0
begin
clock = 0;
reset = 1;
#100 $stop: // This will suspend the simulation at time = 100
#900 $finish; // This will terminate the simulation at time = 1000
end

**Compiler Directives**
Compiler directives are provided in Verilog. All compiler directives are defined
by using the `<keyword> construct. We deal with the two most useful compiler
directives.

**`define**
The`define directive is used to define text macros in Verilog (see Example 3-6).
This is similar to the #define construct in C. The defined constants or text macros
are used in the Verilog code by preceding them with a (back tick). The Verilog
compiler substitutes the text of the macro wherever it encounters a
`<macro_name>.

**Example code:**
//define a text macro that defines default word size
//Used as 'WORD_SIZE in the code
'define WORD_SIZE 32
//define an alias. A $stop will be substituted wherever 'S appears
'define S $stop;
//define a frequently used text string
'define WORD_REG reg [31:0]
// you can then define a 32-bit register as 'WORD_REG reg32;

**include**
The `include directive allows you to include entire contents of a Verilog source
file in another Verilog file during compilation. This works similarly to the #include
in the C programming language. This directive is typically used to include header
files, which typically contain global or commonly used definitions

**Example code:**
// Include the file header.v, which contains declarations in the
// main verilog file design.v.
include header.v
<Verilog code in file design.v>

# Modules and Ports 

![image](https://github.com/user-attachments/assets/7b9cce5f-c52c-4d6d-bc15-e47edc910f5d)

**Ports**
Ports provide the interface by which a module can communicate with its
environment. For example, the input/output pins of an IC chip are its ports. The
environment can interact with the module only through its ports. The internals of
the module are not visible to the environment. This provides a very powerful
flexibility to the designer. The internals of the module can be changed without
affecting the environment as long as the interface is not modified. Ports are also
referred to as terminals.

**List of Ports**
A module definition contains an optional list of ports. If the module does not
exchange any signals with the environment, there are no ports in the list.
Consider a 4-bit full adder that is instantiated inside a top-level module Top. The
diagram for the input/ output ports is shown

![image](https://github.com/user-attachments/assets/8f59503e-6332-4f59-ae2a-a926d4224052)

Notice that in the above figure, the module Top is a top-level module. The module
fulladd4 is instantiated below Top. The module fulladd4 takes input on ports a, b,
and c_in and produces an output on ports sum and c_out. Thus, module fulladd4
performs an addition for its environment. The module Top is a top-level module
in the simulation and does not need to pass signals to or receive signals from the
environment. Thus, it does not have a list of ports. The module names and port
lists for both module declarations in Verilog are as shown in Example

module fulladd4 (sum, c_out, a, b, c_in); //Module with a list of ports
module Top; // No list of ports, top-level module in simulation

**Port Declaration**
All ports in the list of ports must be declared in the module. Ports can be declaredas follows:

![image](https://github.com/user-attachments/assets/2670808b-905b-485f-aa3e-8f7b3f38a051)

Each port in the port list is defined as input, output, or inout, based on the
direction of the port signal. Thus, for the example of the fulladd4 in Example 4-2,
the port declarations will be as shown in Example

module fulladd4 (sum, c_out, a, b, c_in);
//Begin port declarations section
output[3:0] sum;
output c_cout;
input [3:0] a, b;
input c_in;
//End port declarations section
<module internals>
endmodule

Note that all port declarations are implicitly declared as wire in Verilog. Thus, ifa port is intended to be a wire, it is sufficient to declare it as output, input, or
inout. Input or inout ports are normally declared as wires. However, if output
ports hold their value, they must be declared as reg. For example, in the
definition of DFF, in Example 2-5, we wanted the output q to retain its value untilthe next clock edge. The port declarations for DFF will look as shown in Example

module DFF(q, d, clk, reset);
output q;
reg q; // Output port q holds value; therefore it is declared as reg.
input d, clk, reset;
endmodule

Ports of the type input and inout cannot be declared as reg because reg
variables store values and input ports should not store values but simply reflect
the changes in the external signals they are connected to.

 **Port Connection Rules**
One can visualize a port as consisting of two units, one unit that is internal to the
module another that is external to the module. The internal and external units are
connected. There are rules governing port connections when modules are
instantiated within other modules. The Verilog simulator complains if any port
connection rules are violated. These rules are summarized in Figure

![image](https://github.com/user-attachments/assets/b5137a89-50c6-4bb1-b13c-f0e442f7fcef)

**Inputs**
Internally, input ports must always be of the type net. Externally, the inputs can
be connected to a variable which is a reg or a net.

**Outputs**
Internally, outputs ports can be of the type reg or net. Externally, outputs must
always be connected to a net. They cannot be connected to a reg.

**Inouts**
Internally, inout ports must always be of the type net. Externally, inout ports must
always be connected to a net.

**Width matching**
It is legal to connect internal and external items of different sizes when making
inter-module port connections. However, a warning is typically issued that the
widths do not match.

**Unconnected ports**
Verilog allows ports to remain unconnected. For example, certain output ports
might be simply for debugging, and you might not be interested in connecting
them to the external signals. You can let a port remain unconnected by
instantiating a module as shown below.

fulladd4 fa0 (SUM, А, В, C_IN); // Output port c_out is unconnected

# Gate-Level Modeling 
## Gate Types
**And/Or Gates**
And/or gates have one scalar output and multiple scalar inputs. The first terminal
in the list of gate terminals is an output and the other terminals are inputs. The
output of a gate is evaluated as soon as one of the inputs changes. The and/or
gates available in Verilog are shown below.

and  or  xor
nand  nor  xnor

The corresponding logic symbols for these gates are shown in Figure 5-1. We
consider gates with two inputs. The output terminal is denoted by out. Input
terminals are denoted by il and i2.

![image](https://github.com/user-attachments/assets/302a95b4-aa42-4b27-abae-67e7e1afc965)

These gates are instantiated to build logic circuits in Verilog. Examples of gate
instantiations are shown below. In Example 5-1, for all instances, OUT is
connected to the output out, and IN1 and IN2 are connected to the two inputs i1
and i2 of the gate primitives. Note that the instance name does not need to be
specified for primitives. This lets the designer instantiate hundreds of gates
without giving them a name.
More than two inputs can be specified in a gate instantiation. Gates with more
than two inputs are instantiated by simply adding more input ports in the gate
instantiation (see Example 5-1). Verilog automatically instantiates the appropriate
gate.

**Example code:**
wire OUT, IN1, IN2;
// basic gate instantiations.
and al(OUT, IN1, IN2);
nand nal(OUT, IN1, IN2);
or orl(OUT, IN1, IN2);
nor norl(OUT, IN1, IN2);
xor x1(OUT, IN1, IN2);
xnor nx1 (OUT, IN1, IN2);
// More than two inputs; 3 input nand gate
nand nal_3inp (OUT, IN1, IN2, IN3);
// gate instantiation without instance name
and (OUT, IN1, IN2); // legal gate instantiation

The truth tables for these gates define how outputs for the gates are computed
from the inputs. Truth tables are defined assuming two inputs. The truth tables
for these gates are shown in Table

![image](https://github.com/user-attachments/assets/a4a74d5e-2ce5-4626-a844-cf0fcd4c139a)

**Gate-level multiplexer**
4-to-1 multiplexer with 2 select signals. Multiplexers serve a
useful purpose in logic design. They can connect two or more sources to a single
destination. They can also be used to implement boolean functions. We will
assume for this example that signals s1 and s0 do not get the value x or z. The
I/O diagram and the truth table for the multiplexer are shown in Figure

![image](https://github.com/user-attachments/assets/86d3e64a-3e30-44d4-a6b5-6c6e0aca5a9b)

![image](https://github.com/user-attachments/assets/dfec305d-0e37-46e1-aa75-1bc13d318454)

The logic diagram has a one-to-one correspondence with the Verilog description.
The Verilog description for the multiplexer is shown in Example 5-4. Two
intermediate nets, sOn and s1n, are created; they are complements of input signals
s1 and s0. Internal nets y0, y1, y2, y3 are also required. Note that instance names
are not specified for primitive gates, not, and, and or. Instance names are
optional for Verilog primitives but are mandatory for instances of user-defined
modules.

**Example code:**
// Module 4-to-1 multiplexer. Port list is taken exactly from
// the I/0 diagram.
module mux4_to_1 (out, 10, i1, i2, i3, s1, s0);
// Port declarations from the I/0 diagram
output out;
input 10, il, i2, 13;
input s1, s0;
// Internal wire declarations
wire sin, s0n;
wire y0, y1, y2, y3;
// Gate instantiations
// Create sin and s0n signals.
not (sln, s1);
not (son, s0);
// 3-input and gates instantiated
and (y0, i0, sin, son) ;
and (yl, il, sln, s0);
and (y2, 12, s1, s0n);
and (y3, 13, s1, s0);
// 4-input or gate instantiated
or (out, y0, y1, y2, y3);
endmodule

This multiplexer can be tested with the stimulus shown in Example 5-5. The
stimulus checks that each combination of select signals connects the appropriate
input to the output. The signal OUTPUT is displayed one time unit after it
changes. System task $monitor could also be used to display the signals when
they change values.

**Example code:**
// Define the stimulus module (no ports)
module stimulus;
// Declare variables to be connected
// to inputs
reg INO, IN1, IN2, IN3;
reg S1, SO;
// Declare output wire
wire OUTPUT;
// Instantiate the multiplexer
mux4_to_1 mymux (OUTPUT, INO, IN1, IN2, IN3, S1, SO);
// Define the stimulus module (no ports)
// Stimulate the inputs
initial
begin
// set input lines
INO = 1; IN1 = 0; IN2 = 1; IN3 = 0;
#1 $display("INO= %b, IN1= %b, IN2= %b, IN3=
%b\n",INO, IN1, IN2,IN3);
// choose INO
S1 = 0; SO = 0;
#1 $display("S1 = %b, S0 = %b, OUTPUT = %b \n", S1, SO, OUTPUT);
// choose IN1
S1 = 0; S0 = 1;
#1 $display("S1 = %b, S0 = %b, OUTPUT = %b \n", S1, S0, OUTPUT);
// choose IN2
S1 = 1; SO = 0;
#1 $display("S1 = %b, S0 = %b, OUTPUT = %b \n", S1, SO, OUTPUT);
// choose IN3
S1 = 1; S0 = 1;
#1 $display("S1 = %b, s0 = %b, OUTPUT = %b \n", S1, S0, OUTPUT);
end
endmodule

The output of the simulation is shown below. Each combination of the select
signals is tested.

INO= 1, IN1= 0, IN2= 1, IN3= 0
S1 = 0, SO = 0, OUTPUT = 1
S1 = 0, SO = 1, OUTPUT = 0
S1 = 1, SO = 0, OUTPUT = 1
S1 = 1, SO = 1, OUTPUT = 0

## Gate Delays
In real circuits, logic gates have delays associated with them. Gate delays allow the
Verilog user to specify delays through the logic circuits. Pin-to-pin delays can also
be specified in Verilog. They are discussed in Chapter 10, Timing and Delays.

##  Rise, Fall, and Turn-off Delays
There are three types of delays from the inputs to the output of a primitive gate.

**Rise delay**
The rise delay is associated with a gate output transition to a 1 from another
value.

**Fall delay**
The fall delay is associated with a gate output transition to a 0 from another
value.

![image](https://github.com/user-attachments/assets/f20af78f-3907-41cc-a596-2aee28e238fc)

**Turn-off delay**
The turn-off delay is associated with a gate output transition to the high
impedance value (z) from another value.
If the value changes to x, the minimum of the three delays is considered.
Three types of delay specifications are allowed. If only one delay is specified, this
value is used for all transitions. If two delays are specified, they refer to the rise
and fall delay values. The turn-off delay is the minimum of the two delays. If all
three delays are specified, they refer to rise, fall, and turn-off delay values. If no
delays are specified, the default value is zero. 

**Example code:**
// Delay of delay_time for all transitions
and #(delay_time) al(out, il, i2);
// Rise and Fall Delay Specification.
and #(rise_val, fall_val) a2(out, il, i2);
// Rise, Fall, and Turn-off Delay Specification
bufif0 #(rise_val, fall_val, turnoff_val) bl (out, in, control);

**Examples of delay specification are shown below.**

and #(5) al(out, i1, i2); //Delay of 5 for all transitions
and #(4,6) a2(out, il, i2); // Rise = 4, Fall = 6
bufif0 #(3,4,5) b1 (out, in, control); //Rise = 3, Fall = 4, Turn-off = 5

## Min/Typ/Max Values
Verilog provides an additional level of control for each type of delay mentioned
above. For each type of delay-rise, fall, and turn-off-three values, min, typ, and
max, can be specified. Any one value can be chosen at the start of the simulation.
Min/typ/max values are used to model devices whose delays vary within a
minimum and maximum range because of the IC fabrication process variations.

**Min value**
The min value is the minimum delay value that the designer expects the gate to
have.

**Typ val**
The typ value is the typical delay value that the designer expects the gate to have.

**Max value**
The max value is the maximum delay value that the designer expects the gate to
have.

Min, typ, or max values can be chosen at Verilog run time. Method of choosing a
min/typ/max value may vary for different simulators or operating systems. (For
Verilog-XLTM, the values are chosen by specifying options +maxdelays,
+typdelay, and +mindelays at run time. If no option is specified, the typical delay
value is the default). This allows the designers the flexibility of building three
delay values for each transition into their design. The designer can experiment
with delay values without modifying the design.

**Example code:**
// One delay
Min, Max and Typical Delay Values
// if +mindelays, delay= 4
// if +typdelays, delay= 5
// if +maxdelays, delay= 6
and #(4:5:6) al(out, i1, 12);
// Two delays
// if +mindelays, rise= 3, fal1= 5, turn-off = min (3,5)
// if +typdelays, rise= 4, fall= 6, turn-off = min (4,6)
// if +maxdelays, rise= 5, fall= 7, turn-off = min(5,7)
and #(3:4:5, 5:6:7) a2 (out, i1, i2);
// Three delays
// if +mindelays, rise= 2 fall= 3 turn-off = 4
// if +typdelays, rise= 3 fall= 4 turn-off = 5
// if +maxdelays, rise= 4 fall= 5 turn-off = 9
and #(2:3:4, 3:4:5, 4:5:6) a3 (out, i1,i2);

# Dataflow Modeling

##  Continuous Assignments
A continuous assignment is the most basic statement in dataflow modeling, used to
drive a value onto a net. A continuous assignment replaces gates in the
description of the circuit and describes the circuit at a higher level of abstraction.
A continuous assignment statement starts with the keyword assign. The syntaх
of an assign statement is as follows.

//Syntax of assign statement in the simplest form
<continuous_assign>
::= assign <drivestrength>?<delay>? <list_of_assignments>;

Notice that drive strength is optional and can be specified in terms of strength
levels discussed in Section 3.2.1, Value Set. We will not discuss drive strength
specification in this chapter. The default value for drive strength is strong1 and
strong0. The delay value is also optional and can be used to specify delay on the
assign statement. This is like specifying delays for gates. Delay specification is
discussed in this chapter. Continuous assignments have the following
characteristics.

1. The left hand side of an assignment must always be a scalar or vector net or
a concatenation of scalar and vector nets. It cannot be a scalar or vector
register. Concatenations are discussed in Section 6.4.8, Concatenation
Operator.
2. Continuous assignments are always active. The assignment expression is
evaluated as soon as one of the right-hand-side operands changes and the
value is assigned to the left-hand-side net.
3. The operands on the right-hand side can be registers or nets or function
calls. Registers or nets can be scalars or vectors.
4. Delay values can be specified for assignments in terms of time units. Delay
values are used to control the time when a net is assigned the evaluated
value. This feature is similar to specifying delays for gates. It is very useful
in modeling timing behavior in real circuits.

**Example code**
// Continuous assign. out is a net. il and i2 are nets.
assign out = il & i2;
// Continuous assign for vector nets. addr is a 16-bit vector net
// addr1 and addr2 are 16-bit vector registers.
assign addr [15:0] = addrl_bits [15:0]^ addr2_bits [15:0];
// Concatenation. Left-hand side is a concatenation of a scalar
// net and a vector net.
assign {c_out, sum[3:0]} = a[3:0] + b[3:0] + c_in;

## Implicit Continuous Assignment

Instead of declaring a net and then writing a continuous assignment on the net,
Verilog provides a shortcut by which a continuous assignment can be placed on a
net when it is declared. There can be only one implicit declaration assignment per
net because a net is declared only once.
In the example below, an implicit continuous assignment is contrasted with a
regular continuous assignment.

**Example code:**
//Regular continuous assignment
wire out;
assign out = inl & in2;
//Same effect is achieved by an implicit continuous assignment
wire out = inl & in2;

# Behavioral Modeling
## Structured Procedures
There are two structured procedure statements in Verilog: always and initial.
These statements are the two most basic statements in behavioral modeling. All
other behavioral statements can appear only inside these structured procedure
statements.

Verilog is a concurrent programming language unlike the C programming
language, which is sequential in nature. Activity flows in Verilog run in parallel
rather than in sequence. Each always and initial statement represents a
separate activity flow in Verilog. Each activity flow starts at simulation time 0.
The statements always and initial cannot be nested. The fundamental
difference between the two statements is explained in the following sections.

##  initial Statement
All statements inside an initial statement constitute an initial block. An
initial block starts at time 0, executes exactly once during a simulation, and
then does not execute again. If there are multiple initial blocks, each block
starts to execute concurrently at time 0. Each block finishes execution
independently of other blocks. Multiple behavioral statements must be grouped,
typically using the keywords begin and end. If there is only one behavioral
statement, grouping is not necessary. This is similar to the begin-end blocks in
Pascal programming language or the {} grouping in the C programming
language.

**Example code:**
module stimulus;
reg x, y, a,b, m;
initial
m = 1'b0; //single statement; does not need to be grouped
initial
begin
#5 a = 1'bl; //multiple statements; need to be grouped
#25 b = 1'b0;
end
initial
begin
#10 x = 1'b0;
#25 y = 1'bl;
end
7
initial
#50 $finish;
endmodule

In the above example, the three initial statements start to execute in parallel at time
0. If a delay #<delay> is seen before a statement, the statement is executed <delay>
time units after the current simulation time. Thus, the execution sequence of the
statements inside the initial blocks will be as follows.
time statement executed
이 m = 1'b0;
5 a = 1'bl;
10 x = 1'b0;
30 b = 1'b0;
35 y = 1'bl;
50 $finish;
The initial blocks are typically used for initialization, monitoring, waveforms
and other processes that must be executed only once during the entire simulation
run. 

## always Statement
All behavioral statements inside an always statement constitute an always block.
The always statement starts at time 0 and executes the statements in the always
block continuously in a looping fashion. This statement is used to model a blockof activity that is repeated continuously in a digital circuit. An example is a clock
generator module that toggles the clock signal every half cycle. In real circuits, the
clock generator is active from time 0 to as long as the circuit is powered on.

**Example code:**
module clock_gen;
reg clock;
//Initialize clock at time zero
initial
clock = 1'b0;
//Toggle clock every half-cycle (time period = 20)
always
#10 clock = ~clock;
initial
#1000 $finish;
endmodule
the always statement starts at time 0 and executes the statement
clock = ~clock every 10 time units. Notice that the initialization of clock has to be
done inside a separate initial statement. If we put the initialization of clock
inside the always block, clock will be initialized every time the always is entered.
Also, the simulation must be halted inside an initial statement. If there is no
$stop or $finish statement to halt the simulation, the clock generator will run
forever.
C programmers might draw an analogy between the always block and an infinite
loop. But hardware designers tend to view it as a continuously repeated activity
in a digital circuit starting from power on. The activity is stopped only by power
off ($finish) or by an interrupt ($stop).

##  Procedural Assignments
Procedural assignments update values of reg, integer, real, or time variables.
The value placed on a variable will remain unchanged until another procedural
assignment updates the variable with a different value. These are unlike
continuous assignments discussed in Chapter 6, Dataflow Modeling, where one
assignment statement can cause the value of the right-hand-side expression to be
continuously placed onto the left-hand-side net. The syntax for the simplest form
of procedural assignment is shown below.

<assignment>
::= <lvalue> = <expression>
 
The left-hand side of a procedural assignment <lvalue> can be one of the
following:
A reg, integer, real, or time register variable or a memory element
A bit select of these variables (e.g., addr[0])
• A part select of these variables (e.g., addr[31:16])
A concatenation of any of the above
The right-hand side can be any expression that evaluates to a value. In behavioral
modeling all operators listed in Table 6-1 on page 92 can be used in behavioral
expressions.
There are two types of procedural assignment statements: blocking and nonblocking.

##  Blocking assignments
Blocking assignment statements are executed in the order they are specified in a
sequential block. A blocking assignment will not block execution of statements
that follow in a parallel block. Both parallel and sequential blocks are discussed in
Section 7.7, Sequential and Parallel Blocks, The operator is used to specify
blocking assignments.

**Example code:**
reg x, y, Z
reg [15:0] reg_a, reg_b;
integer count;
//All behavioral statements must be inside an initial or always block
initial
begin
x = 0; y = 1; z = 1; //Scalar assignments
count = 0; //Assignment to integer variables
reg_a = 16'b0; reg_b = reg_a; //initialize vectors
#15 reg_a[2] = 1'bl; //Bit select assignment with delay
#10 reg_b[15:13] = {x, y, z} //Assign result of concatenation to
// part select of a vector
count = count + 1; //Assignment to an integer (increment)
end

The statement y = 1 is executed only after x = 0 is executed. The
behavior in a particular block is sequential in a begin-end block if blocking
statements are used, because the statements can execute only in sequence. The
statement count = count + 1 is executed last. The simulation times at which the
statements are executed are as follows:

1. All statements x = 0 through reg_b = reg_a are executed at time 0
2. Statement reg_a[2] = 0 at time = 15
3. Statement reg_b[15:13] = {x, y, z} at time = 25
4. Statement count = count + 1 at time = 25
5. Since there is a delay of 15 and 10 in the preceding statements, count = count
+ 1 will be executed at time = 25 units
+ 
Note that for procedural assignments to registers, if the right-hand side has more
bits than the register variable, the right-hand side is truncated to match the width
of the register variable. The least significant bits are selected and the most
significant bits are discarded. If right-hand side has fewer bits, zeros are filled in
the most significant bits of the register variable.

## Nonblocking Assignments
Nonblocking assignments allow scheduling of assignments without blocking
execution of the statements that follow in a sequential block. A <= operator is
used to specify nonblocking assignments. Note that this operator has the same
120 Verilog HDL: A Guide to Digital Design and Synthesis
7
symbol as a relational operator, less_than_equal_to. The operator <= is interpreted
as a relational operator in an expression and as an assignment operator in the
context of a nonblocking assignment. To illustrate the behavior of nonblocking
statements and its difference from blocking statements, let us consider
Example 7-4, convert some blocking assignments to nonblocking assignments,
and observe the behavior.



































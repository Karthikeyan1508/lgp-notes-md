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






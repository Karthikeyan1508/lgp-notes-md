# Object Oriented Programming

## Types of programming

## 1. Structured Programming
The instruction in this approach will be executed in a serial and structured manner.
The purpose of structured programming is to linearise control flow through a computer program so that the execution sequence follows the sequence in which the code is written.
The program uses single-entry and single-exit  formats.
The structured programming mainly consists of four types of elements:
Sequence Statements
Alternation/selection Statements
Iteration Statements
Nested Structure

## 2. Procedural Programming
The paradigm uses a linear top-down approach and treats data and procedures as two different entities.
To solve a large problem, procedural programming language divides the problem into smaller modules called functions or procedures each of which handles a particular responsibility. The  program which solves the entire problem is a collection of such functions.
It focuses on processes rather than data.
Adding new data and functions is not easy and most if the data is global and keeps floating between functions.

## 3. Object Oriented Programming
Organised around data, with the key principle being “data controlling access to code”
Data defines precisely what sort of operations can be applied to that data.
It focuses on data rather than processes.
Programs are divided into objects(resembling real-life entities).
Functions that operate on the same kind of data and tied together - encapsulation.
Data can be hidden from a specific portion of code - abstraction.
Objects can communicate with each other through functions. 

### Features of OOP <br>
1. Class 
2. Object 
3. Encapsulation
4. Abstraction
5. Polymorphism
6. Inheritance

## OBJECTS AND CLASSES

ANY REAL WORLD ENTITY - OBJECT

- Real-world objects share two characteristics: They all have state and behaviour.

![image](https://github.com/user-attachments/assets/febbfb60-8b87-4adb-9a98-b02383d891c9)

- OOP tries to model real world objects and communication between them through its
programming paradigm.
- An object stores its state in data fields(attributes) and exposes its behaviour through
methods (functions).

### GROUP OF SIMILAR OBJECTS - CLASS
-	Class is a blueprint or template from which objects are created.
-	CLASS : Animal
-	OBJECTS : Cat, Dog, etc.

-	We can think of a class as a sketch (prototype) of a house. It contains all the details about the floors, doors, windows, etc. Based on these descriptions we build the house. House is the object.
-	It is a user defined data type (not C++ built in data type)
•	Objects are variables of the type class
•	Behave like built in data type of C

### Class Definition
-	Starts with the keyword class followed by the class name
-	Then the class body comes enclosed by a pair of curly braces.
-	Necessary to end with a semi-colon

![image](https://github.com/user-attachments/assets/14c1c170-d0c0-4117-81e1-1c00693eab08)
 
### Object Definition
-	Classname followed by object name.
-	We declare objects of a class with exactly the same sort of declaration that we declare variables of basic types.
-	Objects can also be defined when a class is defined by placing their names immediately after the closing brace.


![image](https://github.com/user-attachments/assets/0d4972d2-f7bf-4b3f-8820-e75a7479728c)

-	But, usually we would like to declare objects close to the place where they are actually going to be used.


![image](https://github.com/user-attachments/assets/29e8bbe3-78fc-4ff3-8f4d-aa9512f08fdb)

 
## Member Functions

-	A function is a Member Function if it can be declared as a member of the class (Function declaration or definition within the class).
-	It operates on any object of the class of which it is a member, and has access to all the members of a class for that object (public as well as private).

### How to define member functions?
1.	Within the class
-	A member function will be called using a dot operator (.) on an object.

![image](https://github.com/user-attachments/assets/ac3ede64-b10b-47dd-af2b-f7d239cecee2)


2.	Outside the class (using Scope Resolution Operator(::))
-	Here, only important point is that you would have to use class name just before :: operator.
-	Scope of the function is restricted to the class name given.
-	Calling the member function is same as before.

![image](https://github.com/user-attachments/assets/a7359ba5-b2bb-4cac-9a02-b2e9e285e752)


### Features of Member Functions
-	Several classes can use same function names, the conflict will be resolved by the membership label.
-	Member functions can access all data of its class(whether private or public).
-	A member function can call another member function directly without using (.) operator.

![image](https://github.com/user-attachments/assets/c7e3e65c-e384-4f6d-b76a-b0ac4f86f05c)


### Abstraction
Hiding the details?
- Abstraction is the process of hiding the details of an entity and focusing on the essential characteristics of the entity.
REAL WORLD EXAMPLE : TV Remote.

![image](https://github.com/user-attachments/assets/aeee79b1-7e43-477d-9b9f-08fc07983ef6)

### How can we achieve abstraction in OOP?
By the use of Access Specifiers.



### Access Specifiers
The access specifier determines the access permissions of the members of the class that follow it.
-	Public
-	Private
-	Protected
By default - private in C++ and public in Java.
 
### PUBLIC:
-	A public member can be accessed from outside the class anywhere within the scope of the class object
-	We can set and get the value of public variables without any member function.

### PRIVATE:
-	The class members declared as private can be accessed only by the member functions inside the class and the friend functions of the class.
-	They are not allowed to be accessed directly by any object or function outside the class.
-	However, we can access the private data members of a class indirectly using the public member functions of the class.
-	Practically, we define data in private section and related functions in public section so that they can be called from outside of the class

![image](https://github.com/user-attachments/assets/4e7545b8-ee5f-4a2a-a894-cb26d29425c7)

### What is the need of abstraction?
-	This is to prevent other functions and classes from tampering with the class data.
-	•Exclusive data access to class members and protects object integrity by preventing unintended or intended changes
 
## Friend Functions
Who is a friend?
-	The one who knows everything about us but does not stay at our home!

### Declaration and definition of friend function-
-	The function can be defined anywhere in the program like a normal C++ function.
-	The function definition does not use either the keyword friend or scope resolution operator.
	
![image](https://github.com/user-attachments/assets/c94a691e-f2e5-4b73-b1e2-9a0241f8ca3d)


-	Class objects can be passed as arguments to the functions same as normal variables - that’s the magic of OOPs. And hence similarly, they can be the return type of the function as well!
 
### Properties of friend function-
-	It is not in the scope of the class to which it has been declared as friend.

-	It cannot be called using the object as it is not in the scope of that class.

-	It can be invoked like a normal function without using the object.

-	It cannot access the member names directly and has to use an object name and dot membership operator with the member name.
-	It can be declared either in the private or the public part.

-	Usually, it has the objects as arguments.

## Friend function between multiple classes-
-	Member function of one class can be friend functions of other class.
-	
![image](https://github.com/user-attachments/assets/0b523baa-e5ac-4593-b68f-32a684b14726)

-	More than 1 classes can have same function as friend function.
 
## Inline Functions

### Why do we use use functions in our code?
-	To reduce code repetition.

### What happens when we call a function?
-	When the program executes the function call instruction the CPU stores the memory address of the instruction following the function call, copies the arguments of the function on the stack and finally transfers control to the specified function. The CPU then executes the function code, stores the function return value in a predefined memory location/register and returns control to the calling function.
  
![image](https://github.com/user-attachments/assets/d344a195-0b43-4679-a457-1a82fe204eed)

### Overhead-
-	This can become overhead if the execution time of function is less than the switching time from the caller function to called function (callee).
-	For functions that are large and/or perform complex tasks, the overhead of the function call is usually insignificant compared to the amount of time the function takes to run.
-	However, for small, commonly-used functions, the time needed to make the function call is often a lot more than the time needed to actually execute the function’s code. This overhead occurs for small functions because execution time of small function is less than the switching time.
 
### Inline-
-	Having parts arranged in a line.
-	C++ provides an inline functions to reduce the function call overhead.
-	Inline function is a function that is expanded in line when it is called. When the inline function is called whole code of the inline function gets inserted or substituted at the point of inline function call. This substitution is performed by the C++ compiler at compile time. So the overhead of function calling is reduced
-	Inline function may increase efficiency if it is small.
  
![image](https://github.com/user-attachments/assets/d3c576ab-6eb2-4358-ba05-53e17b13eb9a)

### Properties of inline function-
-	All the functions defined inside class definition are by default inline.

-	We must keep inline functions small, small inline functions have better efficiency.

-	Inline functions do increase efficiency, but we should not make all the functions inline.
Because if we make large functions inline, it may lead to code bloat, i.e., makes the program to take up more memory because the statements that define the inline function are reproduced at each point where the function is called and this might affect the speed too.
-	Hence, it is advised to define large functions outside the class definition using scope resolution :: operator, because if we define such functions inside class definition, then they become inline automatically.
  
![image](https://github.com/user-attachments/assets/78922f5f-1e5c-4b0f-853e-7d52e9ea6ef5)

## Static Functions

### What does static mean?
-	Not changing or moving.
-	Static is a keyword in C++ used to give special characteristics to an element. Static elements are allocated storage only once in a program lifetime in static storage area. And they have a scope till the program lifetime.
Before discussing static functions, we’ll study static variables.

### Static keyword can be used with-
-	Static variable in functions.
-	Static Class Objects.
-	Static member variable in class.
-	Static Methods in class.
 
### Static variables inside a function-
-	Not changing or moving.
-	Static variables are initialised only once.
-	Static variable can be defined inside or outside the function.
-	They are local to the block.
-	The default value of static variable is zero.
-	Once this variable is declared, it exists till the program executes. So, the lifetime of a static variable is the lifetime of the program.
-	When used inside function, they are initialised only once, and then they hold there value even through function calls.

![image](https://github.com/user-attachments/assets/5a7cef2a-8d01-4525-8e10-f59f77b6d95b)

![image](https://github.com/user-attachments/assets/d1bb0f20-79ba-4295-8023-cce820839f2d)

### Static variables of a class-
-	It is initialised to zero when the first object of its class is created.
-	Another kind of initialisation is outside the class.
-	Only one copy of that member is created for the entire class and is shared by all the objects of that class, no matter how many objects are created.
-	It is a property of the class rather than any object.
-	Static variables are normally used to maintain values common to the entire class. For example, a static data member can be used as a counter that records the occurrences of all the objects

![image](https://github.com/user-attachments/assets/02ca2113-8859-4bfc-97a2-31d3263dafd6)


### Here is the second kind of initialisation:

[Uploading image.png…]()
 
### Static Member Functions 
Static functions in C++ are member functions that belong to a class rather than an instance of the class. They can be called on the class itself without creating an object.

-	Like static member variable, we can also have static member functions. A member function that is declared static has the following properties:
-	A static function can have access to only other static members (functions or variables)
declared in the same class.
-	A static member function can be called using the class name (instead of its objects) as follows:

•	class-name :: function-name;

-	Static functions are useful in various real-life scenarios, where you need to perform operations related to a class without having to create objects of that class.
-	In a mathematics library, you can have a “Math” class with static functions for common mathematical operations.

![image](https://github.com/user-attachments/assets/db2ec63d-d6d8-4328-9df4-185c42187ec3)
 
## Encapsulation

### The action of enclosing something in a capsule.

![image](https://github.com/user-attachments/assets/80448eb9-48e9-4b7c-bf52-ea73062dc0be)

### Why is there a need for Encapsulation?

Again think of the same TV Remote that we discussed in Abstraction.
 
### How can we achieve encapsulation?
-	By using classes and objects rather than normal datatypes.
-	By the use of access specifiers.
-	By the use of member functions.


![image](https://github.com/user-attachments/assets/728fbf2d-2311-4ce0-beed-6022febee0b0)


### Benefits of Encapsulation
-	Improved code maintainability
-	Data hiding (Abstraction).
-	Code reusability
-	Security (by using access specifiers).
 
## Polymorphism

### Means having many forms.
Real life example - consider a person.
In terms of OOPs - the ability of a message to be displayed in more than one form.

![image](https://github.com/user-attachments/assets/bab3b746-ac0b-4ae5-af72-506f68ce5cff)


 
### What do we understand by Compile Time and Run Time?

### Compile Time:
Definition: Compile time refers to the period when your source code is transformed into machine code by a compiler. It's the phase before your program is executed.

•	Syntax Errors: If you have a typo or a mistake in your code, the compiler will catch it during compile time. For example, if you forget a semicolon at the end of a line, the compiler will generate an error message.

•	Type Checking: The compiler checks that you're using variables and functions in a way that's consistent with their declared types. If you try to assign a string to an integer variable, it will generate an error during compile time.

•	Purpose: The primary purpose of compile time is to translate human-readable source code into machine code that the computer can execute.

### Run Time:
Definition: Run time, also known as execution time, is the period when your program is running and actively performing tasks. It starts after your program has been successfully compiled and launched.

•	User Input: When your program is running, it can interact with users by taking input from the keyboard or other devices. For example, a calculator program waits for you to enter numbers and operations at run time.

•	Calculations: Any computations or operations your program performs while running, such as sorting a list of numbers, are done at run time.

•	File Operations: Reading from or writing to files is a run-time operation. For example, a word processor saves a document to a file when you click the "Save" button.

•	Purpose: The purpose of run time is to execute the instructions and logic that were defined during compile time. It's when your program actually does what it was designed to do.
 
### Compile Time Polymorphism
-	Compile-time polymorphism is achieved through function overloading and operator overloading.
-	C++ allows you to specify more than one definition for a function name or an operator in the same scope, which is called function overloading and operator overloading respectively.
-	An overloaded declaration is a declaration that is declared with the same name as a previously declared declaration in the same scope, except that both declarations have different arguments and obviously different definition (implementation).
-	The information is present during compile-time. This means the C++ compiler will select the right function at compile time.
-	When you call an overloaded function or operator, the compiler determines the most appropriate definition to use. The process of selecting the most appropriate overloaded function or operator is called overload resolution.

### Function Overloading
-	As stated earlier, overloading refers to the use of the same thing for different purposes.
C++ also permits overloading of functions.
-	This means that we can use the same function name to create functions that perform a variety of different tasks. This is known as function polymorphism in OOP.
-	Using the concept of function overloading; we can design a family of functions with one function name but with different argument lists. The function would perform different operations depending on the argument list in the function call.
-	The correct function to be invoked is determined by checking the number and type of the arguments but not on the function type. For example, an overloaded area() function handles different types of data as shown below:
 
### How does compiler distinguish between overloaded functions?
-	A function call first matches the prototype having the same number and type of
arguments and then calls the appropriate function for execution. A best match must be unique. The function selection involves the following steps:

1.	The compiler first tries to find an exact match in which the types of actual arguments are the same, and use that function.

2.	If an exact match is not found, the compiler uses the integral promotions to the actual arguments, such as,
•	char to int
•	float to double

3.	When either of them fails, the compiler tries to use the built-in conversions (the implicit assignment conversions) to the actual arguments and then uses the function whose match is unique. If the conversion is possible to have multiple matches, then the compiler will generate an error message. Suppose we use the following two functions:
•	long square (long n)
•	double square (double x)
Here, a function call such as square(10) will cause an error because int argument can be converted to either long or double, thereby creating an ambiguous situation as to which version of square() should be used.

Overloaded functions may or may not have different return types but they must have different arguments.
 
### Functions that can’t be overloaded:

-	Function declarations that differ only in the return type.

-	Member function declarations with the same name and the name parameter-type-list cannot be overloaded if any of them is a static member function declaration.

-	Two parameter declarations that differ only in their default arguments are equivalent
 
## Operator Overloading

We stated earlier that one of the aims of C++ is to create user-defined data types such as class, that behave very similar to the built-in types.
This means that we should be able to perform operations on objects much the same way as on an ordinary variable.

In C++, we can change the way operators work for user-defined types like objects and structures. This is known as operator overloading. For example,

Syntax:
```
//outside the class
return type classname :: operator op(all the arguments){
//Function body
}


//inside the class
return type operator op(all the arguments){
//Function body
}
```
### Overloading unary operators
-	In unary operator function, no arguments should be passed. It works only with one class object. It is the overloading of an operator operating on a single operand.

### Overloading binary operators
-	In binary operator overloading function, there should be one argument to be passed. It is overloading of an operator operating on two operands.
Although the semantics of an operator can be extended, we cannot change its syntax, the grammatical rules that govern its use such as the number of operands, precedence and associativity. For example, the multiplication operator will enjoy higher precedence than the addition operator.
Remember, when an operator is overloaded, its original meaning is not lost. For instance, the operator +, which has been overloaded to add two fractions, can still be used to add two integers.

### Operators that can’t be overloaded
-	We can overload (give additional meaning to) all the C++ operators except the following:

•	Class member access operators (. , .*)
•	Scope resolution operator (::)
•	Size operator (sizeof)
•	Conditional operator (? :)
 
## Constructors and Destructors
### Let’s get some background…
-		We stated earlier that one of the aims of C++ is to create user-defined data types such as class, that behave very similar to the built-in types.
-	This means that we should be able to initialise a class type variable (object) when it is declared, much the same way as initialisation of an ordinary variable. For example,
•	int m = 20;
•	float x = 5.75;
are valid initialisation statements for basic data types.
-	Similarly, when a variable of built-in type goes out of scope, the compiler automatically destroys the variable. But it has not happened with the objects we have so far studied.
-	C++ provides a special member function called the constructor which enables an object to initialise itself when it is created. This is known as automatic initialisation of objects. It also provides another member function called the destructor that destroys the objects when they are no longer required.

### Constructor
-	A constructor is a 'special' member function whose task is to initialise the objects of its class. It is special because its name is the same as the class name. The constructor is invoked whenever an object of its associated class is created. It is called constructor because it constructs the values of data members of the class.
-	A constructor that accepts no parameters is called the default constructor. The default constructor for class Animal is Animal(). If no such constructor is defined, then the compiler supplies a default constructor. Therefore a statement such as
•	Animal dog;
invokes the default constructor of the compiler to create the object dog.
The constructor functions have some special characteristics. These are:
-	They should be declared in the public section. They are invoked automatically when the objects are created.
-	They do not have return types, not even void and therefore, and they cannot return values.
-	Like other C++ functions, they can have default arguments.
 
### Parameterised Constructors
-	Constructors can also take parameters (just like regular functions), which can be useful for setting initial values for attributes.
-	The constructors that can take arguments are called parameterised constructors.

-	When a constructor has been parameterised, the object declaration statement such as
•	Animal dog;
may not work. We must pass the initial values as arguments to the constructor function when an object is declared.
-	This can be done in two ways:
•	By calling the constructor explicitly.
•	By calling the constructor implicitly.

-	The following declaration illustrates the first method:
```
Animal dog = Animal("German Shepherd”); // explicit call
```
-	This statement creates an integer object dog and passes the string German Shepherd
to it.
-	The second is implemented as follows:
Animal dog("German Shepherd”); // implicit call
-	This method, sometimes called the shorthand method, is used very often as it is shorter, looks better and is easy to implement.

### Copy Constructors
-	The copy constructor is a constructor which creates an object by initialising it with an object of the same class, which has been created previously.
Syntax:
```
Animal(const Animal &dog1){
	//body of the constructor as per your need
	}
 ```

### Destructor
-	A destructor, as the name implies, is used to destroy the objects that have been created by a constructor. Like a constructor, the destructor is a member function whose name is the same as the class name but is preceded by a tilde.
-	For example, the destructor for the class Animal can be defined as shown below:
  ```
~Animal(){
 //body
 }
```
-	A destructor never takes any argument nor does it return any value. It will be invoked implicitly by the compiler upon exit from the program (or block or function as the case may be) to clean up storage that is no longer accessible. It is a good practice to declare destructors in a program since it releases memory space for future use.
-	Destructors are called when one of the following events occurs:
•	A local (automatic) object with block scope goes out of scope.
•	the function ends
•	the program ends
•	a block containing local variables ends.
•	a delete operator is called
•	The lifetime of a temporary object ends.
•	A program ends and global or static objects exist.
•	The destructor is explicitly called using the destructor’s fully qualified name.

-	Destructors can freely call class member functions and access class member data.
-	Can there be more than one destructor in a class?
-	No, there can only one destructor in a class with classname preceded by ~, no parameters and no return type.

### this pointer:
-	Every object in C++ has access to its own address through an important pointer called this pointer.
-	The this pointer is an implicit parameter to all member functions.
-	Therefore, inside a member function, this may be used to refer to the invoking object.
 
## Inheritance

Inheritance: It is the mechanism by which one class is allowed to inherit the features of another class.
Inheritance in real life can be compared to how family relationships work. Imagine a family with multiple generations:
•	Grandparents: They have certain characteristics, like a family name, traditions, and a family home.

•	Parents: They inherit some of these characteristics from their grandparents, like the family name and traditions. They might also have some unique characteristics of their own, like their profession or hobbies.

•	Children: They inherit not only the family name and traditions from their grandparents but also some traits from their parents, such as physical attributes or personality traits. Children also develop their own unique characteristics as they grow up.

Base Class (or superclass): The class whose properties are inherited by sub class is called Base Class or Super class.
Derived Class (or subclass): The class that inherits properties from another class is called Sub class or Derived Class.

In this example:
•	The grandparents can be seen as the "base class" with certain characteristics.

•	The parents are like "subclasses" or "derived classes" because they inherit the grandparents' characteristics and add some of their own.

•	The children are further "subclasses" because they inherit characteristics from both their grandparents and parents but also develop their own unique traits.
 
### Access Specifiers
-	Public -> anybody can access outside the class -> can be inherited
-	Private -> can’t be accessed outside the class except friend functions -> can’t be inherited
-	Protected
Like private members, protected members are inaccessible outside of the class. However, they can be accessed by derived classes and friend functions.
We need protected members if we want to hide the data of a class, but still want that data to be inherited by its derived classes.

![image](https://github.com/user-attachments/assets/291685ad-fc92-4afa-9324-eb00da20eae5)


Access Modes
Syntax:
```
class subclass_name : access_mode baseclass_name{
// body of the class
};
```

![image](https://github.com/user-attachments/assets/518ba30e-ea7a-4d5c-9c2f-3031aaac2ea0)

 
### Types of Inheritance

![image](https://github.com/user-attachments/assets/6d108af4-4ebf-48cd-a91b-74a628b99c16)

Syntax:
```
class subclass_name : access_mode baseclass_name{
// body of the class
};
```

### Function Overriding
-	Suppose, the same function is declared in both the derived class and the base class.
-	Now if we call this function using the object of the derived class, which function will be called ??
-	The function of the derived class is executed.
-	This is known as function overriding in C++.
-	The function in derived class overrides the function in base class.
 
### Pointers - variables that store address of other variables.
```
	int a = 5;
	int* p = &a;

	char c = 'A';
	char* p1 = &c;
```

-	Similarly we can make pointers for user-defined datatypes (i.e. classes).

-	In C++, we can declare a pointer that points to the base class as well as derive class.

-	One of the key features of class inheritance is that a pointer to a derived class is type- compatible with a pointer to its base class.

### Virtual Functions:

-	But, we just discovered that a base pointer, even when it is made to contain the address of a derived class, always executes the function in the base class.
-	The compiler simply ignores the contents of the pointer and chooses the member function that matches the type of the pointer.

-	How do we then achieve polymorphism? It is achieved using what is known as 'virtual' functions.
-	When we use the same function name in both the base and derived classes, the function in base class is declared as virtual using the keyword virtual preceding its normal declaration.
 
-	When a function is made virtual, C++ determines which function to use at run time based on the type of object pointed to by the base pointer, rather than the type of the pointer. Thus, by making the base pointer to point to different objects, we can execute different versions of the virtual function.
-	A virtual function is a member function in the base class that we expect to redefine in derived classes.
-	Basically, a virtual function is used in the base class in order to ensure that the function is overridden. This especially applies to cases where a pointer of base class points to an object of a derived class.
 
## Abstract Class

### Pure Virtual Functions
-	A pure virtual function has no definition in base class.
-	When the function has no definition, such function is known as "do-nothing" function.
-	The "do-nothing" function is known as a pure virtual function. A pure virtual function is a function declared in the base class that has no definition relative to the base class.
-	Sometimes implementation of all functions cannot be provided in a base class because we don’t know the implementation. Such a class is called abstract class.

### Abstract Class
-	A class that contains at least one pure virtual function is known as an abstract class.
-	We cannot create objects of an abstract class.
-	However, we can derive classes from them, and use their data members and member functions (except pure virtual functions).
-	An abstract class is one that is not used to create objects. An abstract class is designed only to act as a base class (to be inherited by other classes).
-	It is a design concept in program development and provides a base upon which other classes may be built.


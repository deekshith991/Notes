
# C course

## Video 1
In this lecture professor Nithin talked about the add operation that happens in the computer in the terms of electrical system. He also told about the read write and Address of the memory.

## Video 2 : Generalized memory and Computation 31/03/206
- Address Map -> where data is stored.
It decides where the data is placed with restrictions required.

Data map => A | B | op | s | ? |

op (operation) -> tells what to do. It is a set of instructions.

## Video 3 : Split memory architecture

- ***Registers:*** a small low-latency temporary memory that are closedly coupled with ALU.
- ***load:*** Move data from memory to registers.
- ***store:*** move data from registers to memory.

## Video 4 : Loops, conditions and branching
- ***Loop counter:*** it tells about how many times a set of repeatative instructions to do. This method can also be used for branching and control flow.

#### CPU needs the fundamental requirements
  - operations   -> ALU
  - Memory       -> load/store
  - control flow -> branching and loops

## Video 5 : Communication between computer memory & outside world 01/04/2026
All peripherals like input devices(keyboard mouse etc) and output devices(screen, printer, etc) can be referenced as memory to get and delivery info.

## Video 6 : Algorithms, memory and Computation explained
It talks about Algorithms how small the takes are being divided for the CPU to work it basically tell how a quadratic equation can be solved in assembly with pseudocode.

## Video 7 : Introduction to C language
Here we know that the while trying to write a OS for PDP-7(mini computer) ken thompson and Denis ritchie created the C programming language to write the UNIX OS.
It created with a computer
assembly : converts C to assembly
C : converts C to assembly

## Video 8 : Number representation in a computer | binary and data types 02/04/2026
It talks about why and how we are using binary for integers in CPU.

## Video 9 : Negative number & hexadecimal representation.
it is basically compliment another and talked about hexadecimal.

## Video 10 : Floating point representation | real numbers, precision &  IEEE 754 03/04/2024
***1. Fixed point Notation:*** here for a 16bit number we multiply the 2^15 bit value with a fixed scale factor like 2^-8 

***2. Floating point notation:*** Here we use a 32bit memory where for 2x10^30
  - 1 bit is sign bit
  - 8 bit exponent represents 10^x we use this 8 bits for the x. x = 30.
  - 23 main value like 2.

- 16 bit floats called half precision.
- 32 bit floats called single precision.
- 64 bit floats called double precision.

## Video 11 : Character representation & encoding
- ASCII once was 7-bit encoding
- then after 8-bit got popular ASCII got updated to 8-bit
- Unicode was created for languages when we needed to support other languages too.

> [!NOTE]
> need to learn more about this.
#### UNICODE 
  - it specifies the conditions

## Video 12 : Instructions encoding | understand & execute binary code 
ISA - Instruction Set architecture
they are similar to functions in programming languages.

> [!WARNING]
> Not all instructions available on all CPU's.

make a register 0

- mov r1, 0    -> set reg r1 to 0
- add r1, 0, 0 -> add 0 and 0 then place it in r1
- sub r1, r1, r1 -> subtract from itself.
- xor r1, r1, r1 -> number xor with itself = 0.

## Video 13 : program compilation and machine code 
Here nithin talked about about how a binary in assembly looks like and ho they are converted in to machine code so that the machine could run he told about hex representation too.

## Video 14 : Role of operating system in a computer
Some basic shit.


## Video 24 : Functions in C
- "header.h" is a file that contains the function declarations.

## Video 25 : what is a runtime
- something about stack.

## Video 26 : Recursions
- here we leaned how stacks work in recursions saw examples at [c stack visualizer](https://www.pythontutor.com/c.html) visually
- bracket scope: when a variable is declared in a bracket it stays only in that bracket.
- file scope: when a variable declared outside a function then the entire file after the declaration can use the variable.

## Video 28 : Introduction to pointers
***Pointers:*** pointer stores the address of the data store similar to variables.
go to [pointers.c](./src/pointers.c

int, long, pointer byte lengths in different OS
- Linux/apple uses LLP64 4,8,8
- windows uses LLLP64 4,4,8

## Video 29 : Endianness big vs little endian

#### Big-Endian:
- left to right approach
- MSB at lowest address

#### little-Endian:
- top to bottom
- MSB at Highest address

Eg: 0x12345678  is hexdigit value

```
Big-Endian
mem[0]=0x12
mem[1]=0x34
mem[2]=0x56
mem[3]=0x78


Little-Endian
mem[3]=0x12
mem[2]=0x34
mem[1]=0x56
mem[0]=0x78

```

- x86 follow little-Endian
- ARM,RISC-V support both
- In networks Big-Endian is used

## Video 30 : Alignment
Choosing of address such that is the multiple of the size of datatype.


## Video 31 : Pointers and variables
***variable*** is the named address of memory.

## Video 33 : Introduction of Arrays
&i -> Address
*(&i) -> data of i.
*(&i) == int i

***Arrays***: Convenient shortcut of list of homogenous data.
  - specify the start of list
  - number of entries
  - how to reach next value

#### Unusaual case in Initialization
```c
float arr[10] = {1.4,2.5, [5] = 3.14 , 67.7};
```

Array values are { 1.4, 2.5, 0 , 0, 0, 3.14, 67.7, 0, 0, 0, 0};

Here [5] = x the [5] is telling about position.

## Video 35 : Pointer arthematics
```c
A[i] == *(A+i)
```

A -> is the starting address.
i -> is the offset in terms of numbers of elements.

## Video 37 : Strings in C
```c
char *s1 = "hello world";
char s2[]= "hello world";
char s2[10]= "Hello world welcome";
```

- in first case the sizeof operator will always give 8bytes as output because the sizeof pointer is 8bytes.
- in second case we can alter the string with array operations but in first case we can't alter the string.

## Video 38 : String functions

```c
wchar_t s[] = L"teleuguletter english";

```

wchar_t ->datatype for widechar/ unicode
L -> long char

- strlen doesn't work on s because it has lot of null char.
- we use wcslen for strlen.
- wcslen looks for 4byte null char


## Video 43: Union
***Union:*** it basically typecasts a section of memory.

## Video 45: Heap and Stack frames ( Dynamic memory )

|--------------------------|
| Memory structure         | # overall memory layout
|--------------------------|
|                          | # (empty separator)
| code                     | # program instructions segment
| const data               | # read-only constants
|                          | # (empty separator)
| local variables (m)      | # stack frame of function m
| local variables (f)      | # stack frame of function f
|                          | # (empty separator)
|                          | # (empty separator)
| global var's             | # global variables stored in data/heap region
| static values / func     | # static storage duration data and functions
|--------------------------| # end of memory layouts and Topics

## Video 51 : file handling
All files we can we are text mode files
%*s means discard the string


## Video 58 : Introduction to MACROS in C
#### 1. DEFINE 
```c
#define TEXT_MACRO text1 text2
#define ABS(x) ( (x)<0 ? -(x):(x) )
#define MAX(a,b) ( ((a)>(b)) ? (a):(b) )
```

- Macro mostly CAPITALIZED
- it replaces the TEXT_MACRO with text1 text2.
- Macros can have arguments too the macros must have parenthesis.

#### 2. Include


#### Built in macros
```c
__func__
__FILE__
__LINE__
__DATE__
__TIME__
__STDC_VERSION__ // for the version of C
```


# Master Pointer in C
[Code file](./src/masterPointers.c)
House takes 12bytes.

# Additional lecture
1. [Opaque pointers](./Opaque_pointer/Opaque_pointers.md)
2. [kernel github](https://github.com/krnl32) : got some cool stuff.




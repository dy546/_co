# 🖥️ Nand2Tetris: From Logic Gates to Operating System

![Status](https://img.shields.io/badge/Status-Completed-green)
![Language](https://img.shields.io/badge/Languages-HDL%20%7C%20Jack%20%7C%20Python-blue)

## 🏗️ Part I: Hardware Architecture (Projects 1-5) (All Original Work)

### **[Project 1: Boolean Logic](https://github.com/dy546/_co/tree/70fd9e3a6c39c882b5a6b313e701c4bdb64a3689/homework/1)**
**Goal:** Implement elementary logic gates using only `Nand` gates.
* **Core Logic:** `Not`, `And`, `Or`, `Xor`, `Mux`, `DMux`.
* **Multi-Bit Variants:** 16-bit versions of the basic gates (e.g., `And16`).
* **Multi-Way Variants:** `Mux4Way16`, `Mux8Way16`, `DMux4Way`, `DMux8Way`.
> *Key Takeaway:* Any boolean function can be represented using a combination of NAND gates.

### **[Project 2: Boolean Arithmetic](https://github.com/dy546/_co/tree/70fd9e3a6c39c882b5a6b313e701c4bdb64a3689/homework/2)**
**Goal:** Construct an Arithmetic Logic Unit (ALU) capable of performing binary addition and bitwise operations.
* **Adders:** `HalfAdder` (sum & carry) and `FullAdder`.
* **Inc16:** A 16-bit incrementer.
* **The ALU:** The computational brain of the CPU. It computes functions $f(x, y)$ where $x$ and $y$ are 16-bit inputs. It supports 18 different functions based on 6 control bits.

### **[Project 3: Sequential Logic (Memory)](https://github.com/dy546/_co/tree/70fd9e3a6c39c882b5a6b313e701c4bdb64a3689/homework/3)**
**Goal:** Build memory units that maintain state over time using a clock cycle.
* **Bit:** A 1-bit register using a Data Flip-Flop (DFF).
* **Register:** A 16-bit register.
* **RAM:** Built a recursive hierarchy of RAM units (`RAM8`, `RAM64`, `RAM512`, `RAM4K`, `RAM16K`).
* **PC (Program Counter):** Tracks the address of the next instruction to be fetched.

### **[Project 4: Machine Language](https://github.com/dy546/_co/tree/70fd9e3a6c39c882b5a6b313e701c4bdb64a3689/homework/4)**
**Goal:** Write low-level Assembly programs for the Hack computer to understand the hardware/software interface.
* **Mult.asm:** Multiplies `R0` and `R1` and stores the result in `R2` using low-level addition loops.
* **Fill.asm:** Listens to the keyboard input; blackens the screen if a key is pressed, clears it otherwise.

### **[Project 5: Computer Architecture](https://github.com/dy546/_co/tree/70fd9e3a6c39c882b5a6b313e701c4bdb64a3689/homework/5)**
**Goal:** Assemble the chips from previous projects into a functioning computer.
* **Memory.hdl:** Composed of RAM16K, Screen, and Keyboard memory maps.
* **CPU.hdl:** The central processing unit capable of executing instructions, reading/writing to memory, and controlling the PC.
* **Computer.hdl:** The top-level chip connecting the CPU, Instruction Memory (ROM), and Data Memory (RAM).

---

## 💾 Part II: Software Hierarchy (Projects 6-12) (All Copied From [xctom](https://github.com/xctom/Nand2Tetris) Without Modification)

### **[Project 6: The Assembler](https://github.com/dy546/_co/tree/70fd9e3a6c39c882b5a6b313e701c4bdb64a3689/homework/6)**
**Goal:** Develop a program to translate Hack Assembly (`.asm`) into binary machine code (`.hack`).
* **Symbol Table:** Manages symbolic labels (e.g., `(LOOP)`, `@sum`) and maps them to memory addresses.
* **Parser:** Unpacks instructions into fields (A-instruction vs C-instruction).
* **Code Module:** Translates mnemonics (like `D=M+1`) into their corresponding binary bits.

### **[Project 7](https://github.com/dy546/_co/tree/70fd9e3a6c39c882b5a6b313e701c4bdb64a3689/homework/7) & [Project 8](https://github.com/dy546/_co/tree/70fd9e3a6c39c882b5a6b313e701c4bdb64a3689/homework/8): Virtual Machine**
**Goal:** Build a backend translator that converts stack-based VM code into Hack Assembly.
* **Stack Arithmetic:** Implemented commands like `add`, `sub`, `neg`, `eq`, `gt`, `lt`, `and`, `or`, `not`.
* **Memory Access:** Handled memory segments (`local`, `argument`, `this`, `that`, `pointer`, `temp`, `static`).
* **Program Control:** Implemented branching (`label`, `goto`, `if-goto`) and function calling mechanisms (`function`, `call`, `return`).

### **[Project 9: High-Level Language (Jack)](https://github.com/dy546/_co/tree/70fd9e3a6c39c882b5a6b313e701c4bdb64a3689/homework/9)**
**Goal:** Create an interactive application or game using the Jack programming language to test the system.
* **Application:** *[Name of your Game/App]*
* **Description:** A custom application demonstrating object-oriented programming in Jack, featuring graphics, user input, and game logic.

### **[Project 10: Compiler (Syntax Analysis)](https://github.com/dy546/_co/tree/70fd9e3a6c39c882b5a6b313e701c4bdb64a3689/homework/10)**
**Goal:** Build a Tokenizer and Parser for the Jack language.
* **Tokenizer:** Removes comments/whitespace and breaks code into tokens (keywords, symbols, identifiers).
* **XML Output:** Generates a parse tree in XML format to verify that the code follows the grammatical rules of Jack.

### **[Project 11: Compiler (Code Generation)](https://github.com/dy546/_co/tree/70fd9e3a6c39c882b5a6b313e701c4bdb64a3689/homework/11)**
**Goal:** Extend the parser to generate executable VM code.
* **Symbol Table:** Tracks variable scope (class-level vs subroutine-level), types, and indices.
* **VMWriter:** Emits the corresponding stack-machine commands for expressions, flow control, and object creation.

### **[Project 12: The Operating System](https://github.com/dy546/_co/tree/70fd9e3a6c39c882b5a6b313e701c4bdb64a3689/homework/12)**
**Goal:** Implement the standard library in Jack to bridge the gap between high-level code and hardware.
Implemented the following system classes:
* `Math` (efficient multiplication/division)
* `String` (string manipulation)
* `Array` (memory allocation `alloc`/`dealloc`)
* `Output` (printing text/numbers to screen maps)
* `Screen` (drawing pixels, lines, circles, and rectangles)
* `Keyboard` (handling user input)
* `Memory` (OS-level memory access)
* `Sys` (OS initialization and timing)
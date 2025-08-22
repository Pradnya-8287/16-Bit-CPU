# 16-Bit-CPU
This is a custom 16-bit CPU, designed and simulated in Logisim Evolution (v.3.8.0).
The project brings together the core elements of a processor, registers, ALU, memory, control logic, and I/O, into a working 16-bit architecture.

It’s meant as a hands on exploration of computer architecture: writing instructions, executing them in hardware, and watching how the CPU processes data step by step. Along with the circuit, the repo includes assembly examples, opcode files, and a Python script to help generate machine code.

## Overview
- 16-bit architecture with accumulator and general-purpose registers.
- Instruction Set (ISA) with arithmetic, logic, memory, I/O, branching, and even pixel display operations.
- ALU + control logic to execute instructions one step at a time.
- RAM, ROM, and Stack support for programs and subroutines.
- I/O devices: a simple TTY display, keyboard input, and graphics placeholders.

![16-bit CPU Circuit](images/16%20Bit%20CPU.png)

## Repository Contents
- **16BitCPU.circ** → Main CPU circuit and sub circuits (Logisim Evolution file).
- **files/ASSEMBLY INSTRUCTIONS.txt** → Full list of supported instructions (ISA).
- **files/Assembler Python.py** → Python script that assembles .asm programs into machine code.
- **files/FULL OPERATING SYSTEM.asm** → Example assembly code for a simple OS.
- **files/Final Tetris Game.asm** → Tetris game written in assembly.
- **files/Final assembly_tetris game** → Updated Tetris assembly version.
- **files/OPCODE_ROM_MICROCODE_1/2/3** → Opcode ROM microcode files (load into CPU ROM for programs).
- **files/RAM_256_16** → RAM initialization file (256 × 16-bit).
- **files/TETRIS game RAM file** → RAM preload for the Tetris game.
- **images** → Screenshot of the CPU main circuit & sub circuits.

## Instruction Set (ISA)
The CPU supports a wide variety of instructions. Here’s a summary:

- **Data Movement**: LDA, LDB, LDX, LDY, STA, STB, STX, STY, STK, SYX, SXY, SYT
- **Immediate Loads**: LIA, LIB, LIX, LIY, LIT
- **ALU Operations**: ADD, SUB, CMP, ADI, SUI, LNR, LAR, LOR, LXR
- **Branching / Jumps**: JMP, JPL, JPZ, JPE, JPG, JPC, JPY, AIJ, AIE
- **Stack / Calls**: CAL, RET, CAI
- **Display / I/O**: LDT, LIT, LVA, LVD, UPD, RVA, RVD
- **No Operation**: NOP

For the full opcode breakdown, check files/ASSEMBLY INSTRUCTIONS.txt.

## Components
The CPU is built from modular subcircuits, each handling a different role:
- **ALU**: Handles arithmetic and logic operations, updates flags.
- **Registers**: General-purpose registers (B, X, Y) for storage, indexing, and addressing.
- **Flag Register**: Holds condition flags (Zero, Carry, Greater, Less, Equal) for branching.
- **Program Counter (PC)**: Tracks the current instruction address.
- **Instruction Register**: Stores the instruction currently being executed.
- **Memory Address Register (MAR)**: Keeps track of which memory location is being accessed.
- **Step Counter**: Manages micro-instruction sequencing.
- **Output Register**: Temporary holding register for outputs.
- **Frame Buffer / Video Buffer**: Intermediate storage for pixel data.

## How to Run
- Open cpu.circ in Logisim Evolution (tested with v3.8.0+).
- Load opcode.txt into the ROM.
- Start the simulation and enable the clock.
- Watch instructions execute step by step - registers, ALU, memory, and displays will update as the program runs.

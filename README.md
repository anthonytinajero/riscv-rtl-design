# RISC-V Architecture & RTL Design

A hands-on project exploring RISC-V processor architecture,
digital logic, and register-transfer level (RTL) design using SystemVerilog.

## Overview

This repository documents my progress in learning computer architecture
and hardware design through the implementation of RISC-V CPU components.

As an Electrical Engineering student at the University of Houston,
I am developing a deeper understanding of how processors operate at
the register-transfer level (RTL).

My focus is on learning the fundamentals of digital hardware,
implementing individual processor components, and understanding how
these components interact within a CPU.

My long-term goal is to integrate these components into a functional
RISC-V processor.

## Project Background

This project follows the
[RISC-V FPGA Practice — Learner Course](https://github.com/daryl-888/RISCV_FPGA_Practice/tree/learner/course)
developed by [Daryl](https://github.com/daryl-888).

I am working through the structured exercises in the `learner/course`
branch to strengthen my understanding of SystemVerilog, RTL design,
and RISC-V processor architecture.

Rather than copying the entire learning repository, this repository
serves as a personal record of my progress. I add the files I work on
as I complete exercises, implement hardware components, and develop
my understanding of their functionality.

The objective is to document my hands-on learning experience while
building toward a complete processor implementation.

## Technologies & Concepts

**Hardware Description Language**
- SystemVerilog

**Hardware Design**
- Register-Transfer Level (RTL) Design
- Combinational Logic
- Sequential Logic
- Digital Circuit Design

**Computer Architecture**
- RISC-V Architecture
- Arithmetic Logic Units (ALU)
- Program Counters
- Instruction Memory
- Register Files

**Development**
- Git & GitHub
- Visual Studio Code

## Implementation Progress

|  Week | Focus | Status |
|-------|-------|--------|
|   01  | Arithmetic Logic Unit (ALU) | RTL Implemented |
|   02  | Program Counter, Instruction Memory & Register File | RTL Implemented |
|   03  | Instruction Decode & Execution | Next Up |
|   04  | Extended Single-Cycle CPU Functionality | Planned |
| 05–08 | Pipeline Development & Verification | Future Work |

Progress reflects implemented RTL modules, not necessarily
completed simulation or verification milestones.

---

## Week 01 — Arithmetic Logic Unit (ALU)

**File:** [alu.sv](rtl/common/alu.sv)

### Implementation

Developed a 32-bit Arithmetic Logic Unit using SystemVerilog.

The ALU performs arithmetic, logical, comparison, and shift operations
based on a control signal.

Implemented operations include:

| Operation | Function |
|-----------|----------|
| ADD | Addition |
| SUB | Subtraction |
| AND | Bitwise AND |
| OR | Bitwise OR |
| XOR | Bitwise XOR |
| SLT | Signed comparison |
| SLTU | Unsigned comparison |
| SLL | Logical left shift |
| SRL | Logical right shift |
| SRA | Arithmetic right shift |

### Concepts Learned

- How combinational logic is modeled using `always_comb`.
- How `case` statements select hardware operations.
- The difference between signed and unsigned arithmetic.
- How logical and arithmetic shifts operate on binary values.
- How control signals determine ALU behavior.
- How an ALU contributes to instruction execution within a processor.

This exercise helped establish my understanding of how arithmetic
and logical operations are implemented at the hardware level.

---

## Week 02 — Sequential Logic & Processor Components

### Program Counter (PC)

**File:** [pc.sv](rtl/common/pc.sv)

Implemented a 32-bit program counter using sequential logic.

The program counter stores the address associated with instruction
execution and updates its value on the rising edge of the clock.

Features:
- Clock-driven register updates.
- Synchronous reset.
- Enable-controlled updates.
- Nonblocking assignments for sequential logic.

**Key Takeaways**

- Understanding clock signals and rising-edge behavior.
- Learning the difference between combinational and sequential logic.
- Using `always_ff` to describe clocked hardware.
- Understanding the role of the program counter in instruction sequencing.

### Instruction Memory

**File:** [imem.sv](rtl/common/imem.sv)

Implemented an instruction memory module that provides instructions
based on an input memory address.

Features:
- 32-bit instruction output.
- Memory initialization.
- Instruction loading from a memory file.
- Address alignment checking.
- Address-range fault detection.

**Key Takeaways**

- Understanding how instructions are stored and accessed.
- Learning how memory addresses correspond to instruction locations.
- Handling invalid and misaligned instruction addresses.

### Register File

**File:** [regfile.sv](rtl/common/regfile.sv)

Implemented a register file for storing and retrieving processor data.

Features:
- 32 general-purpose 32-bit registers.
- Two asynchronous read ports.
- One synchronous write port.
- Synchronous reset.
- Protection of register `x0`.
- Configurable register bypass logic.

**Key Takeaways**

- Understanding how processor registers store data.
- Learning the differences between synchronous writes and
  asynchronous reads.
- Understanding register addressing and data movement.
- Learning why RISC-V register `x0` must always represent zero.

---

## Week 03 — Instruction Decode & Execution

**Status: Next Up**

The next stage focuses on connecting previously developed components
to begin executing arithmetic instructions.

### Planned Work

- Implement instruction decoding for supported RISC-V operations.
- Extract register addresses and instruction fields.
- Decode arithmetic operations using instruction control fields.
- Implement immediate extraction and sign extension.
- Connect the ALU to the execution stage.
- Begin integrating the program counter, register file, decoder,
  and execution logic into a single-cycle CPU.
- Verify arithmetic instruction execution using the course tests.

### Learning Objectives

The primary goal is to understand how a processor translates
a machine instruction into control signals and data operations.

This will provide the foundation for integrating individual
RTL modules into a functioning CPU datapath.

---

## Project Roadmap

The long-term objective is to progress from individual hardware
components to an integrated RISC-V processor.

### Phase 1 — RTL Fundamentals
- [x] Implement ALU operations.
- [x] Implement program counter.
- [x] Implement instruction memory.
- [x] Implement register file.

### Phase 2 — Single-Cycle Processor
- [ ] Implement instruction decoding.
- [ ] Develop execution-stage logic.
- [ ] Integrate components into a single-cycle CPU.
- [ ] Expand instruction support.
- [ ] Verify instruction execution.

### Phase 3 — Processor Pipelining
- [ ] Study the five-stage processor pipeline.
- [ ] Implement pipeline registers and stages.
- [ ] Understand data and control hazards.
- [ ] Implement forwarding and stall mechanisms.
- [ ] Verify pipelined instruction execution.

### Phase 4 — Final Integration
- [ ] Run architectural verification tests.
- [ ] Evaluate processor functionality.
- [ ] Explore FPGA implementation and validation.

---

## Project Goals

Through this project, I aim to:

1. Build a strong foundation in RTL design and SystemVerilog.
2. Understand the internal architecture of modern processors.
3. Gain hands-on experience developing digital hardware.
4. Develop practical hardware debugging and verification skills.
5. Progress toward designing and implementing a functional RISC-V CPU.

## Acknowledgments

This learning project is based on
[Daryl's RISC-V FPGA Practice repository](https://github.com/daryl-888/RISCV_FPGA_Practice/tree/learner/course).

Credit goes to Daryl for developing the structured course,
providing the learning materials, and offering mentorship
throughout the project.

This repository documents my personal implementations and
progress through the course.

---

**Project Status:** Active Development

**Current Milestone:** Week 03 — Instruction Decode & Execution

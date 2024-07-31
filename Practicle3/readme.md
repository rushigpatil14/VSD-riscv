# RISC-V Instruction Sets Overview

This document provides an overview of the RISC-V instruction set architecture (ISA) focusing on the R, I, S, B, U, and J instruction formats. Each format is briefly described along with an example for clarity.

## R-Type Instructions
R-type instructions are used for register-register operations.

**Format**: `opcode | rd | funct3 | rs1 | rs2 | funct7`

**Example**: `ADD rd, rs1, rs2`
- **ADD**: Adds the values in `rs1` and `rs2`, and stores the result in `rd`.
- `opcode`: Specifies the operation (e.g., 0110011 for integer register-register operations).
- `funct3` and `funct7`: Further specify the operation (e.g., 000 for ADD).

### Here are some examples of R-type instructions with their funct3 and funct7 values:

* ADD (Addition)

``` 
00f507b3  add	a5,a0,a5

Opcode: 0110011\
funct3: 000\
funct7: 0000000\
Binary Encoding: 1111 0101 0000 0111 1011 0011
```
* SUB (Subtraction)
```
40f70733   sub  a4,a4,a5

Opcode: 0110011\
funct3: 000\
funct7: 1000000\
Binary Encoding: 0100 0000 1111 0111 0000 0111 0011 0011
```
* AND (Bitwise AND)
```
014e7e33    and     t3,t3,s4

Opcode: 0110011
funct3: 111
funct7: 0000001
Binary Encoding: 0001 0100 1110 0111 1110 0011 0011
```
 * OR (Bitwise OR)
 ```
00c8e8b3       or      a7,a7,a2

Opcode: 0110011
funct3: 101
funct7: 0000000
Binary Encoding: 1100 1000 1110 1000 1011 0011
 ```
* XOR (Bitwise XOR)

```
00f44433       xor     s0,s0,a5

Opcode: 0110011
funct3: 100
funct7: 0000000
Binary Encoding: 1111 0100 0100 0100 0011 0011

```
 
## I-Type Instructions
I-type instructions are used for immediate operations, loads, and some ALU operations.

**Format**: `opcode | rd | funct3 | rs1 | imm[11:0]`

**Example**: `ADDI rd, rs1, imm`
- **ADDI**: Adds the value in `rs1` to the immediate `imm`, and stores the result in `rd`.
- `opcode`: Specifies the operation (e.g., 0010011 for immediate arithmetic operations).
- `funct3`: Specifies the operation type (e.g., 000 for ADDI).

## S-Type Instructions
S-type instructions are used for store operations.

**Format**: `opcode | imm[11:5] | funct3 | rs1 | rs2 | imm[4:0]`

**Example**: `SW rs2, imm(rs1)`
- **SW**: Stores the value in `rs2` to the memory address calculated by adding the immediate `imm` to the base address in `rs1`.
- `opcode`: Specifies the store operation (e.g., 0100011).
- `funct3`: Specifies the type of store (e.g., 010 for SW).

## B-Type Instructions
B-type instructions are used for conditional branches.

**Format**: `opcode | imm[12] | imm[10:5] | funct3 | rs1 | rs2 | imm[4:1] | imm[11]`

**Example**: `BEQ rs1, rs2, imm`
- **BEQ**: Branches to the address `PC + imm` if the values in `rs1` and `rs2` are equal.
- `opcode`: Specifies the branch operation (e.g., 1100011).
- `funct3`: Specifies the branch condition (e.g., 000 for BEQ).

## U-Type Instructions
U-type instructions are used for upper immediate operations.

**Format**: `opcode | rd | imm[31:12]`

**Example**: `LUI rd, imm`
- **LUI**: Loads the upper 20 bits of the immediate `imm` into `rd`.
- `opcode`: Specifies the operation (e.g., 0110111 for LUI).

## J-Type Instructions
J-type instructions are used for unconditional jumps.

**Format**: `opcode | rd | imm[20] | imm[10:1] | imm[11] | imm[19:12]`

**Example**: `JAL rd, imm`
- **JAL**: Jumps to the address `PC + imm` and stores the return address in `rd`.
- `opcode`: Specifies the jump operation (e.g., 1101111 for JAL).

## References
- [RISC-V International](https://riscv.org/wp-content/uploads/2019/12/riscv-spec-20191213.pdf)
- [RISC-V Instruction Sets Overview](https://devopedia.org/risc-v-instruction-sets)
- [RISC-V Instruction Format Explanation](https://seds.nl/notes/risc_v_instruction_format/)

For more details, refer to the official RISC-V specification documents available on the [RISC-V International website](https://riscv.org).


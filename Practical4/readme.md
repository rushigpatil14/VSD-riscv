# Main Components of RV32I Architecture:

## 1. Registers:

* 32 General Purpose Registers (x0 - x31)

* Program Counter (PC)

## 2. Arithmetic Logic Unit (ALU):

* Performs arithmetic and logical operations.
* Inputs: Two 32-bit operands (from registers or immediate values).
* Output: Result of the operation.

## 3. Instruction Memory:

* Stores the program instructions.
* Addressed by the Program Counter (PC).

## 4. Data Memory:

* Stores data for load/store operations.
* Accessed via load (LW) and store (SW) instructions.

## 5. Control Unit:

* Decodes the instruction.
* Generates control signals to direct the operation of other components.

## 6. Immediate Generator:

* Extracts and sign-extends immediate values from instructions.

## 7. Multiplexers (MUX):

* Select between different inputs based on control signals.
* Example: Selecting between register operand or immediate value for ALU input.

## 8. Branch Target Calculation:

* Computes the target address for branch instructions.

## 9. Jump Target Calculation:

* Computes the target address for jump instructions.

# RV32I Architecture Diagram


## Here is a step-by-step breakdown of how these components are connected and interact.

## 1] Program Counter (PC):

* Points to the current instruction in the Instruction Memory.
* Connected to the Instruction Memory to fetch the instruction.

## 2] Instruction Fetch:

* The instruction at the address in the PC is fetched from the Instruction Memory.

## 3] Instruction Decode:

* The fetched instruction is sent to the Control Unit.
* The Control Unit decodes the instruction and generates appropriate control signals.
* The instruction is also sent to the Immediate Generator, which extracts any immediate value.

## 4] Register File:

* Contains 32 general-purpose registers.
* Two source registers (rs1, rs2) are read based on the instruction.
* The destination register (rd) is specified for the result.

## 5] ALU Operations:

* The ALU performs the operation specified by the instruction.
* Inputs to the ALU can be register values or an immediate value (selected via a MUX).
* The result is sent back to the Register File or Data Memory.

## 6] Data Memory Access:

* For load (LW) and store (SW) instructions, Data Memory is accessed.
* The address for Data Memory is calculated by the ALU.
* Data is loaded from or stored to Data Memory based on the instruction.

## 7] PC Update:

* The PC is updated to point to the next instruction.
* For branch and jump instructions, the target address is calculated and loaded into the PC
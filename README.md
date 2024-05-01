# 8-Bit Microprocessor Project

This project implements an 8-bit microprocessor using Logisim Evolution 3.8.0. The microprocessor features separate address and data buses, three core registers (R0, R1, R2), an Arithmetic Logic Unit (ALU) with addition and logical AND operations, and various control signals for enabling clock cycles and other functionalities.

## Features

- Separate 8-bit address and data buses
- Three core registers: R0, R1, R2
- ALU with addition and logical AND operations
- Control signals for enabling clock cycles and other functionalities

## Control Signals

The microprocessor utilizes the following control signals:

- E0: RAM Output Enable
- E1: RAM Input Enable
- E2: Clock Enable for Program Counter (PC)
- E3: Clock Enable for R0
- E4: Clock Enable for R1
- E5: Clock Enable for R2
- E6: Clock Enable for Instruction Register (IR)
- E7: Clock Enable for RAM
- E8: Load/Count for Program Counter (PC)
- E9: Clock Enable for Instruction Counter (IC)
- E10: Reset for Instruction Counter (IC)
- E11: Enable for ADD operation
- E12: Enable for AND operation

## Instructions

The microprocessor supports the following instructions with suitable 8-bit opcodes:

1. **JUMP**: Jump to a specified address
2. **Read from RAM into R0**: Value is read from RAM and stored in R0
3. **Read from RAM into R1**: Value is read from RAM and stored in R1
4. **Write to RAM from R2**: Value from R2 is written to a specified address in RAM
5. **ADD R0, R1**: Addition operation between R0 and R1, result stored in R2
6. **AND R0, R1**: Logical AND operation between R0 and R1, result stored in R2
7. **Copy R2 into R1**: Contents of R2 are copied into R1
8. **Copy R2 into R0**: Contents of R2 are copied into R0

## Sample Program

A sample program is provided below, along with step-by-step execution:

```
Addr: Instruction
-------------------
0x00: MOV R0, val1    ; Load value from RAM into R0 (val1 is in RAM just after opcode)
0x02: MOV R1, val2    ; Load value from RAM into R1 (val2 is in RAM just after opcode)
0x04: ADD R0, R1      ; Add R0 and R1, store result in R2
0x05: MOV @addr1, R2  ; Write value from R2 to RAM at address @addr1
0x07: COPY R0, R2     ; Copy contents of R0 to R2
0x08: MOV R1, val3    ; Load value from RAM into R1 (val3 is in RAM just after opcode)
0x0A: AND R0, R1      ; Perform logical AND between R0 and R1, store result in R2
0x0B: MOV @addr2, R2  ; Write value from R2 to RAM at address @addr2
0x0D: JUMP 0x00       ; Jump to address 0x00
```

## Execution Steps

1. Load value from RAM into R0.
2. Load value from RAM into R1.
3. Add contents of R0 and R1, store result in R2.
4. Write value from R2 to RAM at specified address.
5. Copy contents of R0 to R2.
6. Load value from RAM into R1.
7. Perform logical AND between R0 and R1, store result in R2.
8. Write value from R2 to RAM at specified address.
9. Jump back to address 0x00 to repeat the process.

## Project Files

This repository contains the Logisim project file (.circ) for the 8-bit microprocessor implementation.

Feel free to explore and use this project for educational purposes or as a reference for building similar microprocessor systems.

For any questions or suggestions, please open an issue or reach out to the project maintainer.

# Notes on Registers (ARMv7-M)

## Overview
- r0-r12: general purpose registers
- r13: stack pointer
- r14: link register
- r15: program counter
- xPSR: status registers
- control registers
- mask registers

## Stack Pointer
The ARMv7-M profile has two stacks(?)
- main stack (MSP)
- process stack (PSP)

## xPSR: Program Status Registers
The PSR is composed of three sub-registers.
- APSR: contains flags related to conditionals
- IPSR: contains exception number
- EPSR: contains execution mode

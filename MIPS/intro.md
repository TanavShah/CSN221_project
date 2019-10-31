### Introduction

**MIPS** is a ‘typical’ RISC architecture: it has a simple and regular instruction set, only one memory addressing mode (base plus displacement) and instructions are of fixed size (32 bit).

MIPS is a register-register (or Load/Store), three address machine.
- register-register means that all operations are performed in registers. Access to memory is provided
only by load and store instructions. There is no arithmetic or logic instruction that has part of operands
in registers and part in memory. Operands for such instructions are always in registers.
- three-address means that all arithmetic and logic instructions have three operands, one destination register which is always listed immediately after the instruction name, and two source registers. add
$t0, $t1, $t2 adds source registers $t1 and $t2 and stores the result in the destination register
$t0.

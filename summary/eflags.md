A flag is a flip-flop that controls certain EU activities or signals a situation carried on by the execution of an instruction. Thirteen flags are present in the EFLAG register. EFLAGS, a 32-bit register, operates as the flags register. FLAGS is the name given to the low-order 16 bits of EFLAGS and can be treated as a unit. This feature is useful for running 8086 and 80286 programs because this component of EFLAGS is similar to the FLAGS register of the 8086 and the 80286.

These flags can be categorized into three different groups.

1. **Status flags:** These flags reflect the state of a particular program.
2. **Control flags:** These flags directly affect the operation of a few instructions.
3. **System flags:** These flags reflect the current status of the machine and are usually used by the operating systems than by application programs.  
     

![](https://media.geeksforgeeks.org/wp-content/uploads/20220816170724/EFLAGSregistersof80386microprocessor-660x330.jpg)

EFLAGS register

### Status Flags: 

The status flags are _CF (Carry Flag) PF (Parity Flag ), AF (Auxiliary carry Flag) 2F (Zero Flag). SF (Sign Flag), and OF (Overflow Flag)_. These flags indicate some conditions produced by the execution of arithmetic or logical instructions. These flags provide necessary information for arithmetic and logical control decisions.

1. **CF (Carry flag)**: This bit is set by arithmetic instructions that generate either a carry or a borrow. This bit can also be set, cleared, or inverted with the STC, CLC, or CMC instructions, respectively Carry flag is also used in shift and rotate instructions to contain the bit shifted or rotated out of the register.
2. **PF (Parity flag):** The parity bit is set by most instructions if the least significant 8-bit of the result contains an even number of one’s
3. **AF (Auxiliary carry flag):** This bit is set when there is a carry or borrow after a nibble addition or subtraction, respectively. The programmer can’t access this bit directly, but this bit is internally used for BCD arithmetic.
4. **ZF (Zero flag):** Zero flags is set to 1 if the result of an operation is zero
5. **SF (Sign flag):** The signed numbers are represented by a combination of sign and magnitude The Most Significant Bit (MSB) indicates a sign of the number. For a negative number, MSB is 1. The sign flag is set to 1 if the result of an operation is negative (MSB=1).
6. **OF (Overflow flag):** In 2’s complemented arithmetic, the most significant bit is used to represent a sign, and the remaining bits are used to represent the magnitude of a number. This flag is set if the result of a signed operation is too large to fit in the number of bits available (7-bits for an 8-bit number) to represent it.  
    For example, if you add the 8-bit signed number 01110110 (+118 decimal) and the 8-bit signed number 00110110 (+54 decimal). The result will be 10101100 (+172 decimal), which is the correct binary result. But in this case, it is too large to fit in the 7-bits allowed for the magnitude in an 8-bit signed number. The overflow flag will be set after this operation to indicate that the result of the addition has overflowed into the sign bit.

### Control Flags:

1. **DF (Direction flag):** The direction flag controls the direction of string operations. When the D flag is cleared these operations process strings from low memory up to high memory. This means that offset pointers (usually SI and DI) are incremented by 1 after each operation in the string instructions when the D flag is cleared. If the D flag is set, then SI and DI are decremented by 1 after each operation to process strings from high to low memory

### System Flags:

1. **1. VM (Virtual Memory) flag:** This flag indicates the operating mode of 80386. When the VM flag is set, 80386 switches from protected mode to virtual 8086 modes.
2. **R (Resume) flag/Restart flag:** This flag, when set allows selective masking of some exceptions at the time of debugging
3. **NT (Nested flag):** This flag is set when one system task invokes another task
4. **IOPL (VO Privilege level):** The two bits in the IOPL are used by the processor and the operating system to determine your application’s access to I/O facilities. It holds a privilege level, from 0 to 3, at which the current code is running in order to execute any I/O-related instruction.
5. **IF (Interrupt Flag):** When the interrupt flag is set, the 80386 recognizes and handles external hardware interrupts on its INTR pin. If the interrupt flag is cleared, 80386 ignores any inputs on this pin. The IF flag is set and cleared with the STI and CLI instructions, respectively.
6. **TF (Trap Flag):** Trap flag allows users to single-step through programs. When an 80386 detects that this flag is set, it executes one instruction and then automatically generates an internal exception 1. After servicing the exception, the processor executes the next instruction and repeats the process. This single stepping continues until the program code resets this flag for debugging programs’ single-step facility is used.
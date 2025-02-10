base 10 = 10x1 + [10x0] x 3

8bits - 1byte

hexidecimal = 1-10 10-16 = A_F

0100, 0110
4      ,6

x86 registers 
0000, 0000, 0000, 0000,
__-----EAX--------------

---------AX- lower 16bits
        ---=======Ah,higher 8bits
                 AL lower 16bits

eax
Extended accumulator, automatically used by multiplication and division instructions
**ebx**
General purpose
**ecx**
Used as a loop counter by the CPU
**edx**
General purpose
**esi**
High speed memory transfer
**edi**
High speed memory transfer
**ebp**
Used to reference function parameters and local variables on the stack
**esp**
A pointer to the current stack address

DB = 1byte 8bits
DW = 2bytes 16bits
DD = 4bytes 32bits
DQ = 8bytes 64bits
DT = 10bytes 80bits

32 ,16, 8, 4, 2,1
![[Pasted image 20250206071919.png]]



![[250124-1001-08.png]]


### Example in Code:

In C or C++:

- **Signed integer**:
    
    c
    
    CopyEdit
    
    `int a = -5; // signed integer`
    
- **Unsigned integer**:
    
    c
    
    CopyEdit
    
    `unsigned int b = 5; // unsigned integer`
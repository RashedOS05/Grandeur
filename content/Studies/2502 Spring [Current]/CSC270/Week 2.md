---
publish: true
created: 2026-02-01T15:24:54.872+03:00
modified: 2026-05-27T16:31:08.500+03:00
---

#school

## Code cannot be ended in Assembly

has to be END : JAL END causing it to be stuck in an infinite loop on the same line ON PURPOSE

#### Prefix 0x means Hexadecimal number

#### LW: Load Word, SW: Save Word (Memory I/O)

No direct equivalent in Java

### Manipulation of variables cannot be performed until they're moved from the memory into the registers

\`ADDI x5, x0, 0x1000 (initialize x5 with the hexadecimal value
ADDI x6, x0, 1
ADDI x7, x0, 6

LOOP:               SW    x6, 0(x5)
ADDI x6, x6, 1
ADDI x5, x5, 4
BLT x6, x7, LOOP

_JAVA EQUIVALENT_:
int x\[] = {1,2,3,4,5};

ADDI x5, x0, 0x1000 ; a
ADDI x6, x0, x0 ; i
ADDI x7, x0, 5 ; limit
ADDI x2, x0, 0 ; sum

LOOP2:               LW    x8, 0(x5)
ADD x2, x2, x8
ADDI x6, x6, 1
ADDI x5, x5, 4
BLT x6, x7, LOOP2
END: JAL END

_JAVA EQUIVALENT:_
int sum = 0;
for (int i-0; i < 5; i++)
sum=sum + a\[i];

### Functions shouldn't change the registers being used

The registers must be put back after the function logic is done to preserve them

#### Stack: LIFO

New elements are added to lower address in the list unlike other data structures (first element is saved in the highest address etc)

### Calling Functions in Assembly

\`main:
ADDI x10, x0, 7
jal x1, fun
end: j end

`fun:
	 addi x2, x2, -12
	 sw x1, 8(x2)
	 sw x8, 4(x2)
	 sw x0, 0(x2)`

```
 addi x8, x10, 2
 div x8, x8, 5
 
 lw  x0, 0(x2)
 lw  x8, 4(x2)
 lw. x1, 8(x2)
 addi x2, x2, 12
 
 jalr x0, 0(x1)`
```

---
publish: true
created: 2026-05-10T15:09:21.678+03:00
modified: 2026-05-27T16:31:08.535+03:00
tags:
  - school
---

Assignment questions: 1.4 3.4, 4.4 4.5 don't solve

CSC270 Test Ch4 & 5
Chapter 4 (excluding single-cycle architecture) and Chapter 5 (To associative caches).

## Pipelining

Overlapping execution to speed up processes
Doing things in pararell improves the performance

### General Speedup Calculation:

$Before/After$

### Pipelining Stages (The sequence of tasks the CPU does for every instruction):

1. **IF:** fetch the instruction from the memory
2. **ID:** Instruction decode & register read (figure out what it does)
3. **EX:** Execute operation or calculate address (do the math)
4. **MEM:** Access memory operand (load/store instructions)
5. **WB:** Write result back to register

### Pipelined Speedup Calculation

Time between instructions<sub>pipelined</sub> = Time between instructions<sub> non-pipelined</sub> / Number of stages

### Hazards

\*Situations that prevent starting the next instruction in the next cycle

- Structure hazards
  A required resource is busy
- Data hazard
  Need to wait for previous instruction to complete its data read/write
- Control hazard
  Deciding on control action depends on previous instruction
  ![[Studies/2502 Spring [Current]/CSC270/Media/Pasted image 20260510212108.png|804]]

## Cache

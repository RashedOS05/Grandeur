---
publish: true
created: 2025-11-29T21:41:24.861+03:00
modified: 2026-05-27T17:00:03.198+03:00
---

| **State** | **id** | **+** | **\$**   | **S** | **D** | **E** | **F** |
| --------- | ------ | ----- | ------- | ----- | ----- | ----- | ----- |
| **0**     | S4     |       |         | 1     | 2     | 3     |       |
| **1**     |        |       | **Acc** |       |       |       |       |
| **2**     |        | R1    | R1      |       |       |       |       |
| **3**     |        | S5    | R2      |       |       |       | 6     |
| **4**     |        | R4    | R4      |       |       |       |       |
| **5**     | S4     |       |         |       |       |       | 6     |
| **6**     |        | R3    | R3      |       |       |       |       |

| **Stack**      | **Input**      | **Action**                          |
| -------------- | -------------- | ----------------------------------- |
| 0              | id + id + id $| Shift (S4)                          |
| 0 id 4         | + id + id$    | Reduce by (F → id) → goto(0,F)=3    |
| 0 F 3          | + id + id $   | Reduce by (E → F) → goto(0,E)=3     |
| 0 E 3          | + id + id$    | Shift (S5)                          |
| 0 E 3 + 5      | id + id $     | Shift (S4)                          |
| 0 E 3 + 5 id 4 | + id$         | Reduce by (F → id) → goto(5,F)=6    |
| 0 E 3 + 5 F 6  | + id $        | Reduce by (E → E + F) → goto(0,E)=3 |
| 0 E 3          | + id$         | Shift (S5)                          |
| 0 E 3 + 5      | id $          | Shift (S4)                          |
| 0 E 3 + 5 id 4 |$              | Reduce by (F → id) → goto(5,F)=6    |
| 0 E 3 + 5 F 6  | $             | Reduce by (E → E + F) → goto(0,E)=3 |
| 0 E 3          |$              | Reduce by (D → E) → goto(0,D)=2     |
| 0 D 2          | $             | Reduce by (S → D) → goto(0,S)=1     |
| 0 S 1          |$              | **Accept**                          |

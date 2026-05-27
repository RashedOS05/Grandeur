---
publish: true
created: 2025-10-06T11:14:27.066+03:00
modified: 2026-05-27T17:00:04.771+03:00
---

## Complements of Binary Numbers

**Only for negative**
its goal is to convert a number to positive to be able to work with it

#### First complement: flipping the bits: 0's to 1's and 1's to 0's

<font color="#00b0f0">Ex: 11001011 -> 00110100</font>

#### Second complement: adding one to the LSB

<font color="#00b0f0">Ex: 11001011 -> 00110100 -> 00110101</font>

#### Sign-magnitude:

`MSB` is reserved for the sign of the numbers. Deals with both negative and positive numbers.
7 bits for the number itself, and 1 for the sign of the number (adds up to 8-bit)

#### <font color="#ffc000">Getting different results for the different methods is normal; every system uses a different way to represent the same numbers</font>

<hr>

### Assignment:

1.

1101 + 1010
10111 + 01101
2\.
1101 - 0100
1001 - 0111
3\.
110 \* 111
1100 / 011

<hr>
## Signed Numbers Arithmetic Operations

##### <font color="#ffc000">Overflow Condition</font>

Occurs when:

- Both numbers added are positive
- Both numbers added are negative
  is indicated when the sign bit of the result is different than the sign bit of the added numbers

##### <font color="#ffc000">Subtraction</font>

There's no subtraction in signed. We add in a special way instead.

#### <font color="#ffc000">Number System</font>

| Type        | Base | Digits             |
| ----------- | ---- | ------------------ |
| Binary      | 2    | 0 :LiArrowRight: 1 |
| Decimal     | 10   | 0 :LiArrowRight: 9 |
| Hexadecimal | 16   | 0 :LiArrowRight: F |

##### <font color="#00b0f0">Hexadecimals Counting:</font>

0 through 9 then A through F

###### Ex:

E = 14, 1F = 20

#### <font color="#ffc000">Binary-to-Hexadecimal Conversion</font>

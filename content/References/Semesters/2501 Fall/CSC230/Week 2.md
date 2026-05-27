---
publish: true
created: 2025-09-29T11:15:25.955+03:00
modified: 2026-05-27T17:00:04.765+03:00
---

# Chapter 1: Duty cycle is the percentage when the signal was high

## Digital vs. analog

analog represents the fractions in between and offers a wider range of frequencies
digital is more immune to noise (distortion and interferences), and is more flexible and scalable, and can be stored and transferred without loss.

## Quantization

The process of converting a continuous analog signal to a discrete digital values.

# Chapter 2

## Digits

### every digit has its own weight

Ex: 23 = (2x10<sup>0</sup>)+(3x10<sup>0</sup>)=20+3=23 <font color="#4bacc6">For integers: 10 to the power of the digits order, starting from zero.
Case: 421: 1 is 10<sup>0</sup>, 2 is 10<sup>1</sup>, etc...
Whereas decimals start from 10<sup>-1</sup>, and goes down as you go to the right.
Case: 0.21: 2 is 10 pow(-1), and 1 is 10<sup>-2</sup></font>

###### HW: Determine the value of each digit in 67.924?

## Binary Numbers

This actually shares some notes from [CSC300's truth table systematic insertion!](obsidian://open?vault=Workspace\&file=School%2FCurrent%2FCSC300%2FWeek%202)

### How it compares:

<font color="#00b0f0">Binary can only be 0's and 1's, so the base number will be 2, and the power of it will depend on the digits placement within the table:</font>

###### Ex:

_-first column will be 2<sup>0</sup>= 1
alternate the binary every 1 row
-second column will be 2<sup>1</sup>= 2
alternate the binary every 2 rows
etc..._

###### Table Demonstration:

| Decimal Number | Binary Number | Binary Number | Binary Number | Binary Number |
| -------------- | ------------- | ------------- | ------------- | ------------- |
| 1              | 0             | 0             | 0             | 0             |
| 2              | 0             | 0             | 0             | 1             |
| 3              | 0             | 0             | 1             | 0             |
| 4              | 0             | 0             | 1             | 1             |
| 5              | 0             | 1             | 0             | 0             |
| 6              | 0             | 1             | 0             | 1             |
| 7              | 0             | 1             | 1             | 0             |
| 8              | 0             | 1             | 1             | 1             |

### <sup>MSB-></sup>110111<sup>LSB</sup>.<sup>MSB-></sup>1101<sup>LSB</sup>

### Converting Binary Numbers

#### Decimal Base: 10

#### Binary Base: 2

#### Case: convert 1101101 to decimals:

**1101101:** 2<sup>6</sup>+2<sup>5</sup>+2<sup>4</sup>+2<sup>3</sup>+2<sup>2</sup>+2<sup>1</sup>+2<sup>0</sup>

#### 0.1011 binary to decimal

2<sup>-1</sup>+2<sup>-3</sup>+2<sup>-4</sup> = 0.6875

## Decimal-to-Binary Conversion

### Method 1: Sum of Weights

9 = 8+ 1 = 2<sup>3</sup>  +  2<sup>0</sup> (the rest are missing so they're replaced with zero)
\= 1001

#### Homework: Convert 125 to binary

125 = 64 + 32 + 16 + 8 + 4 + 1
2<sup>6</sup>+2<sup>5</sup>+2<sup>4</sup>+2<sup>3</sup>+2<sup>2</sup>+2<sup>0</sup> (2<sup>1</sup> is missing so it's subsituted with zero)

###### Binary = 1111101

#### Application on Decimals

0.45 = 0.25 + 0.125 + 0.0625 etc...

### Method 2: Repeated Divsion

Binary for 125:
125/2 = 62: remainder = 1 (LSB)
62/2 = 31: remainder = 0
31/2 = 15: remainder = 1
15/2 = 7: remainder = 1
7/2 = 3: remainder = 1
3/2 = 1: remainder = 1
1/2 = 0: remainder = 1 (MSB)

###### Binary = 1111101 (same as Method 1)

#### Application on Decimals

###### Differences:

**-Division becomes multiplication
-Instead of taking the remainder, we take the total.
-We keep going until the fractional part is all 0's (like 1.00).
-MSB/LSB are inverted (the signficance drops as you go to the right).
-If the result is 1.n, n is the number you procceed the calculations with, and the 1 goes into the binary number**

### Exercise using Method 1:

45.5 = 32 + 8 + 4 + 1 + 0.5
Weight: 2<sup>4</sup>
0.375

### Using Method 2:

## Binary Addition

0 + 0 = 0
0 + 1 = 1
1 + 0 = 1
1 + 1 = 0 and carries 1 (just like decimals)

#### Review Binary Addition

needs to be practiced on paper/tablet

## Binary Subtraction

0 - 0 = 0
1 - 0 = 1
1 -1 = 0
0 - 1 = 1 \*\*and a borrow of 1

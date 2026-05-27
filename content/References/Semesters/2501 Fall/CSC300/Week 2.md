---
publish: true
created: 2025-09-29T09:48:12.689+03:00
modified: 2026-05-27T17:00:04.170+03:00
---

# <font color="#4bacc6">Truth Table for implication:</font>

| p   | q   | p --> q |
| --- | --- | ------- |
| T   | T   | T       |
| T   | F   | F       |
| F   | T   | T       |
| F   | F   | T       |

### <font color="#ffc000">If the consequence happens, but the premise doesn't, the implication truth value is</font><font color="#ffff00"> still true!</font>

#### <font color="#00b050">Demonstration: </font>

p: if you get 100%
q: I will give you an A
if p is true and q is false, p->q is `false`
if p is false and q is true, p->q is <font color="#ffc000">still</font> `true`(he was feeling generous so you still got an A or whatever)

## Converse, Contrapositive, and Inverse

### "<font color="#ffc000">It raining is a sufficient condition</font> <font color="#4bacc6">for my not going to town.</font>"

#### Converse: <font color="#4bacc6">If I'm not going to town</font>, <font color="#ffc000">then it's raining.</font> (swap the conditions order)

#### Inverse: <font color="#ffc000">If it's not raining,</font><font color="#4bacc6"> then I will go to town</font> (negate both of the conditions)

#### Contrapositive: <font color="#4bacc6">If I go to town</font>, <font color="#ffc000">then it's not raining</font> (swap the conditions order and negate both of them)

## Biconditionals: p ⇔ q

### Truth Table for Biconditionals:

| p   | q   | p⇔ q |
| --- | --- | ---- |
| T   | T   | T    |
| F   | T   | F    |
| T   | F   | F    |
| F   | F   | T    |
|     |     |      |

### What makes it different than &&?

Both of them being `False` actually returns `True`.

## Constructing a truth table

Calculating rows: 2 (cuz either True or False) to the power of propositions.

### <font color="#4bacc6">Ex: p V q -> r</font>

2 to the power of 3 = 8
first column: 8/2 = 4 T/F
second column = 4/2 = 2 T/F
third column = 2/2 = 1 T/F

### <font color="#4bacc6">What does this mean?</font>

\*\*This decides the truth table insertion in a systematic manner (crazy!)

### <font color="#4bacc6">Demonstration:</font>\*\*

| <font color="#4bacc6">p</font> | <font color="#4bacc6">q</font> | <font color="#4bacc6">r</font> |
| ------------------------------ | ------------------------------ | ------------------------------ |
| T                              | T                              | T                              |
| T                              | T                              | F                              |
| T                              | F                              | T                              |
| T                              | F                              | F                              |
| F                              | T                              | T                              |
| F                              | T                              | F                              |
| F                              | F                              | T                              |
| F                              | F                              | F                              |
|                                |                                |                                |

#### <font color="#ffc000">Notice the pattern in each column</font>

| p   | q   | r   | ¬r  | pVq | pVq -> ¬ r |
| --- | --- | --- | --- | --- | ---------- |
| T   | T   | T   | F   | T   | F          |
| T   | T   | F   | T   | T   | T          |
| T   | F   | T   | F   | T   | F          |
| T   | F   | F   | T   | T   | T          |
| F   | T   | T   | F   | T   | F          |
| F   | T   | F   | T   | T   | T          |
| F   | F   | T   | F   | F   | T          |
| F   | F   | F   | T   | F   | T          |
|     |     |     |     |     |            |

## Precedence of Logical Operators

**¬** > **∧** > **∨** > **⇒** > **⇔**

## Practice

#### \*"You can access the Internet from campus only if you are a CS major or you are not a freshman."

Internet from campus = p
CS major = q
freshman = r

#### <font color="#ffc000"> p ⇒ (q∨¬r)</font>

## Proposition Types

#### Tautology propositions: always `true`

**Ex: p ∨ ¬p**

#### Contradiction proposition: always `false`

**Ex: p ∧ ¬p**

#### Contingency proposition: neither of the above

###### p and q are logically equivalent: if p ⇔ q is a tautology

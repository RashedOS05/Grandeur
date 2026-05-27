---
publish: true
created: 2026-02-04T15:37:30.504+03:00
modified: 2026-05-27T16:31:08.302+03:00
---

# Correctedness

## Knapsack Problem:

Imagine you have a collection of numbers, let's call this set S (e.g., S = {s₁, s₂, ..., sₙ}). You also have a specific target total, T. The challenge is to find if you can pick some numbers from set S that add up to exactly T.

#### 1: "First Available" Strategy

Easily denied by a counter-example:
Assume T=20
S = {19, 10, 10}
==The algorithm will pick 19, instead of 10 and 10; the correct answer==

#### 2: "Smallest First" Strategy

Also denied:
Assume T= 12
S = {1,3,9}
==Will pick 1 then 3 instead of filling the exact sum==

#### 3: "Biggest First" Strategy

==Denied using the same example used to counter-example Strat No. 1==

# Efficiency

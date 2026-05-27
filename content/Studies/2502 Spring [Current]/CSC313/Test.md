---
publish: true
created: 2026-04-06T14:12:26.266+03:00
modified: 2026-05-27T16:31:08.344+03:00
---

## Efficiency Table:

| Notation   | Name         | Example       |
| ---------- | ------------ | ------------- |
| O(1)       | Constant     | Array access  |
| O(log n)   | Logarithmic  | Binary search |
| O(n)       | Linear       | Linear scan   |
| O(n log n) | Linearithmic | Merge sort    |
| O(n²)      | Quadratic    | Bubble sort   |

## Hashtables & Dicts:

|Structure|Search|Insert|Delete|
|---|---|---|---|
|Unsorted array|O(n)|O(1)|O(n)|
|Sorted array|O(log n)|O(n)|O(n)|
|Balanced BST|O(log n)|O(log n)|O(log n)|
|Hash Table|O(1) avg|O(1) avg|O(1) avg|

### Collision:

When two hash keys refer to the same slot:
Handled through:

#### Open Addressing:

- probe for the next empty slot (linear probing, quadratic probing) aka searching

#### Chaining:

- each slot holds a linked list. Search is O(1 + load factor α), where α = n/m

# Heapsort

Heap: sorted binary tree
Heapmax: parent value > child value

**Key insight:** Guaranteed O(n log n) always, in-place. But slower in practice than quicksort due to cache behavior. Building the heap is O(n), not O(n log n)

# Sorting Comparison:

| Algorithm                                    | Best case  | Average case | Worst case | Space | In-place? | Stable? | Key weakness                            |
| -------------------------------------------- | ---------- | ------------ | ---------- | ----- | --------- | ------- | --------------------------------------- |
| Bubble sort<br><br>swap adjacent pairs       | O(n)       | O(n²)        | O(n²)      | O(1)  | yes       | yes     | Very slow, mostly academic              |
| Insertion sort<br><br>build sorted left side | O(n)       | O(n²)        | O(n²)      | O(1)  | yes       | yes     | Slow on large unsorted arrays           |
| Selection sort<br><br>find min, place it     | O(n²)      | O(n²)        | O(n²)      | O(1)  | yes       | no      | Always O(n²), no best case              |
| Heap sort<br><br>max-heap + extract          | O(n log n) | O(n log n)   | O(n log n) | O(1)  | yes       | no      | Poor cache behavior, slower in practice |
| Merge sort<br><br>divide, sort, merge        | O(n log n) | O(n log n)   | O(n log n) | O(n)  | no        | yes     | Needs O(n) extra memory                 |

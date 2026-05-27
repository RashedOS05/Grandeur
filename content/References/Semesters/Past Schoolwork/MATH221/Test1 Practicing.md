---
publish: true
created: 2025-03-12T03:35:10.186+03:00
modified: 2026-05-27T16:59:56.036+03:00
---

mean is متوسط الحسابي
median is الوسيط divided by its count (by 2 if it’s two numbers)
mode is المنوال
range is المدى
Trimmed mean: after sorting the data remove 25% from left and 25% from the right then do المتوسط الحسابي for the remaining data
Variance: $s^2 = \frac{\sum x_i^2 - \frac{(\sum x_i)^2}{n}}{n-1}$
where ( x i ) represents each data point
Deviance is the square root of Variance

**A ∩ B** the probability of A and B occurring together at the same time
Formula: **P(A∩B)=P(A∣B)⋅P(B)**
A ∣ B is A occurring given that B has occurred (| is given)
$P(A \mid B) = \frac{P(A \cap B)}{P(B)}$
Venn Diagram is the overlapping circles thingy
P(A ∩ B′)=P(A)−P(A ∩ B) (which excludes B)
P(A′ ∩  B′)=1−P(A ∪ B)
P(A ∪ B) **either event A occurs, or event B occurs, or both occur**.
The union includes all outcomes that belong to **at least one** of the events.
**P(A ∪ B)=P(A) + P(B) − P(A ∩ B)**
^^ why do we subtract (A ∩ B)? to get rid of the duplicate values from A and B overlapping
$P(B' \mid A) = \frac{P(A  \cap  B')}{P(A)}$
**Checking for Independence**:
If P(A∣B)=P(A)P(A∣B)=P(A), then A and B are independent.
$P(A' \cup B) = P(A') + P(B) - P(A' \cap B)$
P(random)= total data / the data part given
**key: either or is mentioned: most likely a union**

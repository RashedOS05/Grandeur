---
publish: true
created: 2025-10-05T11:24:42.584+03:00
modified: 2026-05-27T17:00:03.839+03:00
---

## Key Logical Equivalences

###### A way to prove equivalency besides using truth tables

###### **∧** and **∨** are negators of each other

#### Identity Laws:

$p ∧ T ≡ p$  and $p ∨ F ≡ p$

#### Domination Laws:

$p ∨ T ≡ T$  and  $p ∧ F ≡ F$

##### <font color="#00b0f0">demonstration:</font>

`True` is dominant in `or` statements (you just need one `True` for the whole thing to return `True`)

#### Idempotent Laws:

$p ∨ p ≡ p$  and  $p ∧ p ≡ p$

#### Double Negation Laws:

$¬ (¬ p) ≡ p$

##### <font color="#00b0f0">demonstration:</font>

negating a negation of a proposition gives back the proposition

#### Negation Laws

$p∨ ¬ p ≡ T$ and $p∧ ¬ p ≡ F$

##### <font color="#00b0f0">demonstration:</font>

something `or` the lack of it will always return `True`
something `and` the lack of it will always return `False`

#### Commutative Laws:

$p∨q ≡ q∨p$ and $p∧q ≡ q∧p$

##### <font color="#00b0f0">demonstration:</font>

order doesn't matter

#### Associative Laws:

#### Distributive Laws:

$(p∨q(q∧r)) ≡ (p∨q)∧(q∨r)$
$(p∧q(q∨r)) ≡ (p∧q)∨(q∧r)$

#### Absorption Laws:

# Predicate Logic vs Propositional

Predicate logic can have `multiple` truth values
Ex: Let x + y = z. be denoted by  R(x,y,z) where U for all three is integers
4 + 3 = 7 -> T
1 + -2 = 5 -> F

### Quantifier Symbols:

∀ = for all
∃ = there is at least one
If ∀ is `True`, ∃ is definitely \`True

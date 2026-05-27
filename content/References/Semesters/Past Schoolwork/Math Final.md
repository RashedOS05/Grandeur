---
publish: true
created: 2024-12-29T11:49:12.426+03:00
modified: 2026-05-27T16:59:55.644+03:00
---

Let’s solve **Question 1** step by step, explaining each limit evaluation clearly.

---

### **Question 1: Limits**

#### a. $\lim_{{x \to +\infty}} \frac{{x^3 + 2x^2 - x}}{{x^4 - 5x}}$

**Step 1: Analyze the dominant terms**\
For large $x$, the dominant term in the numerator is $x^3$, and in the denominator, it is $x^4$. The other terms become negligible as $x \to \infty$.

**Step 2: Divide numerator and denominator by the highest power of $x$ in the denominator ($x^4$):**

$\frac{{x^3 + 2x^2 - x}}{{x^4 - 5x}} = \frac{{\frac{x^3}{x^4} + \frac{2x^2}{x^4} - \frac{x}{x^4}}}{{\frac{x^4}{x^4} - \frac{5x}{x^4}}} = \frac{{\frac{1}{x} + \frac{2}{x^2} - \frac{1}{x^3}}}{{1 - \frac{5}{x^3}}}.$

**Step 3: Simplify as $x \to +\infty$:**

$\frac{{\frac{1}{x} + \frac{2}{x^2} - \frac{1}{x^3}}}{{1 - \frac{5}{x^3}}} \to \frac{{0 + 0 - 0}}{{1 - 0}} = 0.$

**Final Answer**:

$\lim_{{x \to +\infty}} \frac{{x^3 + 2x^2 - x}}{{x^4 - 5x}} = 0.$

---

#### b. $\lim_{{x \to 3^+}} \frac{{2x - 6}}{{\ln(x^2 - 8)}}.$

**Step 1: Analyze the numerator and denominator as $(x \to 3^+)$:**

- **Numerator:** $(2x - 6) approaches (2(3) - 6 = 0).$
- **Denominator:** $(\ln(x^2 - 8))$ approaches $(\ln(3^2 - 8) = \ln(1) = 0).$

This results in an indeterminate form $(\frac{0}{0}).$

**Step 2: Apply L'Hôpital's Rule:**

Since we have an indeterminate form, we can apply L'Hôpital's Rule, which involves differentiating the numerator and the denominator:

- **Derivative of the numerator:** $(\frac{d}{dx}(2x - 6) = 2)$.
- **Derivative of the denominator:** $(\frac{d}{dx}(\ln(x^2 - 8)) = \frac{1}{x^2 - 8} \cdot 2x = \frac{2x}{x^2 - 8})$.

**Step 3: Evaluate the limit using the derivatives:**

$\lim_{{x \to 3^+}} \frac{2}{\frac{2x}{x^2 - 8}} = \lim_{{x \to 3^+}} \frac{2(x^2 - 8)}{2x} = \lim_{{x \to 3^+}} \frac{x^2 - 8}{x}.$

Simplify the expression:

$\lim_{{x \to 3^+}} \frac{x^2 - 8}{x} = \lim_{{x \to 3^+}} \left(x - \frac{8}{x}\right).$

**Step 4: Substitute (x = 3):**

$\lim_{{x \to 3^+}} \left(x - \frac{8}{x}\right) = 3 - \frac{8}{3} = \frac{9}{3} - \frac{8}{3} = \frac{1}{3}.$

**Final Answer:**

The limit as $(x)$ approaches 3 from the right is $(\frac{1}{3}).$

---

$\lim_{{x \to -2}} \frac{x - 2}{x^2 + 2x}$

1. **Substitute $x = -2$**:
   - **Numerator**: $x - 2 = -2 - 2 = -4$.
   - **Denominator**: $x^2 + 2x = (-2)^2 + 2(-2) = 4 - 4 = 0$.

This results in an indeterminate form $\frac{-4}{0}$, which suggests that the limit might not exist in the traditional sense. However, let's simplify the expression to see if we can resolve it:

2. **Factor the Denominator**:
   - The denominator $x^2 + 2x$ can be factored as $x(x + 2)$.

3. **Simplify the Expression**:
   - The expression becomes $\frac{x - 2}{x(x + 2)}$.

4. **Evaluate the Limit**:
   - Since the denominator becomes zero at $x = -2$, and the numerator does not, the limit approaches negative or positive infinity depending on the direction from which $x$ approaches $-2$.

Thus, the limit $\lim_{{x \to -2}} \frac{x - 2}{x^2 + 2x}$ does not exist in the traditional sense, as the expression approaches infinity. To determine the behavior more precisely, you would need to consider the one-sided limits:

- As $x$ approaches $-2$ from the left ($x \to -2^-$), the expression approaches $-\infty$.
- As $x$ approaches $-2$ from the right ($x \to -2^+$), the expression approaches $+\infty$.

---

#### d. $\lim_{{x \to 0^+}} (5x + \cos x)^{\frac{3}{x}}$

1. **Base Analysis**:
   - As $x \to 0^+$, $5x \to 0$ and $\cos x \to \cos(0) = 1$.
   - Therefore, $5x + \cos x \to 0 + 1 = 1$.

2. **Exponent Analysis**:
   - The exponent $\frac{3}{x}$ approaches $+\infty$ as $x \to 0^+$.

3. **Overall Expression**:
   - We have an expression of the form $1^{\infty}$, which is an indeterminate form.

To resolve this indeterminate form, we can use the natural logarithm and L'Hôpital's Rule:

4. **Take the Natural Logarithm**:
   - Let $y = (5x + \cos x)^{\frac{3}{x}}$.
   - Then $\ln y = \frac{3}{x} \ln(5x + \cos x)$.

5. **Evaluate the Limit of $\ln y$**:
   - Consider $\lim_{{x \to 0^+}} \frac{3}{x} \ln(5x + \cos x)$.
   - As $x \to 0^+$, $\ln(5x + \cos x) \to \ln(1) = 0$.
   - We have an indeterminate form $\frac{0}{0}$, so we can apply L'Hôpital's Rule.

6. **Apply L'Hôpital's Rule**:
   - Differentiate the numerator and the denominator:
     - Derivative of the numerator: $\frac{d}{dx}[\ln(5x + \cos x)] = \frac{5 - \sin x}{5x + \cos x}$.
     - Derivative of the denominator: $\frac{d}{dx}[x] = 1$.
   - The limit becomes $\lim_{{x \to 0^+}} 3 \cdot \frac{5 - \sin x}{x(5x + \cos x)}$.

7. **Evaluate the Limit**:
   - As $x \to 0^+$, $\frac{5 - \sin x}{5x + \cos x} \to \frac{5 - 0}{0 + 1} = 5$.
   - Therefore, the limit of $\ln y$ is $\lim_{{x \to 0^+}} 3 \cdot 5 = 15$.

8. **Exponentiate to Find $y$**:
   - Since $\ln y \to 15$, $y \to e^{15}$.

**Final Answer**: The limit is $e^{15}$.

### Given Piecewise Function:

$$
f(x) =
\begin{cases} 
    \frac{x - 2}{\sqrt{x + 7} - 3}, & x > 2, \\
    5x + b, & x = 2, \\
    3 + ax, & 0 < x < 2, \\
    3 + e^{2x}, & x \leq 0.
\end{cases}
$$

---

### **a. Is (f(x)) continuous at (x = 0)? Justify.**

#### To check continuity at (x = 0), the following must hold:

1. $(f(0))$ is defined.
2. $(\lim_{{x \to 0^-}} f(x)$ = $\lim_{{x \to 0^+}} f(x) = f(0))$.

---

#### **Step 1: Evaluate (f(0)):**

For $(x \leq 0), (f(x) = 3 + e^{2x})$. Substituting $(x = 0)$:

$$
f(0) = 3 + e^{0} = 3 + 1 = 4.
$$

---

#### **Step 2: Evaluate $(\lim_{{x \to 0^-}} f(x)):$**

For $@$ As $(x \to 0^-):$

$$
\lim_{{x \to 0^-}} f(x) = 3 + e^{0} = 4.
$$

---

#### **Step 3: Evaluate: $(\lim_{{x \to 0^+}} f(x))$**

For $(0 < x < 2), (f(x) = 3 + ax).$ As $ (x \to 0^+):$

$$
\lim_{{x \to 0^+}} f(x) = 3 + a(0) = 3.
$$

---

#### **Step 4: Compare limits and (f(0)):**

$$
\lim_{{x \to 0^-}} f(x) = 4, \quad \lim_{{x \to 0^+}} f(x) = 3, \quad f(0) = 4.
$$

Since $(\lim_{{x \to 0^-}} f(x) \neq \lim_{{x \to 0^+}} f(x))$, (f(x)) is **not continuous** at (x = 0).

---

### **b. Find the values of (a) and (b) to make (f(x)) continuous at (x = 2).**

---

To ensure continuity at (x = 2), the following must hold:

1. $\lim_{x \to 2^-} f(x) = f(2)$,
2. $\lim_{x \to 2^+} f(x) = f(2)$.

**Step 1: Compute (f(2)):**
At (x = 2):

$$
f(2) = 5(2) + b = 10 + b. 
%%
$$

---

\*\*Step 2: Compute (\lim\_{x \to 2^-} f(x)) $For$(0 < x < 2), (f(x) = 3 + ax).$As$(x \to 2^-):\$\$

$$$
\lim_{x \to 2^-} f(x) = 3 + a(2) = 3 + 2a. $$
\]

---

**Step 3: Compute \(\lim_{x \to 2^+} f(x)\):**
For \(x > 2\), $$(f(x) = frac{x - 2}{\sqrt{x + 7} - 3}). As (x \to 2^+):$$

1. Simplify the denominator:
   $$[
   \sqrt{x + 7} - 3.
   ]$$
   At $$(x = 2), (\sqrt{x + 7} = \sqrt{9} = 3)$$, so direct substitution leads to an indeterminate form $$(\frac{0}{0}).$$

2. Use L'Hôpital's Rule:
   Differentiate the numerator and denominator:
   - Numerator: $$(\frac{d}{dx}[x - 2] = 1),$$
   - Denominator: \(\frac{d}{dx}[\sqrt{x + 7} - 3] = \frac{1}{2\sqrt{x + 7}}\).

   Applying L'Hôpital's Rule:
   \[
   $$\lim_{x \to 2^+} f(x) = \lim_{x \to 2} \frac{1}{\frac{1}{2\sqrt{x + 7}}} = \lim_{x \to 2} 2\sqrt{x + 7}.
$$$

Substituting (x = 2):
\[
$ \lim_{x \to 2^+} f(x) = 2\sqrt{9} = 6.$
]

---

This version includes the dollar signs for inline math and block math, ensuring proper LaTeX rendering in your notes.

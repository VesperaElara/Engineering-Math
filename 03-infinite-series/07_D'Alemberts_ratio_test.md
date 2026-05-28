# Engineering Mathematics Study Notes: D'Alembert's Ratio Test

## 1. Concept Identification
The notes introduce **D'Alembert's Ratio Test** (commonly known simply as the **Ratio Test**). This is a highly mechanical calculus test used to check if an infinite series converges or diverges. It is especially useful when the terms of a series contain exponents (like $2^n, 7^n$) or factorials (like $n!$). Instead of comparing the series to another helper series, this test analyzes the growth behavior of the series by comparing each term directly to its immediate successor.

---

## 2. Mathematical Representations

### The Core Limit Formula
Let $\sum u_n$ be an infinite series with positive terms. We analyze the behavior of the ratio of the next term ($u_{n+1}$) to the current term ($u_n$) as $n$ grows infinitely large:
$$\lim_{n \to \infty} \frac{u_{n+1}}{u_n} = l$$

### The Decision Threshold Rules
The value of the calculated limit $l$ dictates the absolute final outcome based on three strict criteria:
$$\text{If } l < 1 \implies \text{The series is Convergent}$$

$$\text{If } l > 1 \implies \text{The series is Divergent}$$

$$\text{If } l = 1 \implies \text{The test is Inconclusive (Fail)}$$

> **Important Note:** If $l = 1$, the test provides no information, and a different strategy (like the Limit Comparison Test) must be selected.

---

## 3. The Algorithm (Procedural Recipe)

To solve an infinite series using the Ratio Test, execute this precise step-by-step procedure:

### Step 1: Identify the Current Term ($u_n$)
Extract the main algebraic formula located inside the summation sign.

### Step 2: Formulate the Next Term ($u_{n+1}$)
Create a new expression by replacing every single occurrence of the letter $n$ in the original formula with the quantity $(n + 1)$. Always wrap $(n + 1)$ in parentheses.

### Step 3: Setup the Division Ratio Fraction
Write out the division limit structure. To make calculation easier, immediately convert the division into a multiplication problem by multiplying $u_{n+1}$ by the reciprocal (flipped version) of $u_n$:
$$\frac{u_{n+1}}{u_n} = u_{n+1} \times \frac{1}{u_n}$$

### Step 4: Break Down Exponents and Factorials
Use basic rules of algebra to split up combined exponent terms and expand larger factorials into smaller pieces so they can be canceled out easily.

### Step 5: Force Factor Out Dominant $n$ Terms
Pull out the highest powers of $n$ from all remaining grouped brackets, cancel them, and compute the limit by substituting $n = \infty$.

### Step 6: Evaluate Against Thresholds
Compare the calculated number $l$ against the value $1$ to conclude whether the series converges or diverges.

---

## 4. Operational Mechanics

### The Core Algebraic Rules Needed
Before looking at the problems, you must know how the lecture breaks down complex terms mechanically:

**Rule A: Splitting Exponents**
An addition in an exponent is simply multiplication in disguise:
$$2^{n+1} = 2^n \times 2^1 = 2 \cdot 2^n$$

$$7^{n+1} = 7^n \times 7^1 = 7 \cdot 7^n$$

**Rule B: Stripping Factorials**
A factorial represents multiplying all whole numbers down to $1$. You can strip off the first term to reveal the original factorial expression:
$$(n+1)! = (n+1) \times n \times (n-1) \times \dots \times 1 = (n+1) \cdot n!$$

---

### Solution to Problem 1: Growing Exponential Numerator
$$\text{Test for convergence of the series: } \sum_{n=1}^{\infty} \frac{2^n}{n^3 + 1}$$

**Step 1: State the current term**
$$u_n = \frac{2^n}{n^3 + 1}$$

**Step 2: State the next term**
Substitute $(n+1)$ into every $n$ position:
$$u_{n+1} = \frac{2^{n+1}}{(n+1)^3 + 1}$$

**Step 3: Setup the flipped multiplication limit**
$$\lim_{n \to \infty} \frac{u_{n+1}}{u_n} = \lim_{n \to \infty} \left[ \frac{2^{n+1}}{(n+1)^3 + 1} \times \frac{n^3 + 1}{2^n} \right]$$

**Step 4: Break down components and regroup terms**
Split $2^{n+1}$ into $2^n \cdot 2$ and rearrange the matching components:
$$\lim_{n \to \infty} \frac{u_{n+1}}{u_n} = \lim_{n \to \infty} \left[ \frac{2 \cdot 2^n}{2^n} \times \frac{n^3 + 1}{(n+1)^3 + 1} \right]$$

Cancel the $2^n$ terms:
$$\lim_{n \to \infty} \frac{u_{n+1}}{u_n} = \lim_{n \to \infty} \left[ 2 \times \frac{n^3 + 1}{(n+1)^3 + 1} \right]$$

**Step 5: Factor out $n^3$ to compute the limit**
$$\lim_{n \to \infty} \frac{u_{n+1}}{u_n} = \lim_{n \to \infty} \left[ 2 \times \frac{n^3\left(1 + \frac{1}{n^3}\right)}{n^3\left(1 + \frac{1}{n}\right)^3 + 1} \right]$$

$$\lim_{n \to \infty} \frac{u_{n+1}}{u_n} = \lim_{n \to \infty} \left[ 2 \times \frac{n^3\left(1 + \frac{1}{n^3}\right)}{n^3\left[ \left(1 + \frac{1}{n}\right)^3 + \frac{1}{n^3} \right]} \right]$$

Cancel the $n^3$ terms outside the brackets:
$$\lim_{n \to \infty} \frac{u_{n+1}}{u_n} = \lim_{n \to \infty} \left[ 2 \times \frac{1 + \frac{1}{n^3}}{\left(1 + \frac{1}{n}\right)^3 + \frac{1}{n^3}} \right]$$

Substitute $n = \infty$, which turns all fractional components to $0$:
$$l = 2 \times \frac{1 + 0}{(1 + 0)^3 + 0} = 2 \times 1 = 2$$

**Step 6: Evaluate the threshold**
$$l = 2 \implies 2 > 1$$

$$\text{Conclusion: The series is divergent.}$$

---

### Solution to Problem 2: Growing Exponential Denominator
$$\text{Test for convergence of the series: } \sum_{n=1}^{\infty} \frac{n^2}{7^n}$$

**Step 1: State the current term**
$$u_n = \frac{n^2}{7^n}$$

**Step 2: State the next term**
$$u_{n+1} = \frac{(n+1)^2}{7^{n+1}}$$

**Step 3: Setup the flipped multiplication limit**
$$\lim_{n \to \infty} \frac{u_{n+1}}{u_n} = \lim_{n \to \infty} \left[ \frac{(n+1)^2}{7^{n+1}} \times \frac{7^n}{n^2} \right]$$

**Step 4: Break down components and regroup terms**
Split $7^{n+1}$ into $7^n \cdot 7$ and rearrange matching components:
$$\lim_{n \to \infty} \frac{u_{n+1}}{u_n} = \lim_{n \to \infty} \left[ \frac{7^n}{7 \cdot 7^n} \times \frac{(n+1)^2}{n^2} \right]$$

Cancel the $7^n$ terms:
$$\lim_{n \to \infty} \frac{u_{n+1}}{u_n} = \lim_{n \to \infty} \left[ \frac{1}{7} \times \left(\frac{n+1}{n}\right)^2 \right]$$

Simplify the internal fraction:
$$\lim_{n \to \infty} \frac{u_{n+1}}{u_n} = \lim_{n \to \infty} \left[ \frac{1}{7} \times \left(1 + \frac{1}{n}\right)^2 \right]$$

**Step 5: Compute the limit value**
Substitute $n = \infty$, which turns the fractional component to $0$:
$$l = \frac{1}{7} \times (1 + 0)^2 = \frac{1}{7} \times 1 = \frac{1}{7}$$

**Step 6: Evaluate the threshold**
$$l = \frac{1}{7} \implies \frac{1}{7} < 1$$

$$\text{Conclusion: The series is convergent.}$$

---

### Solution to Problem 3: The Factorial Series
$$\text{Using the Ratio Test, test the convergence of the series: } \sum \frac{n! \cdot 2^n}{n^n}$$

**Step 1: State the current term**
$$u_n = \frac{n! \cdot 2^n}{n^n}$$

**Step 2: State the next term**
Carefully change all $n$ variables to $(n+1)$:
$$u_{n+1} = \frac{(n+1)! \cdot 2^{n+1}}{(n+1)^{n+1}}$$

**Step 3: Setup the flipped multiplication limit**
$$\lim_{n \to \infty} \frac{u_{n+1}}{u_n} = \lim_{n \to \infty} \left[ \frac{(n+1)! \cdot 2^{n+1}}{(n+1)^{n+1}} \times \frac{n^n}{n! \cdot 2^n} \right]$$

**Step 4: Break down components to prepare for cancellation**
* Expand the factorial: $(n+1)! = (n+1) \cdot n!$
* Expand the exponential base: $2^{n+1} = 2 \cdot 2^n$
* Expand the power base: $(n+1)^{n+1} = (n+1)^n \cdot (n+1)^1 = (n+1) \cdot (n+1)^n$

Substitute these expanded pieces back into our limit calculation line:
$$\lim_{n \to \infty} \frac{u_{n+1}}{u_n} = \lim_{n \to \infty} \left[ \frac{(n+1) \cdot n! \cdot 2 \cdot 2^n}{(n+1) \cdot (n+1)^n} \times \frac{n^n}{n! \cdot 2^n} \right]$$

Cross out the matching pairs ($n!$, $2^n$, and the standalone bracket term $(n+1)$):
$$\lim_{n \to \infty} \frac{u_{n+1}}{u_n} = \lim_{n \to \infty} \left[ 2 \times \frac{n^n}{(n+1)^n} \right]$$

Consolidate the terms under a shared exponent power of $n$:
$$\lim_{n \to \infty} \frac{u_{n+1}}{u_n} = \lim_{n \to \infty} \left[ 2 \times \left(\frac{n}{n+1}\right)^n \right]$$

Invert the internal fraction to move the power down to the denominator:
$$\lim_{n \to \infty} \frac{u_{n+1}}{u_n} = \lim_{n \to \infty} \left[ \frac{2}{\left(\frac{n+1}{n}\right)^n} \right]$$

$$\lim_{n \to \infty} \frac{u_{n+1}}{u_n} = \lim_{n \to \infty} \left[ \frac{2}{\left(1 + \frac{1}{n}\right)^n} \right]$$

**Step 5: Compute the limit value using the special identity**
Recall the fundamental calculus identity rule: $\lim_{n \to \infty} \left(1 + \frac{1}{n}\right)^n = e$ (where Euler's constant $e \approx 2.718$).
$$l = \frac{2}{e}$$

**Step 6: Evaluate the threshold**
Substitute the value of $e \approx 2.718$ to check the size of the fraction:
$$l = \frac{2}{2.718} \approx 0.736 \implies 0.736 < 1$$

$$\text{Conclusion: The series is convergent.}$$
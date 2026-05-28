# Engineering Mathematics Study Notes: Geometric Series Solved Problems

## 1. Concept Identification
The latest lecture boards apply the **Geometric Series Test** to multi-term algebraic fractions and numerical fractional series. It introduces two core algebraic strategies for beginners:
* **Splitting the Numerator**: Distributing a shared denominator across a sum of terms to break one complex series into two separate geometric series.
* **Base Exponential Form Conversion**: Recognizing powers of numbers (like $4, 16, 64$) to convert a raw list of fractions into standard geometric index form ($r^n$).

---

## 2. Mathematical Representations

### Linearity Property of Summation
An infinite series containing added terms can be mechanically separated into independent infinite series:
$$\sum_{n=1}^{\infty} (u_n + v_n) = \sum_{n=1}^{\infty} u_n + \sum_{n=1}^{\infty} v_n$$

### Index Laws for Powers
Fractions with shared exponents can be consolidated into a single base ratio:
$$\frac{a^n}{b^n} = \left(\frac{a}{b}\right)^n$$

---

## 3. The Algorithm (Procedural Recipe)

To solve multi-term or implicit exponential series, follow this exact structural procedure:

### Step 1: Simplify into Independent Fractional Terms
If the numerator has multiple added components over a single denominator, split the fraction completely.

### Step 2: Extract Common Exponents
Group the individual numerator and denominator powers into a single fraction raised to the power of $n$. Simplify the internal fraction to its lowest terms.

### Step 3: Separate into Independent Geometric Series
Distribute the summation symbol ($\sum$) to each individual exponential term.

### Step 4: Extract Parameters ($a$ and $r$) for Each Sub-Series
For each independent series, identify the first term ($a$) by substituting the starting index (e.g., $n=1$) and find the common ratio ($r$) by inspecting the base of the exponent.

### Step 5: Run Individual Convergence Evaluations
Test the absolute value of each common ratio ($|r|$) against the threshold value of $1$.

### Step 6: Conclude Overall Behavior
Combine the results. If all individual sub-series converge, the entire combined series is **Convergent**. If any single part diverges, the entire expression is **Divergent**.

---

## 4. Operational Mechanics & Solutions to Board Problems

### Solution to Problem 1: Multi-Term Exponential Fraction
The lecture board presents the following problem:
$$\text{Test for convergence of the series: } \sum_{n=1}^{\infty} \frac{4^n + 5^n}{6^n}$$

**Step 1: Split the shared denominator across the numerator terms**
$$\sum_{n=1}^{\infty} \left( \frac{4^n}{6^n} + \frac{5^n}{6^n} \right)$$

**Step 2: Consolidate the exponents using power laws**
$$\sum_{n=1}^{\infty} \left[ \left(\frac{4}{6}\right)^n + \left(\frac{5}{6}\right)^n \right]$$

Reduce the fractions to their simplest forms by dividing by their greatest common factors:
$$\sum_{n=1}^{\infty} \left[ \left(\frac{2}{3}\right)^n + \left(\frac{5}{6}\right)^n \right]$$

**Step 3: Separate into two independent summation loops**
$$\sum_{n=1}^{\infty} \left(\frac{2}{3}\right)^n + \sum_{n=1}^{\infty} \left(\frac{5}{6}\right)^n$$

**Step 4: Analyze Part 1 ($\sum_{n=1}^{\infty} \left(\frac{2}{3}\right)^n$)**
Find the first term by plugging in the starting index $n=1$:
$$a_1 = \left(\frac{2}{3}\right)^1 = \frac{2}{3}$$

Identify the base ratio under the exponent:
$$r_1 = \frac{2}{3}$$

Evaluate the convergence condition:
$$\left| \frac{2}{3} \right| < 1 \implies \text{Part 1 is Convergent}$$

**Step 5: Analyze Part 2 ($\sum_{n=1}^{\infty} \left(\frac{5}{6}\right)^n$)**
Find the first term by plugging in the starting index $n=1$:
$$a_2 = \left(\frac{5}{6}\right)^1 = \frac{5}{6}$$

Identify the base ratio under the exponent:
$$r_2 = \frac{5}{6}$$

Evaluate the convergence condition:
$$\left| \frac{5}{6} \right| < 1 \implies \text{Part 2 is Convergent}$$

**Step 6: Final Conclusion**
Since both individual sub-series are completely convergent, their sum is stable.
$$\text{Conclusion: The series is convergent.}$$

---

### Solution to Problem 2: Implicit Numerical Fractional Series
The lecture board presents the following numerical sequence:
$$\text{Test for convergence of the series: } 1 + \frac{3}{4} + \frac{9}{16} + \frac{27}{64} + \dots \infty$$

**Step 1: Convert values into base exponent notation**
Examine the denominators: $1, 4, 16, 64$ are all perfect powers of $4$ ($4^0, 4^1, 4^2, 4^3$).
Examine the numerators: $1, 3, 9, 27$ are all perfect powers of $3$ ($3^0, 3^1, 3^2, 3^3$).

Rewrite the list matching the exponential powers explicitly:
$$1 + \frac{3}{4} + \left(\frac{3}{4}\right)^2 + \left(\frac{3}{4}\right)^3 + \dots \infty$$

This structure matches the standard definition of a geometric series.

**Step 2: Extract the parameters directly**
Identify the very first number listed in the series:
$$a = 1$$

Identify the constant factor being multiplied to progress from term to term:
$$r = \frac{3}{4}$$

**Step 3: Test the stability threshold**
Take the absolute value of the ratio parameter:
$$|r| = \left| \frac{3}{4} \right| = \frac{3}{4}$$

Compare this fraction directly against $1$:
$$\frac{3}{4} < 1 \implies \text{The absolute value of common ratio is less than 1}$$

**Step 4: Final Conclusion**
Because the common ratio falls strictly within the convergence window, the infinite addition is guaranteed to settle on a single finite number.
$$\text{Conclusion: The series is convergent.}$$
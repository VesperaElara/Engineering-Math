# Engineering Mathematics Study Notes: Limit Comparison Test Solved Problems

## 1. Concept Identification
The notes apply the **Limit Comparison Test (LCT)** combined with the **P-Series Test** to advanced algebraic series containing fractional factors and radical terms. It also introduces **Rationalization** as a preliminary mechanical step to convert difference-of-roots expressions into fraction forms suitable for testing.

---

## 2. Mathematical Representations

### Difference of Squares Identity (Rationalization)
To remove radical terms subtraction from the numerator, apply the conjugate identity:
$$(a - b)(a + b) = a^2 - b^2$$

### Limit Comparison Test Ratio
$$\lim_{n \to \infty} \frac{u_n}{v_n} = L \quad (0 < L < \infty)$$

---

## 3. The Algorithm (Procedural Recipe)

To solve any complex fractional or radical infinite series from first principles, follow this exact procedural blueprint:

### Step 1: Pre-Process with Rationalization (If Radicals are Subtracted)
If $u_n$ consists of two square roots subtracted from each other, multiply the numerator and denominator by its conjugate counterpart (changing the minus sign to a plus sign) to force a fractional form.

### Step 2: Establish the Target Term ($u_n$)
Isolate the simplified algebraic expression inside the summation sign.

### Step 3: Determine the Helper Term ($v_n$)
Extract the single highest order term of $n$ from the numerator and divide it by the single highest order term of $n$ from the denominator. Simplify this down to a pure p-series structure:
$$v_n = \frac{1}{n^p}$$

### Step 4: Evaluate the Limit of the Ratio ($\frac{u_n}{v_n}$)
Compute the limit as $n \to \infty$ of the product of $u_n$ and the mathematical inverse of $v_n$. Factor out leading degrees of $n$, eliminate terms approaching zero, and solve for a finite constant value $L$.

### Step 5: Execute the Benchmark Verification
Check $p$ against the p-series condition ($p > 1$ converges, $p \leq 1$ diverges) to determine the fate of $\sum v_n$. Conclude that $\sum u_n$ shares the same outcome.

---

## 4. Operational Mechanics & Solutions to Board Problems

### Solution to Problem 1: Fractional Factored Series
The lecture board presents the following problem:
$$\text{Test for convergence of the series: } \frac{1}{1 \cdot 2 \cdot 3} + \frac{3}{2 \cdot 3 \cdot 4} + \frac{5}{3 \cdot 4 \cdot 5} + \dots \infty$$

**Step 1: Construct the general term formula ($u_n$)**
Examine the pattern of the numerators: $1, 3, 5, \dots$ which forms an arithmetic progression where $a=1, d=2$:
$$\text{Top Term} = 1 + (n-1)2 = 2n - 1$$

Examine the pattern of the three multiplying numbers in the denominators:
$$\text{First factors: } 1, 2, 3 \dots \implies n$$

$$\text{Second factors: } 2, 3, 4 \dots \implies (n + 1)$$

$$\text{Third factors: } 3, 4, 5 \dots \implies (n + 2)$$

Combine these together to form the target expression:
$$u_n = \frac{2n - 1}{n(n + 1)(n + 2)}$$

**Step 2: Isolate the maximum powers to build $v_n$**
The highest power of $n$ visible in the numerator is $n^1$. 
Multiply out the leading terms of the denominator to find its maximum power degree:
$$n \times n \times n = n^3$$

Form the comparison helper term using these maximum degrees:
$$v_n = \frac{n}{n^3} = \frac{1}{n^2}$$

**Step 3: Setup the ratio calculation**
Set up the limit function by multiplying $u_n$ by the reciprocal of $v_n$:
$$\lim_{n \to \infty} \frac{u_n}{v_n} = \lim_{n \to \infty} \left[ \frac{2n - 1}{n(n+1)(n+2)} \times \frac{n^2}{1} \right]$$

Multiply out the expressions:
$$\lim_{n \to \infty} \frac{u_n}{v_n} = \lim_{n \to \infty} \frac{2n^3 - n^2}{n^3 + 3n^2 + 2n}$$

Forcefully pull out the maximum global power ($n^3$) from all positions:
$$\lim_{n \to \infty} \frac{u_n}{v_n} = \lim_{n \to \infty} \frac{n^3 \left( 2 - \frac{1}{n} \right)}{n^3 \left( 1 + \frac{3}{n} + \frac{2}{n^2} \right)}$$

Cancel the $n^3$ elements outside the brackets:
$$\lim_{n \to \infty} \frac{u_n}{v_n} = \lim_{n \to \infty} \frac{2 - \frac{1}{n}}{1 + \frac{3}{n} + \frac{2}{n^2}}$$

Substitute $n = \infty$, turning all inverse elements to $0$:
$$L = \frac{2 - 0}{1 + 0 + 0} = 2$$

Since $2$ is a real, finite, non-zero constant, the Limit Comparison Test is active and valid.

**Step 4: Run the p-series assessment**
Look at the helper term exponent from Step 2:
$$v_n = \frac{1}{n^2} \implies p = 2$$

Because $2 > 1$, the helper series $\sum v_n$ is convergent.

**Step 5: Final Conclusion**
By the rules of the Limit Comparison Test, the original target series is **Convergent**.

---

### Solution to Problem 2: Radical Difference Series
The lecture board presents the following radical problem:
$$\text{Test the convergence of the series: } \sum_{n=1}^{\infty} \left( \sqrt{n + 1} - \sqrt{n - 1} \right)$$

**Step 1: Rationalize the expression to create a fraction**
The target expression is:
$$u_n = \sqrt{n + 1} - \sqrt{n - 1}$$

Multiply both the top and hidden bottom by the conjugate addition expression:
$$u_n = \frac{\left(\sqrt{n + 1} - \sqrt{n - 1}\right) \times \left(\sqrt{n + 1} + \sqrt{n - 1}\right)}{\sqrt{n + 1} + \sqrt{n - 1}}$$

Apply the algebraic difference of squares identity $(a-b)(a+b) = a^2 - b^2$ to collapse the top numerator:
$$u_n = \frac{(\sqrt{n + 1})^2 - (\sqrt{n - 1})^2}{\sqrt{n + 1} + \sqrt{n - 1}}$$

$$\text{Extract values out of the canceled square roots:}$$
$$u_n = \frac{(n + 1) - (n - 1)}{\sqrt{n + 1} + \sqrt{n - 1}}$$

$$\text{Distribute the negative sign carefully:}$$
$$u_n = \frac{n + 1 - n + 1}{\sqrt{n + 1} + \sqrt{n - 1}}$$

$$u_n = \frac{2}{\sqrt{n + 1} + \sqrt{n - 1}}$$

**Step 2: Formulate the comparison helper term ($v_n$)**
The numerator contains no variable, so its highest degree is $n^0 = 1$.
The denominator's dominant terms are locked inside square roots, which means their highest power degree is $\sqrt{n} = n^{1/2}$.
$$v_n = \frac{1}{\sqrt{n}} = \frac{1}{n^{1/2}}$$

**Step 3: Evaluate the limit value**
Multiply $u_n$ by the mathematical reciprocal of $v_n$:
$$\lim_{n \to \infty} \frac{u_n}{v_n} = \lim_{n \to \infty} \left[ \frac{2}{\sqrt{n + 1} + \sqrt{n - 1}} \times \frac{\sqrt{n}}{1} \right]$$

$$\lim_{n \to \infty} \frac{u_n}{v_n} = \lim_{n \to \infty} \frac{2\sqrt{n}}{\sqrt{n}\left(\sqrt{1 + \frac{1}{n}} + \sqrt{1 - \frac{1}{n}}\right)}$$

Cancel the matching $\sqrt{n}$ terms from both positions:
$$\lim_{n \to \infty} \frac{u_n}{v_n} = \lim_{n \to \infty} \frac{2}{\sqrt{1 + \frac{1}{n}} + \sqrt{1 - \frac{1}{n}}}$$

Apply the infinite limit to eliminate the internal fractional values:
$$L = \frac{2}{\sqrt{1 + 0} + \sqrt{1 - 0}} = \frac{2}{1 + 1} = \frac{2}{2} = 1$$

Since $1$ is a finite, non-zero constant, the test framework confirms identical behavior.

**Step 4: Execute the p-series test**
Check the value of the exponent from Step 2:
$$p = \frac{1}{2}$$

Evaluate the threshold condition:
$$\frac{1}{2} \leq 1 \implies \text{The helper series } \sum v_n \text{ is Divergent.}$$

**Step 5: Final Conclusion**
By the mechanical rules of the Limit Comparison Test, the original target radical series is **Divergent**.
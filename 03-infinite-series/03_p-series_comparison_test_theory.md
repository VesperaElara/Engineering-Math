# Engineering Mathematics Study Notes: Limit Comparison Test & P-Series Test

## 1. Concept Identification
The notes introduce a powerful, mechanical strategy for determining the convergence or divergence of an infinite series containing algebraic fractions:
* **The Limit Comparison Test (LCT)**: A test used when an infinite series $\sum u_n$ is too complex to evaluate directly. We compare its behavior against a simpler, known helper series $\sum v_n$.
* **The P-Series Test**: A highly standardized benchmark test used exclusively to instantly know whether the chosen helper series $\sum v_n$ converges or diverges based on the exponent value.

---

## 2. Mathematical Representations

### The Limit Comparison Test Condition
Let $\sum u_n$ be your given positive term series, and let $\sum v_n$ be your constructed helper series. Compute the limit of their ratio:
$$\lim_{n \to \infty} \frac{u_n}{v_n} = L$$

The test is valid and operational if and only if $L$ satisfies:
$$0 < L < \infty \quad (\text{where } L \text{ is a Finite, Non-Zero constant})$$

Under this condition, both series possess identical convergence behavior (they either converge together or diverge together).

### The P-Series Test Formula
A standard p-series is written in the form:
$$\sum v_n = \sum \frac{1}{n^p}$$

The convergence or divergence behavior is determined mechanically by inspecting the value of the exponent $p$:
$$\text{If } p > 1 \implies \text{The series is Convergent}$$

$$\text{If } p \leq 1 \implies \text{The series is Divergent}$$

---

## 3. The Algorithm (Procedural Recipe)

To solve an infinite algebraic series using the Limit Comparison Test framework, follow this exact step-by-step recipe:

### Step 1: Extract the General Term ($u_n$)
Identify the algebraic formula representing the inside of the summation sign. 
$$u_n = \text{Given Expression}$$

### Step 2: Construct the Helper Term ($v_n$)
Look at the formula for $u_n$. Find the highest power of $n$ in the numerator and the highest power of $n$ in the denominator. Define $v_n$ as:
$$v_n = \frac{\text{Highest Power of } n \text{ in Numerator}}{\text{Highest Power of } n \text{ in Denominator}} = \frac{1}{n^p}$$

### Step 3: Set up and Simplify the Ratio Fraction $\frac{u_n}{v_n}$
Multiply $u_n$ by the reciprocal of $v_n$ to cleanly cancel out the dominant $n$ terms before passing the limit:
$$\frac{u_n}{v_n} = u_n \times \frac{1}{v_n}$$

### Step 4: Evaluate the Limit as $n \to \infty$
Factor out the remaining dominant powers of $n$ within the parentheses, cancel them, and apply the infinite limit substitution to collapse all remaining fractional $n$ elements into zero:
$$L = \lim_{n \to \infty} \frac{u_n}{v_n}$$

### Step 5: Run the P-Series Decision on $v_n$
Check the value of $p$ from Step 2 against the p-series threshold rule. State whether $\sum v_n$ converges or diverges.

### Step 6: Conclude the Target Behavior
Because $L$ is a finite, non-zero number, declare that your target series $\sum u_n$ copies the exact conclusion found in Step 5.

---

## 4. Operational Mechanics

### Mechanical Example 1: Creating a Helper Series ($v_n$)
The board shows examples of extracting the highest powers to form $v_n$. Let's trace how the teacher does it mechanically:

**Case A**
$$u_n = \frac{n^5}{n^7}$$
The highest power on top is $n^5$. The highest power on bottom is $n^7$.
$$v_n = \frac{n^5}{n^7} = \frac{1}{n^{7-5}} = \frac{1}{n^2}$$

**Case B**
$$u_n = \frac{n^2}{n^5}$$
The highest power on top is $n^2$. The highest power on bottom is $n^5$.
$$v_n = \frac{n^2}{n^5} = \frac{1}{n^{5-2}} = \frac{1}{n^3}$$

### Mechanical Example 2: Factoring out Radicals
Let's look at the mechanical steps on the board for extracting terms trapped inside square roots:
$$u_n = \frac{1}{\sqrt{n+1} + \sqrt{n-1}}$$

Pull out $n$ inside each radical sign:
$$u_n = \frac{1}{\sqrt{n\left(1 + \frac{1}{n}\right)} + \sqrt{n\left(1 - \frac{1}{n}\right)}}$$

Distribute the square root power onto both components:
$$u_n = \frac{1}{\sqrt{n}\sqrt{1 + \frac{1}{n}} + \sqrt{n}\sqrt{1 - \frac{1}{n}}}$$

Factor out the common $\sqrt{n}$ from the entire denominator:
$$u_n = \frac{1}{\sqrt{n}\left(\sqrt{1 + \frac{1}{n}} + \sqrt{1 - \frac{1}{n}}\right)}$$

Now, isolate the pure $n$ fraction outside the parentheses to find your helper series $v_n$:
$$v_n = \frac{1}{\sqrt{n}} = \frac{1}{n^{1/2}}$$

### Mechanical Example 3: Full Solved Board Problem
Let's trace through the complete problem solved across the final board images:
$$\text{Test for convergence of the series: } \sum_{n=0}^{\infty} \frac{2n^3 + 5}{4n^5 + 1}$$

**Step 1: State the general term**
$$u_n = \frac{2n^3 + 5}{4n^5 + 1}$$

**Step 2: Construct the helper term**
The highest power on top is $n^3$. The highest power on bottom is $n^5$.
$$v_n = \frac{n^3}{n^5} = \frac{1}{n^2}$$

**Step 3 & 4: Set up the limit of the ratio**
Multiply $u_n$ by the flip of $v_n$:
$$\lim_{n \to \infty} \frac{u_n}{v_n} = \lim_{n \to \infty} \left( \frac{2n^3 + 5}{4n^5 + 1} \times \frac{n^2}{1} \right)$$

Distribute the $n^2$ directly into the top terms:
$$\lim_{n \to \infty} \frac{u_n}{v_n} = \lim_{n \to \infty} \frac{2n^5 + 5n^2}{4n^5 + 1}$$

Forcefully factor out the highest power ($n^5$) from the top and bottom expressions:
$$\lim_{n \to \infty} \frac{u_n}{v_n} = \lim_{n \to \infty} \frac{n^5\left(2 + \frac{5}{n^3}\right)}{n^5\left(4 + \frac{1}{n^5}\right)}$$

Cancel the matching outer $n^5$ variables:
$$\lim_{n \to \infty} \frac{u_n}{v_n} = \lim_{n \to \infty} \frac{2 + \frac{5}{n^3}}{4 + \frac{1}{n^5}}$$

Substitute the infinite limit ($\infty$) values:
$$L = \frac{2 + 0}{4 + 0} = \frac{2}{4} = \frac{1}{2}$$

Verify the condition: $\frac{1}{2}$ is a finite, non-zero constant. The test is completely valid.

**Step 5: Apply the P-Series Test on our helper**
Look back at our helper series formula:
$$\sum v_n = \sum \frac{1}{n^2}$$

Identify the exponent:
$$p = 2$$

Evaluate the condition:
$$2 > 1 \implies \sum v_n \text{ is Convergent}$$

**Step 6: Conclude the final result**
By the Limit Comparison Test, since $\sum v_n$ converges, the original target series also converges.
$$\text{Conclusion: The sequence/series is convergent.}$$
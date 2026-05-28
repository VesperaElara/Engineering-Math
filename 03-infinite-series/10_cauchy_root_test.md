# Engineering Mathematics Study Notes: Cauchy's Root Test

## 1. IDENTIFY
The mathematical concept presented on the board is **Cauchy's Root Test** (frequently called the $n$-th Root Test). It is an elegant convergence test for infinite series of positive terms. It is uniquely engineered to handle mathematical terms wrapped inside global exponents like $n$, $n^2$, $n^3$, or $n^4$.

---

## 2. THE FORMULA
Let $\sum u_n$ be an infinite series of positive terms where individual terms contain variable powers. We evaluate the limit value $l$ by taking the $n$-th root of the general term:

$$\lim_{n \to \infty} (u_n)^{\frac{1}{n}} = l$$

The structural behavior of the infinite series is determined by comparing $l$ directly against $1$:

1. The series $\sum u_n$ is **convergent** if:
$$l < 1$$

2. The series $\sum u_n$ is **divergent** if:
$$l > 1$$

3. The test **fails** to provide a conclusion if:
$$l = 1$$

---

## 3. THE ALGORITHM
This structural blueprint highlights how to execute Cauchy's Root Test mechanically.

### Step 1: Detect the Visual Trigger
Look for general terms that are entirely enclosed within an outer power of $n$ or its powers ($n^2$, $n^3$, etc.).

### Step 2: Extract the General Term
Identify and write out the exact algebraic expression for the $n$-th term, designated as $u_n$.

### Step 3: Apply the Radical Multiplier
Raise the entire expression $u_n$ to the power of $\frac{1}{n}$.

$$(u_n)^{\frac{1}{n}}$$

### Step 4: Neutralize the Outer Exponent
Apply exponent laws to multiply the internal power by $\frac{1}{n}$, canceling out the dominant $n$ variable.

### Step 5: Compute the Limit
Evaluate the limit of the remaining structural expression as $n \to \infty$.

$$l = \lim_{n \to \infty} (u_n)^{\frac{1}{n}}$$

### Step 6: Execute the Decision Rule
Check if the output value $l$ is strictly less than $1$ (convergent) or greater than $1$ (divergent).

---

## 4. THE MECHANICS

### Core Operations Explained
- **Power of a Power Rule**: When an exponential expression is raised to another power, the exponents multiply together directly.
$$(a^m)^n = a^{m \times n}$$
- **Exponent Cancellation**: Raising an $n$-th power to $\frac{1}{n}$ completely strips away the outer exponent.
$$\left(x^n\right)^{\frac{1}{n}} = x^{n \times \frac{1}{n}} = x^1 = x$$
- **Higher-Order Exponent Reduction**: If a term is raised to $n^2$, multiplying by $\frac{1}{n}$ reduces the power down to a single linear $n$.
$$\left(x^{n^2}\right)^{\frac{1}{n}} = x^{n^2 \times \frac{1}{n}} = x^n$$
- **Infinity Fractions**: When evaluating the limit as $n \to \infty$, terms structured as $\frac{\text{constant}}{n}$ dissolve systematically to $0$.

### Full Mechanics Walkthrough: Problem 1
Consider the series:
$$\sum_{n=1}^{\infty} \frac{2^n}{3^n}$$

Extract the general term $u_n$ and pull out the shared exponent:
$$u_n = \frac{2^n}{3^n} = \left(\frac{2}{3}\right)^n$$

Apply the $n$-th root operator to the term expression:
$$\lim_{n \to \infty} (u_n)^{\frac{1}{n}} = \lim_{n \to \infty} \left[ \left(\frac{2}{3}\right)^n \right]^{\frac{1}{n}}$$

Multiply the exponents together to simplify the expression layout:
$$\lim_{n \to \infty} \left(\frac{2}{3}\right)^{n \times \frac{1}{n}}$$

Cancel the inverse matching variable terms in the exponent:
$$\lim_{n \to \infty} \left(\frac{2}{3}\right)^1$$

Evaluate the constant limit directly:
$$l = \frac{2}{3}$$

Compare the final evaluated value against the threshold rule:
$$\frac{2}{3} < 1$$

Since the limit value satisfies $l < 1$, the series is **convergent**.

### Full Mechanics Walkthrough: Problem 2
Consider the series:
$$\left(\frac{1}{3}\right)^1 + \left(\frac{2}{5}\right)^2 + \left(\frac{3}{7}\right)^3 + \dots$$

Determine the general mathematical pattern for the $n$-th term $u_n$:
- Numerator pattern ($1, 2, 3 \dots$) maps to: $n$
- Denominator pattern ($3, 5, 7 \dots$) maps to an arithmetic progression: $2n + 1$
- Global power pattern ($1, 2, 3 \dots$) maps to: $n$

$$u_n = \left(\frac{n}{2n+1}\right)^n$$

Apply the root test operator to the constructed expression:
$$\lim_{n \to \infty} (u_n)^{\frac{1}{n}} = \lim_{n \to \infty} \left[ \left(\frac{n}{2n+1}\right)^n \right]^{\frac{1}{n}}$$

Execute exponent multiplication to remove the outer bracket power:
$$\lim_{n \to \infty} \left(\frac{n}{2n+1}\right)^{n \times \frac{1}{n}}$$

Simplify the expression down to its core fraction component:
$$\lim_{n \to \infty} \frac{n}{2n+1}$$

Factor out the dominant variable $n$ from the internal terms of the denominator:
$$\lim_{n \to \infty} \frac{n}{n\left(2 + \frac{1}{n}\right)}$$

Cancel out the common shared variable $n$ across both positions:
$$\lim_{n \to \infty} \frac{1}{2 + \frac{1}{n}}$$

Apply the limit condition boundaries as $n$ approaches infinity:
$$\frac{1}{2 + \frac{1}{\infty}} = \frac{1}{2 + 0} = \frac{1}{2}$$

Compare the calculated limit value against the final checklist rule:
$$\frac{1}{2} < 1$$

Since the limit value satisfies $l < 1$, the series is **convergent**.
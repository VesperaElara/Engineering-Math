# Engineering Mathematics Study Notes: Raabe's Test with Variable Terms

## 1. IDENTIFY
The mathematical concept presented on the board is **Raabe's Test** applied to an infinite series containing a variable parameter $x$. When a variable like $x$ is present, **D'Alembert's Ratio Test** is always performed first to determine convergence conditions dependent on $x$. Raabe's Test is then applied specifically to resolve the boundary case where the ratio test fails (i.e., when the expression involving $x$ equals $1$).

---

## 2. THE FORMULA
The general term of the series contains a variable $x > 0$. The evaluation follows a two-tiered formula approach:

### Tier 1: D'Alembert's Ratio Test
$$\lim_{n \to \infty} \frac{u_{n+1}}{u_n} = L$$

- If $L < 1$, the series converges.
- If $L > 1$, the series diverges.
- If $L = 1$, the test fails (this occurs at a specific value of $x$).

### Tier 2: Raabe's Test Fallback
When $L = 1$, substitute the failing value of $x$ back into the terms and evaluate:

$$\lim_{n \to \infty} n \left( \frac{u_n}{u_{n+1}} - 1 \right) = l$$

- Convergent if $l > 1$.
- Divergent if $l < 1$.

---

## 3. THE ALGORITHM

### Step 1: Extract the General Term
Define $u_n$ from the given summation notation.

### Step 2: Extract the Successor Term
Find $u_{n+1}$ by changing every $n$ to $(n+1)$. Remember to expand factorials and product chains to include their next natural terms.

### Step 3: Run the Ratio Test
Set up $\lim_{n \to \infty} \frac{u_{n+1}}{u_n}$ and simplify it by canceling common terms. This will leave an expression containing $x$.

### Step 4: State Conditional Convergence
Set the simplified limit expression $< 1$ for convergence and $> 1$ for divergence. Isolate $x$ to find the intervals.

### Step 5: Isolate the Failure Point
Set the limit expression exactly equal to $1$ to find the specific value of $x$ where D'Alembert's test fails.

### Step 6: Execute Raabe's Test at the Failure Point
Substitute this specific value of $x$ into your simplified expression for $\frac{u_n}{u_{n+1}}$, plug it into the Raabe formula, compute the limit as $n \to \infty$, and apply the decision rules.

---

## 4. THE MECHANICS

### Core Operations Explained
- **Factorial Expansion**: The term $n!$ represents $1 \cdot 2 \cdot 3 \dots n$. Therefore, its successor $(n+1)!$ can be written as $n! \cdot (n+1)$. This allows $n!$ to be completely canceled during division.
- **Product Chain Expansion**: The numerator chain grows by adding $3$ to each successive term ($4, 7, 10...$). The last term is $3n+1$. The next term after it is obtained by replacing $n$ with $n+1$:
$$3(n+1) + 1 = 3n + 3 + 1 = 3n + 4$$
- **Variable Power Split**: The term $x^{n+1}$ can be split algebraically using exponent laws:
$$x^{n+1} = x^n \cdot x^1$$
This allows $x^n$ to cancel out, leaving a single $x$ in the ratio.

### Full Mechanics Walkthrough: Problem Solving
Consider the series:
$$\sum \frac{4 \cdot 7 \dots (3n+1)x^n}{n!}$$

The general term $u_n$ is defined as:
$$u_n = \frac{4 \cdot 7 \dots (3n+1)x^n}{n!}$$

The successor term $u_{n+1}$ is constructed by appending the next elements in the patterns:
$$u_{n+1} = \frac{4 \cdot 7 \dots (3n+1)(3n+4)x^{n+1}}{(n+1)!}$$

Set up the standard ratio test limit expression:
$$\lim_{n \to \infty} \frac{u_{n+1}}{u_n} = \lim_{n \to \infty} \frac{\frac{4 \cdot 7 \dots (3n+1)(3n+4)x^{n+1}}{(n+1)!}}{\frac{4 \cdot 7 \dots (3n+1)x^n}{n!}}$$

Convert the division into direct multiplication by using the reciprocal:
$$\lim_{n \to \infty} \frac{4 \cdot 7 \dots (3n+1)(3n+4)x^n \cdot x}{n! \cdot (n+1)} \times \frac{n!}{4 \cdot 7 \dots (3n+1)x^n}$$

Cancel all matching terms ($4 \dots (3n+1)$, $n!$, and $x^n$) appearing simultaneously across the fractions:
$$\lim_{n \to \infty} \frac{(3n+4)x}{n+1}$$

Factor out the variable $n$ from both the numerator and denominator structures:
$$\lim_{n \to \infty} \frac{n\left(3 + \frac{4}{n}\right)x}{n\left(1 + \frac{1}{n}\right)}$$

Cancel the isolated factor $n$ from the ratio expression:
$$\lim_{n \to \infty} \frac{\left(3 + \frac{4}{n}\right)x}{1 + \frac{1}{n}}$$

Apply the limit condition values as $n$ goes to infinity:
$$\frac{(3 + 0)x}{1 + 0} = 3x$$

Apply D'Alembert's conditional decision rules:
- The series is **convergent** if $3x < 1$, which means $x < \frac{1}{3}$.
- The series is **divergent** if $3x > 1$, which means $x > \frac{1}{3}$.
- The test **fails** if $3x = 1$, which means $x = \frac{1}{3}$.

To resolve the failure point, look back at the ratio of terms. Since $\frac{u_{n+1}}{u_n} = \frac{3n+4}{n+1}x$, substitute $x = \frac{1}{3}$ into it:
$$\frac{u_{n+1}}{u_n} = \frac{3n+4}{n+1} \cdot \frac{1}{3} = \frac{3n+4}{3n+3}$$

Invert this expression to find the required value for Raabe's Test:
$$\frac{u_n}{u_{n+1}} = \frac{3n+3}{3n+4}$$

Initiate the Raabe's Test process using this inverted term:
$$\lim_{n \to \infty} n \left( \frac{3n+3}{3n+4} - 1 \right)$$

Find a common denominator to combine the components inside the parentheses:
$$\lim_{n \to \infty} n \left( \frac{(3n+3) - (3n+4)}{3n+4} \right)$$

Simplify the numerator expression by distributing the negative sign:
$$\lim_{n \to \infty} n \left( \frac{3n + 3 - 3n - 4}{3n+4} \right)$$

Combine constants to simplify the remaining expression values:
$$\lim_{n \to \infty} n \left( \frac{-1}{3n+4} \right)$$

Multiply the external factor $n$ into the fractional expression:
$$\lim_{n \to \infty} \frac{-n}{3n+4}$$

Factor out $n$ from the terms located in the denominator:
$$\lim_{n \to \infty} \frac{-n}{n\left(3 + \frac{4}{n}\right)}$$

Cancel out the variable $n$ present across both fields:
$$\lim_{n \to \infty} \frac{-1}{3 + \frac{4}{n}}$$

Apply the final limit condition boundaries to resolve the constant expression:
$$\frac{-1}{3 + 0} = -\frac{1}{3}$$

Compare the final result against the Raabe decision threshold rule:
$$-\frac{1}{3} < 1$$

Since the computed limit value satisfies $l < 1$, the series is **divergent** at $x = \frac{1}{3}$.

### Final Summary of Convergence Conditions
$$\text{Convergent if: } x < \frac{1}{3}$$
$$\text{Divergent if: } x \ge \frac{1}{3}$$
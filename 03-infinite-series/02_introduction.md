# Engineering Mathematics Study Notes: Boundedness and Convergence Behavior

## 1. Concept Identification
The notes introduce how sequences behave as they expand indefinitely, categorized into two main properties:
* **Boundedness**: Determining if a sequence is trapped within real boundaries (Upper and Lower bounds).
* **Convergence Behavior**: Evaluating what happens to the value of the $n$-th term ($u_n$) as $n$ approaches infinity ($\infty$). This divides sequences into three types:
  1. **Convergent**: Headed toward a single, fixed real number.
  2. **Divergent**: Exploding toward positive infinity ($+\infty$) or negative infinity ($-\infty$).
  3. **Oscillatory**: Bouncing back and forth between different values without settling down.

---

## 2. Mathematical Representations

### Boundedness Thresholds
A sequence is **bounded below** if every term is greater than or equal to a lower bound $k$:
$$u_n \geq k \quad \forall \ n \in \mathbb{N}$$

A sequence is **bounded above** if every term is less than or equal to an upper bound $K$:
$$u_n \leq K \quad \forall \ n \in \mathbb{N}$$

A sequence is strictly bounded if it has both a lower bound and an upper bound:
$$k \leq u_n \leq K$$

### Convergence Criterion
A sequence **converges** if its limit as $n$ goes to infinity equals a definitive, single **finite** number $L$:
$$\lim_{n \to \infty} u_n = L \quad (\text{where } L \text{ is finite and unique})$$

### Divergence Criterion
A sequence **diverges** if its values increase or decrease without limit:
$$\lim_{n \to \infty} u_n = \pm\infty$$

### Limit Inversion Property
When evaluating limits at infinity, any constant divided by an infinitely large number mechanical collapses to zero:
$$\lim_{n \to \infty} \frac{1}{n} = 0$$

---

## 3. The Algorithm (Procedural Recipe)

To evaluate the convergence behavior of a fractional rational sequence ($u_n = \frac{P(n)}{Q(n)}$) as shown on the board, apply this algebraic recipe:

### Step 1: Identify the Highest Power of $n$
Look at both the numerator and denominator expressions and find the highest power of the variable $n$.

### Step 2: Factor Out $n$ Forcefully
Pull out that highest power of $n$ from every term in the numerator and denominator to create terms of the form $\frac{\text{constant}}{n}$.

### Step 3: Cancel Common Factors
Algebraically cross out the matching $n$ terms outside the parentheses from the top and bottom.

### Step 4: Apply the Limit ($\infty$) Conversion
Substitute $\infty$ into the remaining $n$ variables, converting all fraction components of $\frac{\text{constant}}{\infty}$ explicitly into $0$.

### Step 5: Classify the System Behavior
* If the result is a clean, single finite number, label it **Convergent**.
* If the result is $\pm\infty$, label it **Divergent**.
* If it alternates between values, label it **Oscillatory**.

---

## 4. Operational Mechanics

### Mechanical Example 1: Understanding Boundedness
The board displays three basic numeric frameworks to show how bounds function:

**Case A: Bounded Below Only**
The sequence is given as: $1, 2, 3, 4, 5, \dots$
The sequence starts at $1$ and grows larger forever. It has a floor but no ceiling.
$$u_n \geq 1$$
Therefore, the lower bound is $1$.

**Case B: Bounded Above Only**
The sequence formula is $u_n = -n$, yielding: $-1, -2, -3, -4, -5, \dots$
The sequence starts at $-1$ and drops smaller forever. It has a ceiling but no floor.
$$u_n \leq -1$$
Therefore, the upper bound is $-1$.

**Case C: Fully Bounded**
The sequence is given as: $1, \frac{1}{2}, \frac{1}{3}, \frac{1}{4}, \dots$
Let's look at the boundaries:
* The first term is $1$ (it never gets higher than this).
* As $n$ grows, the fraction gets closer and closer to $0$ (it never drops below or touches $0$).
$$0 < u_n \leq 1$$
Lower Bound = $0$, Upper Bound = $1$. The sequence is fully trapped.

### Mechanical Example 2: Solving a Convergent Rational Limit
Let's mechanically solve the problem from the board:
$$u_n = \frac{3n + 2}{n + 5}$$

Apply Step 2 by pulling out the highest power of $n$ (which is $n^1$) from both the top and the bottom expressions:
$$u_n = \frac{n \cdot \left(3 + \frac{2}{n}\right)}{n \cdot \left(1 + \frac{5}{n}\right)}$$

Cancel the matching $n$ terms from the top and bottom:
$$u_n = \frac{3 + \frac{2}{n}}{1 + \frac{5}{n}}$$

Apply the limit process by letting $n \to \infty$:
$$\lim_{n \to \infty} u_n = \frac{3 + \frac{2}{\infty}}{1 + \frac{5}{\infty}}$$

Convert the infinite fractions directly to $0$:
$$\lim_{n \to \infty} u_n = \frac{3 + 0}{1 + 0} = 3$$

Because $3$ is a clean, unique finite value, the sequence is **Convergent**.

### Mechanical Example 3: Solving a Divergent Limit
Let's mechanically evaluate the second example shown on the board:
$$u_n = n^3$$

Apply the limit directly to the term as $n$ grows infinitely large:
$$\lim_{n \to \infty} n^3 = (\infty)^3 = \infty$$

Because the value escapes to infinity, the sequence is classified as **Divergent**.

### Mechanical Example 4: Identifying Oscillatory Behavior
The lecturer writes down a sequence alternating signs: $1, -1, 1, -1, 1, \dots$

Let's look at the value behavior based on whether the term position ($n$) is odd or even:
$$u_n = 1 \quad (\text{when } n \text{ is Odd})$$

$$u_n = -1 \quad (\text{when } n \text{ is Even})$$

When you apply a limit to infinity, you cannot predict whether the destination index is odd or even. Because it yields two entirely different values ($1$ and $-1$), the limit has a **not unique value**. It is classified as **Oscillatory**.
# Engineering Mathematics Study Notes: Geometric Series Test

## 1. Concept Identification
The notes introduce the **Geometric Series Test**, which is a direct, inspection-based test used to determine the convergence or divergence of an infinite series where each consecutive term is found by multiplying the previous term by a fixed, constant multiplier called the **common ratio**.

---

## 2. Mathematical Representations

### Standard Form of a Geometric Series
An infinite geometric series is written algebraically as:
$$\sum_{n=0}^{\infty} a \cdot r^n = a + ar + ar^2 + ar^3 + \dots + ar^n + \dots$$

Where:
* $a$ is the first term of the series ($a \neq 0$).
* $r$ is the constant common ratio between consecutive terms.

### The Geometric Series Convergence Criteria
The absolute value of the common ratio, denoted as $|r|$, completely dictates the behavior of the infinite sum:
$$\text{If } |r| < 1 \implies \text{The series is Convergent}$$

$$\text{If } |r| \geq 1 \implies \text{The series is Divergent}$$

### Sum of an Infinite Convergent Geometric Series
If a geometric series satisfies the convergence condition ($|r| < 1$), its total infinite summation value settles exactly on a finite value calculated by:
$$S_{\infty} = \frac{a}{1 - r}$$

---

## 3. The Algorithm (Procedural Recipe)

To evaluate an infinite series using the Geometric Series framework from absolute first principles, execute these steps mechanically:

### Step 1: Extract Individual Terms
Expand the summation notation to list out the first three or four sequential terms of the numerical series explicitly.

### Step 2: Determine the First Term ($a$)
Identify the very first numeric term in the expanded progression and assign it to the variable $a$.
$$a = \text{Term } 1$$

### Step 3: Compute the Common Ratio ($r$)
Divide any term by its immediate predecessor to find the constant multiplier value $r$:
$$r = \frac{\text{Term } 2}{\text{Term } 1} = \frac{\text{Term } 3}{\text{Term } 2}$$

### Step 4: Apply the Absolute Value Condition
Find the positive magnitude of the common ratio ($|r|$) and check it against the threshold value of $1$.

### Step 5: Classify the Convergence Behavior
* If the absolute value is strictly less than $1$, write **"Convergent"** and proceed to Step 6.
* If the absolute value is greater than or equal to $1$, write **"Divergent"** and terminate the procedure.

### Step 6: Compute the Final Sum (Only if Convergent)
Substitute the values of $a$ and $r$ into the infinite sum formula to resolve the final numeric value of the entire infinite addition.

---

## 4. Operational Mechanics



### Mechanical Example 1: Solving a Fractional Decreasing Geometric Series
Let's solve the primary example presented across the lecture boards:
$$\text{Test the series: } 1 + \frac{1}{3} + \frac{1}{9} + \frac{1}{27} + \dots \infty$$

**Step 1: Extract parameter $a$**
Look at the beginning of the series expression:
$$a = 1$$

**Step 2: Calculate parameter $r$**
Divide the second term by the first term:
$$r = \frac{\frac{1}{3}}{1} = \frac{1}{3}$$

Let's verify this remains constant by checking the next pair:
$$r = \frac{\frac{1}{9}}{\frac{1}{3}} = \frac{1}{9} \times \frac{3}{1} = \frac{3}{9} = \frac{1}{3}$$

The common ratio is verified mechanically as $r = \frac{1}{3}$.

**Step 3: Test the stability condition**
Take the absolute value of our ratio:
$$|r| = \left| \frac{1}{3} \right| = \frac{1}{3}$$

Compare this fraction directly against $1$:
$$\frac{1}{3} < 1 \implies \text{The series is Convergent}$$

**Step 4: Compute the final infinite sum**
Since the series is confirmed to be convergent, compute its exact total final value:
$$S_{\infty} = \frac{1}{1 - \frac{1}{3}}$$

Simplify the denominator expression ($1 - \frac{1}{3} = \frac{2}{3}$):
$$S_{\infty} = \frac{1}{\frac{2}{3}}$$

Multiply by the reciprocal of the denominator fraction to find the final evaluation:
$$S_{\infty} = 1 \times \frac{3}{2} = \frac{3}{2}$$

---

### Mechanical Example 2: Recognizing a Divergent Geometric Series
Consider a series where terms grow larger over time:
$$\text{Test the series: } 2 + 4 + 8 + 16 + 32 + \dots \infty$$

**Step 1: Extract parameter $a$**
$$a = 2$$

**Step 2: Calculate parameter $r$**
Divide the second term by the first term:
$$r = \frac{4}{2} = 2$$

**Step 3: Test the stability condition**
Take the absolute value of our ratio:
$$|r| = |2| = 2$$

Compare this value directly against the divergent threshold:
$$2 \geq 1 \implies \text{The series is Divergent}$$

The terms grow infinitely large, meaning the total sum escapes to infinity. No summation calculation can be performed.
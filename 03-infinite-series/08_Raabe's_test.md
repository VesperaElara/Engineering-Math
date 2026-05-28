# Engineering Mathematics Study Notes: Raabe's Test

## 1. IDENTIFY
The mathematical concept presented on the board is **Raabe's Test**. It is a higher-order convergence test used for infinite series of positive terms. It is primarily executed as a fallback verification when **D'Alembert's Ratio Test** fails because the ratio limit evaluates exactly to $1$.

---

## 2. THE FORMULA
Let $\sum u_n$ be an infinite series consisting entirely of positive terms. Raabe's Test requires calculating the limit value $l$ using the following expression:

$$\lim_{n \to \infty} n \left( \frac{u_n}{u_{n+1}} - 1 \right) = l$$

The behavior of the infinite series is evaluated based on the numerical value of $l$:

1. The series $\sum u_n$ is **convergent** if:
$$l > 1$$

2. The series $\sum u_n$ is **divergent** if:
$$l < 1$$

3. The test **fails** to provide a conclusion if:
$$l = 1$$

---

## 3. THE ALGORITHM
This systematic blueprint outlines how to solve convergence problems when basic ratio tests fail.

### Step 1: Establish the General Term
Identify the algebraic rule for the $n$-th term of the given series, designated as $u_n$.

### Step 2: Establish the Successor Term
Obtain the $(n+1)$-th term, designated as $u_{n+1}$, by substituting every instance of $n$ in $u_n$ with $(n+1)$.

### Step 3: Attempt the Base Ratio Test
Set up and compute the limit of the term ratio as $n$ approaches infinity to verify if Raabe's Test is required.

$$\lim_{n \to \infty} \frac{u_{n+1}}{u_n}$$

If this evaluates to $1$, the standard test fails, creating a direct dependency on Raabe's Test.

### Step 4: Construct the Raabe Ratio
Invert the calculated ratio fraction to get $\frac{u_n}{u_{n+1}}$, subtract $1$ from it, and multiply the entire expression by $n$.

### Step 5: Compute the Limit
Evaluate the limit of the new expression as $n \to \infty$.

$$l = \lim_{n \to \infty} n \left( \frac{u_n}{u_{n+1}} - 1 \right)$$

### Step 6: Apply the Decision Rule
Compare the computed value of $l$ against the reference threshold of $1$ to conclude whether the series converges or diverges.

---

## 4. THE MECHANICS

### Core Operations Explained
- **Term Substitution**: To transition from $u_n$ to $u_{n+1}$, wrap $(n+1)$ in parentheses wherever $n$ appears. For example, if a term is $2n$, its successor is $2(n+1) = 2n + 2$. If a term is $2n-1$, its successor is $2(n+1)-1 = 2n + 2 - 1 = 2n + 1$.
- **Fraction Division via Multiplication**: Dividing by a fraction is achieved by multiplying by its reciprocal.
$$\frac{A}{B} \div \frac{C}{D} = \frac{A}{B} \times \frac{D}{C}$$
- **Factorial-Style Product Cancellation**: In series containing expanding products of numbers like $1 \cdot 3 \cdot 5 \dots (2n-1)$, the terms in $u_{n+1}$ contain all factors of $u_n$ plus an additional trailing term. When computing ratios, all common matching front factors cancel out completely, leaving only the individual trailing elements.
- **Infinity Limit Mechanism**: To evaluate limits where $n \to \infty$, factor out the highest power of $n$ from both the numerator and denominator to isolate expressions of the form $\frac{k}{n}$. As $n$ becomes infinitely large, any term divided by $n$ becomes $0$.
$$\lim_{n \to \infty} \frac{1}{n} = 0$$

### Full Mechanics Walkthrough: Problem 1
Consider the series:
$$\sum \frac{1}{n^2}$$

The general term $u_n$ is defined as:
$$u_n = \frac{1}{n^2}$$

The successor term $u_{n+1}$ is constructed by replacing $n$ with $n+1$:
$$u_{n+1} = \frac{1}{(n+1)^2}$$

Evaluate the standard limit ratio of the successor term to the general term:
$$\lim_{n \to \infty} \frac{u_{n+1}}{u_n} = \lim_{n \to \infty} \frac{\frac{1}{(n+1)^2}}{\frac{1}{n^2}}$$

Convert the fraction division into a reciprocal multiplication step:
$$\lim_{n \to \infty} \frac{1}{(n+1)^2} \times n^2 = \lim_{n \to \infty} \frac{n^2}{(n+1)^2}$$

Factor out $n$ from the base expression within the denominator:
$$\lim_{n \to \infty} \frac{n^2}{n^2 \left(1 + \frac{1}{n}\right)^2}$$

Cancel out the common $n^2$ variable shared between numerator and denominator:
$$\lim_{n \to \infty} \frac{1}{\left(1 + \frac{1}{n}\right)^2}$$

Substitute the limit variable boundary values into the expression:
$$\frac{1}{\left(1 + \frac{1}{\infty}\right)^2} = \frac{1}{(1 + 0)^2} = 1$$

Because the limit equals $1$, D'Alembert's Ratio Test fails. Transition to the Raabe's Test formula:
$$\lim_{n \to \infty} n \left( \frac{u_n}{u_{n+1}} - 1 \right)$$

Substitute the explicit definitions of $u_n$ and $u_{n+1}$ into the test:
$$\lim_{n \to \infty} n \left( \frac{\frac{1}{n^2}}{\frac{1}{(n+1)^2}} - 1 \right)$$

Simplify the internal complex fraction inside the parentheses:
$$\lim_{n \to \infty} n \left( \frac{(n+1)^2}{n^2} - 1 \right)$$

Expand the squared binomial expression located in the numerator:
$$\lim_{n \to \infty} n \left( \frac{n^2 + 2n + 1}{n^2} - 1 \right)$$

Combine the terms across a unified common denominator:
$$\lim_{n \to \infty} n \left( \frac{n^2 + 2n + 1 - n^2}{n^2} \right)$$

Simplify the terms inside the numerator by canceling out $n^2$:
$$\lim_{n \to \infty} n \left( \frac{2n + 1}{n^2} \right)$$

Multiply the outer factor $n$ directly into the internal fraction numerator:
$$\lim_{n \to \infty} \frac{n(2n + 1)}{n^2}$$

Distribute $n$ or cancel one factor of $n$ from the denominator:
$$\lim_{n \to \infty} \frac{2n + 1}{n}$$

Split the fraction into individual component terms:
$$\lim_{n \to \infty} \left( 2 + \frac{1}{n} \right)$$

Evaluate the limit explicitly as $n$ approaches infinity:
$$2 + 0 = 2$$

Since the final limit value $l = 2$, which satisfies $l > 1$, the series is **convergent**.

### Full Mechanics Walkthrough: Problem 2
Consider the series:
$$\frac{1}{2} + \frac{1 \cdot 3}{2 \cdot 4} + \frac{1 \cdot 3 \cdot 5}{2 \cdot 4 \cdot 6} + \dots$$

The general term $u_n$ representing the pattern of the product sequence is:
$$u_n = \frac{1 \cdot 3 \cdot 5 \dots (2n-1)}{2 \cdot 4 \cdot 6 \dots 2n}$$

The successor term $u_{n+1}$ includes the next sequence terms:
$$u_{n+1} = \frac{1 \cdot 3 \cdot 5 \dots (2n-1)(2n+1)}{2 \cdot 4 \cdot 6 \dots 2n(2n+2)}$$

Set up the standard ratio test limit expression:
$$\lim_{n \to \infty} \frac{u_{n+1}}{u_n} = \lim_{n \to \infty} \frac{\frac{1 \cdot 3 \cdot 5 \dots (2n-1)(2n+1)}{2 \cdot 4 \cdot 6 \dots 2n(2n+2)}}{\frac{1 \cdot 3 \cdot 5 \dots (2n-1)}{2 \cdot 4 \cdot 6 \dots 2n}}$$

Convert the division into direct multiplication by using the reciprocal:
$$\lim_{n \to \infty} \frac{1 \cdot 3 \cdot 5 \dots (2n-1)(2n+1)}{2 \cdot 4 \cdot 6 \dots 2n(2n+2)} \times \frac{2 \cdot 4 \cdot 6 \dots 2n}{1 \cdot 3 \cdot 5 \dots (2n-1)}$$

Cancel all matching terms appearing simultaneously in numerators and denominators:
$$\lim_{n \to \infty} \frac{2n+1}{2n+2}$$

Factor out the variable $n$ from both components to prepare for infinity evaluation:
$$\lim_{n \to \infty} \frac{n \left(2 + \frac{1}{n}\right)}{n \left(2 + \frac{2}{n}\right)}$$

Cancel the isolated factor $n$ from the ratio expression:
$$\lim_{n \to \infty} \frac{2 + \frac{1}{n}}{2 + \frac{2}{n}}$$

Apply the limit condition values as $n$ goes to infinity:
$$\frac{2 + \frac{1}{\infty}}{2 + \frac{2}{\infty}} = \frac{2 + 0}{2 + 0} = 1$$

The ratio test value equals $1$, confirming a test failure. Initiate the Raabe's Test process:
$$\lim_{n \to \infty} n \left( \frac{u_n}{u_{n+1}} - 1 \right)$$

Substitute the reciprocal of the simplified ratio term directly into the test:
$$\lim_{n \to \infty} n \left( \frac{2n+2}{2n+1} - 1 \right)$$

Find a common denominator to unify the elements inside the bracket:
$$\lim_{n \to \infty} n \left( \frac{(2n+2) - (2n+1)}{2n+1} \right)$$

Simplify the numerator expression by distributing the negative sign:
$$\lim_{n \to \infty} n \left( \frac{2n + 2 - 2n - 1}{2n+1} \right)$$

Combine constants to simplify the remaining expression values:
$$\lim_{n \to \infty} n \left( \frac{1}{2n+1} \right)$$

Multiply the external factor $n$ into the fractional expression:
$$\lim_{n \to \infty} \frac{n}{2n+1}$$

Factor out $n$ from the expression terms located in the denominator:
$$\lim_{n \to \infty} \frac{n}{n \left(2 + \frac{1}{n}\right)}$$

Cancel out the variable $n$ present across both fields:
$$\lim_{n \to \infty} \frac{1}{2 + \frac{1}{n}}$$

Apply the final limit condition boundaries to resolve the constant expression:
$$\frac{1}{2 + \frac{1}{\infty}} = \frac{1}{2 + 0} = \frac{1}{2}$$

Compare the result against the decision criterion rule:
$$\frac{1}{2} < 1$$

Since the computed limit value satisfies $l < 1$, the series is definitively **divergent**.
# Engineering Mathematics Study Notes: Sequences and Series

## 1. Concept Identification
The provided notes introduce the fundamental building blocks of Real Analysis and Infinite Series Calculus:
* **Sequence**: A function whose domain is the set of positive integers.
* **Series**: The algebraic sum of the terms of a sequence.
* **Sequence of Partial Sums ($S_n$)**: A secondary sequence constructed to analyze the convergence behavior of an infinite series.
* **Monotonic Sequence**: A sequence that consistently moves in a single directional trend—either entirely non-decreasing or entirely non-increasing.

---

## 2. Mathematical Representations

### Definition of a Sequence
A sequence is denoted mathematically as:
$$\{u_n\}_{n=1}^{\infty} = \{u_1, u_2, u_3, \dots, u_n, \dots\}$$

### Definition of an Infinite Series
The infinite summation of the sequence terms is written as:
$$S_n = \sum_{n=1}^{\infty} u_n = u_1 + u_2 + u_3 + \dots + u_n + \dots + \infty$$

### Sequence of Partial Sums
The partial sums are generated recursively:
$$S_1 = u_1$$

$$S_2 = u_1 + u_2$$

$$S_3 = u_1 + u_2 + u_3$$

$$S_n = u_1 + u_2 + \dots + u_n = \sum_{i=1}^{n} u_i$$

### Conditions for Monotonicity
For a sequence to be classified as monotonic increasing:
$$u_{n+1} \geq u_n$$

For a sequence to be classified as monotonic decreasing:
$$u_{n+1} \leq u_n$$

---

## 3. The Algorithm (Procedural Recipe)

To analyze an arithmetic progression sequence and determine its general term ($u_n$ or $t_n$) as shown in the lecture, execute these procedural steps:

### Step 1: Identify the Sequence Type
Examine the given list of numbers to determine if the difference between consecutive terms is constant.
$$d = u_{n+1} - u_n$$

### Step 2: Extract Key Parameters
Identify the first term ($a$) and calculate the common difference ($d$).
$$a = u_1$$

$$d = u_2 - u_1$$

### Step 3: Substitute into the General Term Formula
Plug the extracted parameters $a$ and $d$ into the Arithmetic Progression general term formula:
$$t_n = a + (n - 1)d$$

### Step 4: Simplify Symbolically
Expand the algebraic expression and collect like terms to arrive at the final simplified formula for the $n$-th term.

---

## 4. Operational Mechanics

### Mechanical Example 1: Finding the General Term ($t_n$)
The whiteboard shows an example sequence: $1, 3, 5, 7, 9, \dots$

Identify the first term:
$$a = 1$$

Calculate the constant difference between adjacent elements ($3-1$, $5-3$, $7-5$):
$$d = 2$$

Apply the general formula:
$$t_n = 1 + (n - 1)2$$

Distribute the constant multiplier $2$ across the parenthesis:
$$t_n = 1 + 2n - 2$$

Combine the constants ($1 - 2$):
$$t_n = 2n - 1$$

### Mechanical Example 2: Understanding Partial Sums
An infinite series adds terms infinitely, which is mechanically impossible to compute directly. Instead, we compute finite chunks called "Partial Sums".

Given the sequence terms generated above ($u_n = 2n-1$):
$$u_1 = 1, \quad u_2 = 3, \quad u_3 = 5$$

Compute the first partial sum:
$$S_1 = u_1 = 1$$

Compute the second partial sum:
$$S_2 = u_1 + u_2 = 1 + 3 = 4$$

Compute the third partial sum:
$$S_3 = u_1 + u_2 + u_3 = 1 + 3 + 5 = 9$$

The behavior of this new sequence of totals ($\{1, 4, 9, \dots\}$) dictates whether the entire infinite addition approaches a stable finite number or escapes to infinity.

### Mechanical Example 3: Verifying Monotonicity
To determine if a sequence is monotonic, compare any arbitrary term $u_n$ to its immediate successor $u_{n+1}$.

Consider the sequence from the board: $1, 3, 5, 7, \dots$
$$u_1 = 1, \quad u_2 = 3$$

Evaluate the inequality:
$$3 \geq 1 \implies u_2 \geq u_1$$

Since every subsequent term is greater than or equal to the preceding term ($u_{n+1} \geq u_n$), the sequence is mechanically verified as **monotonic increasing**.

Consider a fractional sequence from the board: $1, \frac{1}{2}, \frac{1}{3}, \frac{1}{4}, \dots$
$$u_1 = 1, \quad u_2 = 0.5$$

Evaluate the inequality:
$$0.5 \leq 1 \implies u_2 \leq u_1$$

Since every subsequent term is smaller than or equal to the preceding term ($u_{n+1} \leq u_n$), the sequence is mechanically verified as **monotonic decreasing**.
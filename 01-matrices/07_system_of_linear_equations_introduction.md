# Engineering Mathematics: System of Linear Equations

## 1. Introduction to Matrix Representation
A system of linear equations involves multiple equations with shared variables. To solve these efficiently, we translate the algebraic form into a matrix equation.

### Algebraic Form
$$
a_{1}x + b_{1}y + c_{1}z = d_{1}
$$
$$
a_{2}x + b_{2}y + c_{2}z = d_{2}
$$
$$
a_{3}x + b_{3}y + c_{3}z = d_{3}
$$

### Matrix Form ($AX = B$)

The system is represented as:
```math
\begin{bmatrix}
a_{1} & b_{1} & c_{1} \\
a_{2} & b_{2} & c_{2} \\
a_{3} & b_{3} & c_{3}
\end{bmatrix}
\begin{bmatrix}
x \\
y \\
z
\end{bmatrix}
=
\begin{bmatrix}
d_{1} \\
d_{2} \\
d_{3}
\end{bmatrix}
```

*   **A (Coefficient Matrix):** Contains the coefficients of the variables.
*   **X (Variable Matrix):** A column matrix of the unknowns ($x, y, z$).
*   **B (Constant Matrix):** A column matrix of the constants on the right-hand side.

---

## 2. Classification of Systems
Based on the constant matrix ($B$), systems are classified into two types:

1.  **Non-Homogeneous System:** $B \neq 0$ (at least one constant is non-zero).
2.  **Homogeneous System:** $B = 0$ (all constants are zero, represented as $AX = 0$).

---

## 3. The Augmented Matrix $[A|B]$
To analyze and solve the system, we combine Matrix $A$ and Matrix $B$ into a single structure called the **Augmented Matrix**. This allows us to perform row operations on the entire system simultaneously.

$$
[A|B] = 
\begin{bmatrix}
a_{1} & b_{1} & c_{1} & | & d_{1} \\
a_{2} & b_{2} & c_{2} & | & d_{2} \\
a_{3} & b_{3} & c_{3} & | & d_{3}
\end{bmatrix}
$$

---

## 4. Consistency and Types of Solutions
A system is **Consistent** if at least one solution exists, and **Inconsistent** if no solution exists.

| Condition (for 2 variables) | Algebraic Meaning | Solution Type |
| :--- | :--- | :--- |
| $\frac{a_1}{a_2} \neq \frac{b_1}{b_2}$ | Lines intersect at one point | **Unique Solution** |
| $\frac{a_1}{a_2} = \frac{b_1}{b_2} \neq \frac{c_1}{c_2}$ | Lines are parallel | **No Solution** |
| $\frac{a_1}{a_2} = \frac{b_1}{b_2} = \frac{c_1}{c_2}$ | Lines are coincident (overlap) | **Infinite Solutions** |

---

## 5. Step-by-Step Transformation Example
We use Elementary Row Operations (ERO) to transform the Augmented Matrix into Row Echelon Form to find the solution.

**Goal:** Solve the system by creating zeros in the lower triangle.

### Initial Augmented Matrix
$$
\begin{bmatrix}
1 & 2 & 3 & | & 14 \\
0 & 1 & 2 & | & 8 \\
2 & 4 & 7 & | & 31
\end{bmatrix}
(R_{3} \rightarrow R_{3} - 2R_{1}) \longrightarrow
\begin{bmatrix}
1 & 2 & 3 & | & 14 \\
0 & 1 & 2 & | & 8 \\
0 & 0 & 1 & | & 3
\end{bmatrix}
$$

### Back-Substitution Logic
Once in Echelon form, we solve from the bottom up:
1.  From $R_{3}$: $1z = 3 \implies z = 3$
2.  From $R_{2}$: $y + 2z = 8 \implies y + 2(3) = 8 \implies y = 2$
3.  From $R_{1}$: $x + 2y + 3z = 14 \implies x + 2(2) + 3(3) = 14 \implies x = 1$

**Solution:** $(x, y, z) = (1, 2, 3)$

---
## Working Rule for Consistency of Linear Equations

1. **Represent the System:** 
   Let the given system of linear equations be represented in matrix form as:
   $$AX = B \quad \dots (1)$$

2. **Form the Augmented Matrix:** 
   Find the augmented matrix $[A|B]$ for the system (1).

3. **Row Reduction:** 
   Transform the augmented matrix $[A|B]$ into **Echelon Form**. Once in echelon form, observe the rank of the coefficient matrix $A$, denoted as $\rho(A)$, and the rank of the augmented matrix $[A|B]$, denoted as $\rho(A|B)$.

4. **Consistency Analysis:**

   *   **Case 1: Inconsistent System**
       If $\text{Rank}(A) \neq \text{Rank}(A|B)$, the system is **inconsistent** and has **no solution**.

   *   **Case 2: Consistent with Unique Solution**
       If $\text{Rank}(A) = \text{Rank}(A|B) = n$ (where $n$ is the number of unknown variables), the system is **consistent** and has a **unique solution**.

   *   **Case 3: Consistent with Infinite Solutions**
       If $\text{Rank}(A) = \text{Rank}(A|B) = r < n$ (where $n$ is the number of variables), the system is **consistent** and has **infinitely many solutions**.
       * In this case, $(n - r)$ variables must be chosen arbitrarily.

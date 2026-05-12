# Engineering Mathematics: Analysis of Linear Systems with Parameters

Determine the values of $\lambda$ and $\mu$ that result in different solution types.

## 1. Problem Setup

The system of equations is:
1. $x + y + z = 6$
2. $x + 2y + 3z = 10$
3. $x + 2y + \lambda z = \mu$

### Augmented Matrix $[A|B]$
$$
\begin{bmatrix}
1 & 1 & 1 & 6 \\
1 & 2 & 3 & 10 \\
1 & 2 & \lambda & \mu
\end{bmatrix}
$$

---

## 2. Row Transformations

We reduce the matrix to Row Echelon Form (REF) to analyze the consistency.

### Step 1: Eliminate $x$ from $R_2$ and $R_3$
$$
\begin{bmatrix}
1 & 1 & 1 & 6 \\
1 & 2 & 3 & 10 \\
1 & 2 & \lambda & \mu
\end{bmatrix} (R_2 \to R_2 - R_1, R_3 \to R_3 - R_1) \longrightarrow \begin{bmatrix}
1 & 1 & 1 & 6 \\
0 & 1 & 2 & 4 \\
0 & 1 & \lambda - 1 & \mu - 6
\end{bmatrix}
$$

### Step 2: Eliminate $y$ from $R_3$
$$
\begin{bmatrix}
1 & 1 & 1 & 6 \\
0 & 1 & 2 & 4 \\
0 & 1 & \lambda - 1 & \mu - 6
\end{bmatrix} (R_3 \to R_3 - R_2) \longrightarrow \begin{bmatrix}
1 & 1 & 1 & 6 \\
0 & 1 & 2 & 4 \\
0 & 0 & \lambda - 3 & \mu - 10
\end{bmatrix}
$$

---

## 3. Parametric Analysis

The solution type depends on the final row: $0x + 0y + (\lambda - 3)z = (\mu - 10)$.

### Case 1: No Solutions
A system is inconsistent if the rank of the coefficient matrix $A$ is less than the rank of the augmented matrix $[A|B]$. This happens if the last row suggests $0 = \text{non-zero}$.
* **Condition:** $\lambda - 3 = 0$ AND $\mu - 10 \neq 0$
* **Result:** $\lambda = 3, \mu \neq 10$

### Case 2: One Solution (Unique)
A system has a unique solution if the rank of $A$ equals the rank of $[A|B]$ and equals the number of variables ($n=3$). This requires a non-zero pivot in every row of $A$.
* **Condition:** $\lambda - 3 \neq 0$
* **Result:** $\lambda \neq 3$ (Value of $\mu$ can be anything)

### Case 3: Infinite Solutions
A system has infinite solutions if $\rho(A) = \rho[A|B] < n$. This happens if the entire last row becomes zero.
* **Condition:** $\lambda - 3 = 0$ AND $\mu - 10 = 0$
* **Result:** $\lambda = 3, \mu = 10$

---

## 4. Summary Table

| Solution Type | Condition on $\lambda$ | Condition on $\mu$ |
| :--- | :--- | :--- |
| **No Solution** | $\lambda = 3$ | $\mu \neq 10$ |
| **Unique Solution** | $\lambda \neq 3$ | Any value |
| **Infinite Solutions** | $\lambda = 3$ | $\mu = 10$ |

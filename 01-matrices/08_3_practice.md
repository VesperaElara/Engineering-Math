# Engineering Mathematics: Solving Systems of Linear Equations (Fractional Form)

This note details the systematic solution of the linear system using the Augmented Matrix and Gaussian Elimination, prioritizing exact fractional arithmetic to avoid rounding errors.

## 1. Conceptual Framework

When solving for actual competence in CSE, maintaining precision is vital. Using fractions ensures that the logical flow remains mathematically rigorous.

### The Matrix Equation
$$AX = B$$
Where:
- **A** is the Coefficient Matrix.
- **X** is the Variable Matrix
```math
\begin{bmatrix} x \\ y \\ z \end{bmatrix}
```
- **B** is the Constant Matrix.

---

## 2. The Problem Statement

From the system provided:
1. $5x + 3y + 7z = 4$
2. $3x + 26y + 2z = 9$
3. $7x + 2y + 10z = 5$

### Step 1: Initialize the Augmented Matrix $[A|B]$
$$
\begin{bmatrix}
5 & 3 & 7 & 4 \\
3 & 26 & 2 & 9 \\
7 & 2 & 10 & 5
\end{bmatrix}
$$

---

## 3. Gaussian Elimination (Transforming to Row Echelon Form)

We will use Row Transformations to create zeros below the main diagonal.

### Operation 1: Create a Leading 1 in $R_1$
$$
\begin{bmatrix}
5 & 3 & 7 & 4 \\
3 & 26 & 2 & 9 \\
7 & 2 & 10 & 5
\end{bmatrix} \left(R_1 \to \frac{1}{5}R_1\right) \longrightarrow \begin{bmatrix}
1 & \frac{3}{5} & \frac{7}{5} & \frac{4}{5} \\
3 & 26 & 2 & 9 \\
7 & 2 & 10 & 5
\end{bmatrix}
$$

### Operation 2: Eliminate $x$ from $R_2$ and $R_3$
Calculations:
- $R_2: 26 - 3(\frac{3}{5}) = \frac{130-9}{5} = \frac{121}{5}$
- $R_2: 2 - 3(\frac{7}{5}) = \frac{10-21}{5} = -\frac{11}{5}$
- $R_2: 9 - 3(\frac{4}{5}) = \frac{45-12}{5} = \frac{33}{5}$
- $R_3: 2 - 7(\frac{3}{5}) = \frac{10-21}{5} = -\frac{11}{5}$
- $R_3: 10 - 7(\frac{7}{5}) = \frac{50-49}{5} = \frac{1}{5}$
- $R_3: 5 - 7(\frac{4}{5}) = \frac{25-28}{5} = -\frac{3}{5}$

$$
\begin{bmatrix}
1 & \frac{3}{5} & \frac{7}{5} & \frac{4}{5} \\
3 & 26 & 2 & 9 \\
7 & 2 & 10 & 5
\end{bmatrix} \left(R_2 \to R_2 - 3R_1, R_3 \to R_3 - 7R_1\right) \longrightarrow \begin{bmatrix}
1 & \frac{3}{5} & \frac{7}{5} & \frac{4}{5} \\
0 & \frac{121}{5} & -\frac{11}{5} & \frac{33}{5} \\
0 & -\frac{11}{5} & \frac{1}{5} & -\frac{3}{5}
\end{bmatrix}
$$

### Operation 3: Simplify $R_2$ (Pivot)
$$
\begin{bmatrix}
1 & \frac{3}{5} & \frac{7}{5} & \frac{4}{5} \\
0 & \frac{121}{5} & -\frac{11}{5} & \frac{33}{5} \\
0 & -\frac{11}{5} & \frac{1}{5} & -\frac{3}{5}
\end{bmatrix} \left(R_2 \to \frac{5}{121}R_2\right) \longrightarrow \begin{bmatrix}
1 & \frac{3}{5} & \frac{7}{5} & \frac{4}{5} \\
0 & 1 & -\frac{1}{11} & \frac{3}{11} \\
0 & -\frac{11}{5} & \frac{1}{5} & -\frac{3}{5}
\end{bmatrix}
$$

### Operation 4: Eliminate $y$ from $R_3$
Calculation for $R_3$:
- Column 3: $\frac{1}{5} + (\frac{11}{5})(-\frac{1}{11}) = \frac{1}{5} - \frac{1}{5} = 0$
- Column 4: $-\frac{3}{5} + (\frac{11}{5})(\frac{3}{11}) = -\frac{3}{5} + \frac{3}{5} = 0$

$$
\begin{bmatrix}
1 & \frac{3}{5} & \frac{7}{5} & \frac{4}{5} \\
0 & 1 & -\frac{1}{11} & \frac{3}{11} \\
0 & -\frac{11}{5} & \frac{1}{5} & -\frac{3}{5}
\end{bmatrix} \left(R_3 \to R_3 + \frac{11}{5}R_2\right) \longrightarrow \begin{bmatrix}
1 & \frac{3}{5} & \frac{7}{5} & \frac{4}{5} \\
0 & 1 & -\frac{1}{11} & \frac{3}{11} \\
0 & 0 & 0 & 0
\end{bmatrix}
$$

---

## 4. Final Analysis

### Rank Assessment
- **Rank of A** = $\rho(A)$ = 2 (Number of non-zero rows).
- **Rank of Augmented Matrix ($\rho[A|B]$)** = 2.
- **Number of Variables ($n$)** = 3.

### Conclusion
Since $\rho(A) = \rho[A|B] < n$, the system is **Consistent** but has **Infinitely Many Solutions**.

### General Solution
Let $z = k$ (where $k$ is any real number).
1. From $R_2$: $y - \frac{1}{11}k = \frac{3}{11} \implies y = \frac{3+k}{11}$
2. From $R_1$: $x + \frac{3}{5}y + \frac{7}{5}z = \frac{4}{5}$
   $x = \frac{4}{5} - \frac{3}{5}(\frac{3+k}{11}) - \frac{7}{5}k$

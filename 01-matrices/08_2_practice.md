# Engineering Mathematics: Solving Systems of Linear Equations

## Conceptual Overview: Augmented Matrices and Row Echelon Form (REF)

To solve a system of linear equations, we translate the system into a single mathematical object: the **Augmented Matrix**. This allows us to perform operations on the coefficients and constants simultaneously without the distraction of variable names.

### The Logic of Row Operations
We use **Elementary Row Operations (EROs)** to transform the matrix into **Row Echelon Form (REF)**. The goal is to create a "staircase" pattern of zeros in the lower-left corner.
1.  **Swapping:** Interchanging two rows.
2.  **Scaling:** Multiplying a row by a non-zero constant.
3.  **Pivoting:** Adding a multiple of one row to another to create zeros below a "pivot" element.

Once in REF, we use **Back-Substitution** to determine the values of the variables.

---

## Step-by-Step Solution

Given System of Equations:
1. $x + 2y - z = 3$
2. $3x - y + 2z = 1$
3. $2x - 2y + 3z = 2$
4. $x - y + z = -1$

### Step 1: Represent as an Augmented Matrix
We represent the system as $[A|B]$ where $A$ is the coefficient matrix and $B$ is the constant vector.

$$
\begin{bmatrix}
1 & 2 & -1 & 3 \\
3 & -1 & 2 & 1 \\
2 & -2 & 3 & 2 \\
1 & -1 & 1 & -1
\end{bmatrix}
$$

### Step 2: Eliminate $x$ from Rows 2, 3, and 4
We use $R_1$ as the pivot row. The operations are:
- $R_2 \to R_2 - 3R_1$
- $R_3 \to R_3 - 2R_1$
- $R_4 \to R_4 - R_1$

$$
\begin{bmatrix}
1 & 2 & -1 & 3 \\
3 & -1 & 2 & 1 \\
2 & -2 & 3 & 2 \\
1 & -1 & 1 & -1
\end{bmatrix} (R_2-3R_1, R_3-2R_1, R_4-R_1) \longrightarrow \begin{bmatrix}
1 & 2 & -1 & 3 \\
0 & -7 & 5 & -8 \\
0 & -6 & 5 & -4 \\
0 & -3 & 2 & -4
\end{bmatrix}
$$

### Step 3: Simplify Row 4 (Optional but helpful for calculation)
To make calculations easier, we can swap $R_2$ and $R_4$ to use the $-3$ as a more manageable pivot.

$$
\begin{bmatrix}
1 & 2 & -1 & 3 \\
0 & -7 & 5 & -8 \\
0 & -6 & 5 & -4 \\
0 & -3 & 2 & -4
\end{bmatrix} (R_2 \leftrightarrow R_4) \longrightarrow \begin{bmatrix}
1 & 2 & -1 & 3 \\
0 & -3 & 2 & -4 \\
0 & -6 & 5 & -4 \\
0 & -7 & 5 & -8
\end{bmatrix}
$$

### Step 4: Eliminate $y$ from Rows 3 and 4
Using $R_2$ as the new pivot row:
- $R_3 \to R_3 - 2R_2$
- $R_4 \to R_4 - \frac{7}{3}R_2$ (Alternatively, use $3R_4 - 7R_2$ to avoid fractions)

Let's use $3R_4 - 7R_2 \to R_4$:

$$
\begin{bmatrix}
1 & 2 & -1 & 3 \\
0 & -3 & 2 & -4 \\
0 & -6 & 5 & -4 \\
0 & -7 & 5 & -8
\end{bmatrix} (R_3-2R_2, 3R_4-7R_2) \longrightarrow \begin{bmatrix}
1 & 2 & -1 & 3 \\
0 & -3 & 2 & -4 \\
0 & 0 & 1 & 4 \\
0 & 0 & 1 & 4
\end{bmatrix}
$$

### Step 5: Eliminate $z$ from Row 4
- $R_4 \to R_4 - R_3$

$$
\begin{bmatrix}
1 & 2 & -1 & 3 \\
0 & -3 & 2 & -4 \\
0 & 0 & 1 & 4 \\
0 & 0 & 1 & 4
\end{bmatrix} (R_4-R_3) \longrightarrow \begin{bmatrix}
1 & 2 & -1 & 3 \\
0 & -3 & 2 & -4 \\
0 & 0 & 1 & 4 \\
0 & 0 & 0 & 0
\end{bmatrix}
$$

---

## Step 6: Back-Substitution Logic

The matrix is now in **Row Echelon Form**. We translate the rows back into equations:

1.  From $R_3$: $1z = 4 \implies z = 4$
2.  From $R_2$: $-3y + 2z = -4$
    - Substitute $z = 4$:
    - $-3y + 2(4) = -4$
    - $-3y + 8 = -4$
    - $-3y = -12 \implies y = 4$
3.  From $R_1$: $x + 2y - z = 3$
    - Substitute $y = 4$ and $z = 4$:
    - $x + 2(4) - (4) = 3$
    - $x + 8 - 4 = 3$
    - $x + 4 = 3 \implies x = -1$

### Final Result
The system is consistent and has a unique solution:
- $x = -1$
- $y = 4$
- $z = 4$

**Note on Consistency:** Since the last row became all zeros ($0=0$), the fourth equation was redundant. Since the number of non-zero rows ($r=3$) equals the number of variables ($n=3$), the system has a unique solution.

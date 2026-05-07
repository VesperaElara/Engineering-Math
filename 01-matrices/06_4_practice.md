# Rank of a Matrix: Echelon and Normal Forms

## Understanding Rank Through Inspection
Before applying algorithms, it is often useful to look for linear dependencies. If a row is a exact multiple of another, or if two rows are identical, they are linearly dependent and will eventually become a zero row during reduction.

---

## Row Echelon Form for Problem 1
To find the rank, we reduce the matrix to a form where all entries below the leading diagonal (pivots) are zero. The rank is the number of non-zero rows remaining.

### Solving Matrix (i)
$$
A = \begin{bmatrix}
1 & a & b & 0 \\
0 & c & d & 1 \\
1 & a & b & 0 \\
0 & c & d & 1
\end{bmatrix}
$$

**Step 1: Observation**
Notice that $R_1 = R_3$ and $R_2 = R_4$. This immediately tells us that two rows are redundant.

**Step 2: Perform Row Operations**
We subtract $R_1$ from $R_3$ and $R_2$ from $R_4$:

$$
\begin{bmatrix}
1 & a & b & 0 \\
0 & c & d & 1 \\
1 & a & b & 0 \\
0 & c & d & 1
\end{bmatrix} 
(R_3 \to R_3 - R_1 \\: , \\: R_4 \to R_4 - R_2) \longrightarrow
\begin{bmatrix}
1 & a & b & 0 \\
0 & c & d & 1 \\
0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0
\end{bmatrix}
$$

**Result for (i):**
The number of non-zero rows is **2**.
Therefore, **Rank = 2**.

---

## Normal Form for Problem 2
Normal form (also called Canonical form) involves using both **Row Operations** and **Column Operations** to transform a matrix into an identity-like block structure:
```math
\begin{bmatrix}
I_r & 0 \\
0 & 0
\end{bmatrix}
```
Where $I_r$ is an identity matrix of order $r$. The value of $r$ is the Rank.

### Solving Matrix (ii)
$$
A = \begin{bmatrix}
-2 & -1 & -3 & -1 \\
1 & 2 & -3 & -1 \\
1 & 0 & 1 & 1 \\
0 & 1 & 1 & -1
\end{bmatrix}
$$

**Step 1: Get a '1' at the (1,1) position**
Swap $R_1$ and $R_3$ to make calculations easier:

$$
\begin{bmatrix}
-2 & -1 & -3 & -1 \\
1 & 2 & -3 & -1 \\
1 & 0 & 1 & 1 \\
0 & 1 & 1 & -1
\end{bmatrix} (R_1 \leftrightarrow R_3) \longrightarrow \begin{bmatrix}
1 & 0 & 1 & 1 \\
1 & 2 & -3 & -1 \\
-2 & -1 & -3 & -1 \\
0 & 1 & 1 & -1
\end{bmatrix}
$$

**Step 2: Clear the first column and first row**
($R_2 \to R_2-R_1, R_3 \to R_3+2R_1$) and Column operations ($C_3 \to C_3-C_1, C_4 \to C_4-C_1$):

$$
\begin{bmatrix}
1 & 0 & 1 & 1 \\
1 & 2 & -3 & -1 \\
-2 & -1 & -3 & -1 \\
0 & 1 & 1 & -1
\end{bmatrix} (Row \: Ops) \longrightarrow \begin{bmatrix}
1 & 0 & 1 & 1 \\
0 & 2 & -4 & -2 \\
0 & -1 & -1 & 1 \\
0 & 1 & 1 & -1
\end{bmatrix} (Col \: Ops) \longrightarrow \begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 2 & -4 & -2 \\
0 & -1 & -1 & 1 \\
0 & 1 & 1 & -1
\end{bmatrix}
$$

**Step 3: Simplify the remaining block**
Swap $R_2 \leftrightarrow R_4$:

$$
\begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 2 & -4 & -2 \\
0 & -1 & -1 & 1 \\
0 & 1 & 1 & -1
\end{bmatrix} (R_2 \leftrightarrow R_4) \longrightarrow \begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & 1 & -1 \\
0 & -1 & -1 & 1 \\
0 & 2 & -4 & -2
\end{bmatrix}
$$

**Step 4: Clear entries below and beside the second pivot**
Row operations ($R_3 \to R_3+R_2, R_4 \to R_4-2R_2$) and Column operations ($C_3 \to C_3-C_2, C_4 \to C_4+C_2$):

$$
\begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & 1 & -1 \\
0 & -1 & -1 & 1 \\
0 & 2 & -4 & -2
\end{bmatrix} (Row \: Ops) \longrightarrow \begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & 1 & -1 \\
0 & 0 & 0 & 0 \\
0 & 0 & -6 & 0
\end{bmatrix} (Col \: Ops) \longrightarrow \begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & 0 & 0 \\
0 & 0 & -6 & 0
\end{bmatrix}
$$

**Step 5: Final transformation**
Swap $R_3 \leftrightarrow R_4$ and scale $R_3$ by $-1/6$:

$$
\begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & 0 & 0 \\
0 & 0 & -6 & 0
\end{bmatrix} (R_3 \leftrightarrow R_4, R_3 \to -1/6 R_3) \longrightarrow
\begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & 1 & 0 \\
0 & 0 & 0 & 0
\end{bmatrix}
$$

This is the Normal Form $[I_3 : 0]$. Since the identity matrix is of order 3:
**Rank = 3**.

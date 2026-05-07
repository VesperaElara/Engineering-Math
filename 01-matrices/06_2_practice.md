# Finding the Rank of a Matrix: Pivot Method

The **rank** of a matrix, denoted as $\rho(A)$, is the number of linearly independent rows. We find this by converting the matrix into **Row Echelon Form** using a strict step-by-step algorithm.

---

## The Golden Rule of Row Transformations
To avoid logical errors or "moving target" glitches, follow this one rule:
> **Only use a "Pivot Row" to change other rows if that Pivot Row itself is NOT being changed in the same step.**

---

## Step-by-Step Transformation Logic

**Problem:** Find the rank of Matrix $A$:

$$
\begin{bmatrix} 
1 & 4 & 9 & 16 \\
4 & 9 & 16 & 25 \\
9 & 16 & 25 & 36 \\
16 & 25 & 36 & 49
\end{bmatrix}
$$

### Step 1: Use $R_1$ as the Anchor
We use the top-left unity ($1$) to clear the first column. $R_1$ remains frozen.
* $R_2 \to R_2 - 4R_1$
* $R_3 \to R_3 - 9R_1$
* $R_4 \to R_4 - 16R_1$

$$
\begin{bmatrix} 
1 & 4 & 9 & 16 \\
4 & 9 & 16 & 25 \\
9 & 16 & 25 & 36 \\
16 & 25 & 36 & 49
\end{bmatrix} \quad \to \quad
\begin{bmatrix}
1 & 4 & 9 & 16 \\
0 & -7 & -20 & -39 \\
0 & -20 & -56 & -108 \\
0 & -39 & -108 & -207
\end{bmatrix}
$$

### Step 2: Simplify the Rows
To make the numbers easier, we can simplify $R_2, R_3, R_4$ independently. For example, dividing $R_3$ by $4$:
* $R_3 \to R_3 \div 4$

$$
\begin{bmatrix} 
1 & 4 & 9 & 16 \\
0 & -7 & -20 & -39 \\
0 & -20 & -56 & -108 \\
0 & -39 & -108 & -207
\end{bmatrix} \quad \to \quad
\begin{bmatrix} 1 & 4 & 9 & 16 \\
0 & -7 & -20 & -39 \\
0 & -5 & -14 & -27 \\
0 & -39 & -108 & -207 
\end{bmatrix}
$$

### Step 3: Clear the Remaining Columns
By repeating the pivot process (using the new $R_2$ as the anchor to clear the rows below it), we eventually find that $R_4$ becomes a row of zeros because the original numbers followed a quadratic pattern ($n^2$), which always disappears after three layers of consistent subtraction.

---

## Conceptual Breakdown
1. **Pivot Selection:** Always start with the $a_{11}$ element. If it isn't $1$, swap rows to make it $1$.
2. **Elimination:** Use that $1$ to create zeros in every cell below it.
3. **Repeat:** Move to the next diagonal element ($a_{22}$) and repeat the process for the remaining sub-matrix.
4. **Count:** The number of rows that contain at least one non-zero number at the end is your Rank.

## Final Result
* **Rank of Matrix A:** $\rho(A) = 3$
* **Note:** For any $n \times n$ matrix of consecutive squares where $n \geq 4$, the rank will always be $3$.

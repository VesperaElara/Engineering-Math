# Matrix Analysis: Rank and Nullity

This study note breaks down how to find the **Rank** and **Nullity** of a matrix using two standard engineering methods: the **Determinant Method** and the **Transformation Method**.

---

## 1. Conceptual Breakdown
*   **Rank $\rho(A)$:** The number of linearly independent rows. It tells you the "useful" size of the matrix.
*   **Nullity $N(A)$:** The "wasted" dimensions. It represents how many rows became zero during simplification.
*   **The Relation:** $N(A) = \text{Order of Matrix} - \rho(A)$

---

## 2. Method 1: The Determinant Method (Minor Method)
This method involves checking the determinants of the square sub-matrices (minors).

### Step 1: Check the $3 \times 3$ Determinant
```math
\text{|A|} = \begin{vmatrix} 1 & 2 & 3 \\ 1 & 4 & 2 \\ 2 & 6 & 5 \end{vmatrix}
= 1(20 - 12) - 2(5 - 4) + 3(6 - 8)
= 1(8) - 2(1) + 3(-2) = 8 - 2 - 6 = 0
```
$\text{Because |A| = 0, the rank is less than 3.}$


### Step 2: Check a $2 \times 2$ Minor
Pick any $2 \times 2$ sub-matrix, for example, the top left:
```math
\begin{vmatrix} 1 & 2 \\ 1 & 4 \end{vmatrix} = (4 - 2) = 2
```
*Since we found a minor that is **not zero**, the Rank is **2**.*

---

## 3. Method 2: Transformation Method (Row Echelon Form)
We use **Elementary Row Operations** to create a staircase of zeros.

### The Transformation Algorithm

**Step 1: Use $R_1$ to clear the first column.**
We apply $R_2 \to R_2 - R_1$ and $R_3 \to R_3 - 2R_1$ simultaneously:
```math
\begin{bmatrix} 1 & 2 & 3 \\ 1 & 4 & 2 \\ 2 & 6 & 5 \end{bmatrix} \quad \text{R}_2-\text{R}_1 \, , \, \text{R}_3-\text{2R}_1 \to \quad \begin{bmatrix} 1 & 2 & 3 \\ 0 & 2 & -1 \\ 0 & 2 & -1 \end{bmatrix}
```

**Step 2: Use $R_2$ to clear the second column.**
Apply $R_3 \to R_3 - R_2$:
```math
\begin{bmatrix} 1 & 2 & 3 \\ 0 & 2 & -1 \\ 0 & 2 & -1 \end{bmatrix} \quad \text{R}_3-\text{R}_2 \to \quad \begin{bmatrix} 1 & 2 & 3 \\ 0 & 2 & -1 \\ 0 & 0 & 0 \end{bmatrix}
```

---

## 4. Final Calculation
From the final matrix (Echelon Form):
1.  **Count Non-Zero Rows:** There are 2 non-zero rows.
    *   **Rank $\rho(A) = 2$**
2.  **Calculate Nullity:** The matrix order is 3.
    *   **Nullity $N(A) = 3 - 2 = 1$**

> **Quick Summary:** Both methods confirm that one row is a combination of the others, leading to a Rank of 2 and a Nullity of 1.

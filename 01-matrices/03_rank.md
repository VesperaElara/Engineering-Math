# Matrix Theory: Rank of a Matrix

This study note provides a simplified, professional guide to understanding and calculating the **Rank** of a matrix.

---

## 1. What is the Rank?
The **Rank** of a matrix is essentially the number of "useful" or linearly independent rows it contains.

*   **Key Principle:** Elementary transformations (row/column swaps, multiplication by a constant, or adding rows) do **not** change the rank of a matrix.
*   **Equivalent Matrices:** Two matrices are "equivalent" if one can be transformed into the other via these operations. Equivalent matrices always have the same rank.

---

## 2. Methods to Find Rank
There are three primary methods used in Engineering Mathematics:

1.  **Determinant Method** (also known as the Minor Method).
2.  **Echelon Form Method** (using Row Transformations).
3.  **Normal Form Method** (using both Row and Column Transformations).

---

## 3. The Echelon Form
A matrix is considered to be in **Echelon Form** if it follows these three simple rules:

1.  **Zero Rows at the Bottom:** All rows consisting entirely of zeros must be below all non-zero rows.
2.  **The "Staircase" of Zeros:** In each successive row, the number of leading zeros must increase.
3.  **Leading Unity:** The first non-zero element in every row (the pivot) should ideally be **1** (unity).

### Determining Rank from Echelon Form
Once a matrix is in Echelon Form:
> **Rank $\rho(A)$ = The number of non-zero rows.**

---

## 4. Practical Example
Let's analyze the Echelon matrix provided in the lecture notes:

$$
A = \begin{bmatrix} 
1 & 5 & 6 & 7 & 0 & 8 \\ 
0 & 1 & 2 & 5 & -1 & 2 \\ 
0 & 0 & 0 & 1 & 2 & 4 \\ 
0 & 0 & 0 & 0 & 0 & 0 
\end{bmatrix}
$$

### Step-by-Step Logic Breakdown:
1.  **Identify Non-Zero Rows:**
    *   Row 1 is non-zero.
    *   Row 2 is non-zero.
    *   Row 3 is non-zero.
    *   Row 4 is a **zero row** (all elements are $0$).
2.  **Verify Rules:**
    *   The zero row is at the bottom.
    *   The number of zeros before the first non-zero number increases per row ($0 \to 1 \to 3$).
    *   The first non-zero element in every row is $1$.
3.  **Conclusion:**
    *   There are **3** non-zero rows.
    *   **Rank $\rho(A) = 3$**.

---

## 5. Summary Table for GitHub Compatibility


| Method | Best Used For... | Transformation Used |
| :--- | :--- | :--- |
| **Determinant** | Small $2 \times 2$ or $3 \times 3$ matrices | Calculation of Minors |
| **Echelon Form** | Systems of Equations | Row Transformations |
| **Normal Form** | Finding Rank only | Row & Column Transformations |

# Matrix Theory: Normal Form (Canonical Form)

This study note explains the **Normal Form** of a matrix, which is the most simplified state a matrix can reach using both row and column transformations.

---

## 1. What is Normal Form?
If a matrix $A$ has a rank $r$, it can always be reduced to a specific block-style structure containing an Identity (Unit) matrix $I_r$ surrounded by zero matrices. This is known as the **Normal** or **Canonical Form**.

### The Four Possible Structures
Depending on the original dimensions of the matrix, it will take one of these forms:

Unit matrix with zero rows and columns:
```math
\begin{bmatrix} I_r & O \\ O & O \end{bmatrix}
```
Unit matrix with zero rows below:
```math
\begin{bmatrix} I_r \\ O \end{bmatrix}
```
Unit matrix with zero columns to the right:
```math
\begin{bmatrix} I_r & O \end{bmatrix}
```
The entire matrix reduces to a Unit matrix:
```math
\begin{bmatrix} I_r \end{bmatrix}
```

> **Key Rule:** The order of the resulting Identity matrix $I$ is exactly equal to the **Rank** of the original matrix.

---

## 2. Visual Examples (using $I_3$)
As shown in the lecture, if the rank of a matrix is **3**, the Normal Form might look like any of these:

**Type (i):** 
```math
\begin{bmatrix} 1 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 \\ 0 & 0 & 1 & 0 \\ 0 & 0 & 0 & 0 \end{bmatrix} = \begin{bmatrix} I_3 & O \\ O & O \end{bmatrix}
```
**Type (ii):** 
```math
\begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \\ 0 & 0 & 0 \end{bmatrix} = \begin{bmatrix} I_3 \\ O \end{bmatrix}
```
**Type (iii):** 
```math
\begin{bmatrix} 1 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 \\ 0 & 0 & 1 & 0 \end{bmatrix} = \begin{bmatrix} I_3 & O \end{bmatrix}
```
**Type (iv):** 
```math
\begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \end{bmatrix} = \begin{bmatrix} I_3 \end{bmatrix}
```

---

## 3. Step-by-Step Example: Finding Rank via Reduction
To reach Normal Form, we use **Elementary Transformations**. Unlike Echelon form, here we use both Rows ($R$) and Columns ($C$).

### The Problem
Find the rank of matrix $A$:
```math
A = \begin{bmatrix} 1 & 2 & 3 \\ 1 & 4 & 2 \\ 2 & 6 & 5 \end{bmatrix}
```

### The Transformation Algorithm

**Step 1: Eliminate elements in the first column.**
Apply $R_2 \to R_2 - R_1$ and $R_3 \to R_3 - 2R_1$:
```math
\begin{bmatrix} 1 & 2 & 3 \\ 0 & 2 & -1 \\ 0 & 2 & -1 \end{bmatrix}
```

**Step 2: Eliminate elements in the second column (Row Operation).**
Apply $R_3 \to R_3 - R_2$:
```math
\begin{bmatrix} 1 & 2 & 3 \\ 0 & 2 & -1 \\ 0 & 0 & 0 \end{bmatrix}
```
*At this stage, the matrix is in **Triangular (Echelon) Form**.*

**Step 3: Further reduction to reach Normal Form.**
By continuing with column operations (e.g., $C_2 \to C_2 - 2C_1$) and scaling rows, we eventually reach:
```math
\begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 0 \end{bmatrix} = \begin{bmatrix} I_2 & O \\ O & O \end{bmatrix}
```

### Final Result
*   **Normal Form:**
```math
\begin{bmatrix} I_2 & O \\ O & O \end{bmatrix}
```
*   **Rank:** $\rho(A) = 2$ (Since the identity matrix is of order 2).

---

## 4. Summary Table for GitHub


| Form | Purpose | Transformations Used |
| :--- | :--- | :--- |
| **Echelon Form** | Solving $Ax = B$ | Rows Only |
| **Normal Form** | Simplest definition of Rank | Rows & Columns |

# Matrix Theory: The "Legal" Transformation Rules

In Engineering Math, we use **Elementary Row Operations (ERO)** to simplify matrices. These are the only three moves allowed to change a matrix without changing its **Rank**.

---

## 1. The Three Legal Moves
You can perform these operations on any row to reach **Echelon Form** or **Normal Form**.

### I. The Swap (Interchange)
You can swap any two rows. This is usually done to get a "1" or a non-zero number into the top-left corner (the pivot position).
*   **Notation:** $R_i \leftrightarrow R_j$
*   **Example:** Swap Row 1 and Row 2.
```math
\begin{bmatrix} 0 & 5 \\ 1 & 2 \end{bmatrix} 
\quad \text{applying } R_1 \leftrightarrow R_2 \to \quad
\begin{bmatrix} 1 & 2 \\ 0 & 5 \end{bmatrix}
```

### II. The Scale (Multiplication)
You can multiply or divide an entire row by any non-zero constant ($k$). 
*   **Notation:** $R_i \to kR_i$
*   **Example:** Divide Row 1 by 5 to get a leading 1.
$$
\begin{bmatrix} 5 & 10 \\ 0 & 1 \end{bmatrix} \xrightarrow{R_1 \to \frac{1}{5}R_1} \begin{bmatrix} 1 & 2 \\ 0 & 1 \end{bmatrix}
$$

### III. The Combine (Addition/Subtraction)
You can add or subtract a multiple of one row to another row. This is the primary tool for creating **zeros** below your pivots.
*   **Notation:** $R_i \to R_i \pm (k)R_j$
*   **Rule of Thumb:**
    *   If signs are the **same**: Subtract ($R_2 - kR_1$)
    *   If signs are **opposite**: Add ($R_2 + kR_1$)
*   **Example:** Use Row 1 to create a zero in Row 2.
$$
\begin{bmatrix} 1 & 2 \\ 3 & 8 \end{bmatrix} \xrightarrow{R_2 \to R_2 - 3R_1} \begin{bmatrix} 1 & 2 \\ 0 & 2 \end{bmatrix}
$$

---

## 2. Comparison: Determinants vs. Matrices
It is easy to get confused with 12th-grade rules. Here is the "How-To" difference:


| Feature | In Determinants (12th) | In Matrices (Engineering) |
| :--- | :--- | :--- |
| **Scalar $k$** | Taken out of **one** row only. | Multiplies **every** element in the matrix. |
| **Transformations** | Done to find a **value**. | Done to find the **Rank** (Independence). |
| **Goal** | Make it easy to expand. | Create a "staircase" of zeros (Echelon Form). |

---

## 3. The Golden Strategy: "The Pivot"
To avoid making mistakes, always follow this order:
1.  **Get a "1"** in the diagonal position (e.g., $A_{11}$) using **Swap** or **Scale**.
2.  **Kill everything below** that "1" using **Combine** ($R_2 \pm kR_1$, etc.).
3.  **Move to the next diagonal** ($A_{22}$) and repeat.

> **Warning:** Never use a row that you are *currently changing* to change another row in the same step. Stick to using the "Pivot" row to change the others.

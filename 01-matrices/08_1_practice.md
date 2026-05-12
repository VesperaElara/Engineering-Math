# Engineering Mathematics: Consistency of Linear Systems

## 1. Conceptual Framework
To solve a system of linear equations $AX = B$, we use the **Rank Method**. This allows us to determine if a solution exists (consistency) and if that solution is unique or infinite, all before we spend energy on back-substitution.

### Core Variables
* **n**: The number of unknowns (in this case, $x, y, z$, so $n=3$).
* **$\rho(A)$**: The Rank of the coefficient matrix.
* **$\rho(A|B)$**: The Rank of the augmented matrix.

### Logic Gates
1.  **If $\rho(A) \neq \rho(A|B)$**: The system is **Inconsistent** (No Solution).
2.  **If $\rho(A) = \rho(A|B) = n$**: The system is **Consistent** with a **Unique Solution**.
3.  **If $\rho(A) = \rho(A|B) < n$**: The system is **Consistent** with **Infinite Solutions**.

---

## 2. Step-by-Step Transformation (Example)

Question:

$$3x + y + 2z = 11$$

$$2x + 3y + z = 11$$

$$x + 2y + 3z = 14$$

### Step 1: Represent as Augmented Matrix $[A|B]$
We extract the coefficients and the constants into a single matrix. 

$$
\begin{bmatrix}
3 & 1 & 2 & 11 \\
2 & 3 & 1 & 11 \\
1 & 2 & 3 & 14 \\
\end{bmatrix}
$$

### Step 2: Row Swapping for Efficiency
To make calculations easier, we want a '1' in the $R_1C_1$ position. We swap $R_1 \leftrightarrow R_3$.

$$
\begin{bmatrix}
3 & 1 & 2 & 11 \\
2 & 3 & 1 & 11 \\
1 & 2 & 3 & 14 \\
\end{bmatrix} (R_1 \leftrightarrow R_3) \longrightarrow 
\begin{bmatrix}
1 & 2 & 3 & 14 \\
2 & 3 & 1 & 11 \\
3 & 1 & 2 & 11 \\
\end{bmatrix}
$$

### Step 3: Eliminate elements below the pivot
We target the first column using $R_2 \to R_2 - 2R_1$ and $R_3 \to R_3 - 3R_1$.

$$
\begin{bmatrix}
1 & 2 & 3 & 14 \\
2 & 3 & 1 & 11 \\
3 & 1 & 2 & 11 \\
\end{bmatrix} (R_2 - 2R_1, R_3 - 3R_1) \longrightarrow 
\begin{bmatrix}
1 & 2 & 3 & 14 \\
0 & -1 & -5 & -17 \\
0 & -5 & -7 & -31 \\
\end{bmatrix}
$$

### Step 4: Final Echelon Transformation
We target the second column to reach Row Echelon Form using $R_3 \to R_3 - 5R_2$.

$$
\begin{bmatrix}
1 & 2 & 3 & 14 \\
0 & -1 & -5 & -17 \\
0 & -5 & -7 & -31 \\
\end{bmatrix} (R_3 - 5R_2) \longrightarrow 
\begin{bmatrix}
1 & 2 & 3 & 14 \\
0 & -1 & -5 & -17 \\
0 & 0 & 18 & 54 \\
\end{bmatrix}
$$

---

## 3. Analysis & Verification

### Observe the Rank
* The number of non-zero rows in the whole matrix is **3**, so $\rho(A|B) = 3$.
* Ignoring the last column, the number of non-zero rows in matrix $A$ is **3**, so $\rho(A) = 3$.
* The number of unknowns ($x, y, z$) is $n = 3$.

**Conclusion:** Since $\rho(A) = \rho(A|B) = n = 3$, the system is **Consistent** and has a **Unique Solution**.

### Solving for Variables (Back-Substitution)
From $R_3$: 
$$18z = 54 \implies z = 3$$

From $R_2$: 
$$-y - 5(3) = -17 \implies -y - 15 = -17 \implies y = 2$$

From $R_1$: 
$$x + 2(2) + 3(3) = 14 \implies x + 4 + 9 = 14 \implies x = 1$$

**Final Result Set:** $(x, y, z) = (1, 2, 3)$.

### Post-Transformation Insights
* **The "End State" Logic:** A matrix has reached its final Row Echelon Form when each leading entry (pivot) is to the right of the pivot in the row above it, and all entries below these pivots are zero. Once this "staircase" is established and no more non-zero entries exist below the pivots to eliminate, the transformation is complete.
*  **The Role of Back-Substitution:** The transformed matrix represents a simplified system of equations where the final row typically contains only one variable. By solving this last variable first and "plugging" it back into the preceding equations, we systematically unlock the values of the remaining unknowns.

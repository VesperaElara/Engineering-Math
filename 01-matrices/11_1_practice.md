# Engineering Mathematics: Cayley-Hamilton Theorem

This note focuses on the verification of the Cayley-Hamilton Theorem and the subsequent calculation of a matrix inverse.

---

## 1. Theoretical Foundation

### The Cayley-Hamilton Theorem
The Cayley-Hamilton Theorem states that every square matrix satisfies its own **characteristic equation**. If the characteristic polynomial of an $n \times n$ matrix $A$ is given by $P(\lambda) = \det(A - \lambda I)$, then:
$$P(A) = 0$$
where $0$ is the null matrix of order $n$.

### Conceptual Logic
1.  **Characteristic Equation**: Find the eigenvalues by solving $\det(A - \lambda I) = 0$.
2.  **Substitution**: Replace the scalar variable $\lambda$ with the matrix $A$, and replace the constant term $c$ with $cI$ (where $I$ is the Identity matrix).
3.  **Verification**: Perform matrix arithmetic to prove the resulting expression equals the zero matrix.
4.  **Inverse Calculation**: Multiply the characteristic equation by $A^{-1}$ to isolate and solve for the inverse matrix.

---

## 2. Step-by-Step Verification & Application

Matrix given:
```math
A = \begin{bmatrix}
1 & 2\\
-1 & 3
\end{bmatrix}
```

### Step 1: Find the Characteristic Equation
We solve $\det(A - \lambda I) = 0$:
```math
\det\left(\begin{bmatrix}
1 & 2\\
-1 & 3
\end{bmatrix} - \lambda \begin{bmatrix}
1 & 0\\
0 & 1
\end{bmatrix}\right) = 0
```
```math
\begin{vmatrix}
1 - \lambda & 2\\
-1 & 3 - \lambda
\end{vmatrix} = 0
```

Expanding the determinant:

$$(1 - \lambda)(3 - \lambda) - (2)(-1) = 0$$

$$3 - \lambda - 3\lambda + \lambda^2 + 2 = 0$$

$$\lambda^2 - 4\lambda + 5 = 0$$

### Step 2: Verify Cayley-Hamilton Theorem
According to the theorem, $A^2 - 4A + 5I = 0$.

**Calculate $A^2$**:
```math
A^2 = \begin{bmatrix}
1 & 2\\
-1 & 3
\end{bmatrix} \begin{bmatrix}
1 & 2\\
-1 & 3
\end{bmatrix}
```

```math
A^2 = \begin{bmatrix}
(1)(1) + (2)(-1) & (1)(2) + (2)(3)\\
(-1)(1) + (3)(-1) & (-1)(2) + (3)(3)
\end{bmatrix} = \begin{bmatrix}
-1 & 8\\
-4 & 7
\end{bmatrix}
```

**Substitute into the equation**:
```math
\begin{bmatrix}
-1 & 8\\
-4 & 7
\end{bmatrix} - 4\begin{bmatrix}
1 & 2\\
-1 & 3
\end{bmatrix} + 5\begin{bmatrix}
1 & 0\\
0 & 1
\end{bmatrix}
```

```math
\begin{bmatrix}
-1 & 8\\
-4 & 7
\end{bmatrix} - \begin{bmatrix}
4 & 8\\
-4 & 12
\end{bmatrix} + \begin{bmatrix}
5 & 0\\
0 & 5
\end{bmatrix}
```

```math
\begin{bmatrix}
-1 - 4 + 5 & 8 - 8 + 0\\
-4 - (-4) + 0 & 7 - 12 + 5
\end{bmatrix} = \begin{bmatrix}
0 & 0\\
0 & 0
\end{bmatrix}
```
The theorem is verified.

### Step 3: Find the Inverse Matrix ($A^{-1}$)
Starting from the verified equation:

$$A^2 - 4A + 5I = 0$$

Multiply the entire equation by $A^{-1}$:

$$A^{-1}(A^2) - 4A^{-1}(A) + 5A^{-1}(I) = 0$$

$$A - 4I + 5A^{-1} = 0$$

Isolate $5A^{-1}$:
```math
5A^{-1} = 4I - A
```

```math
5A^{-1} = 4\begin{bmatrix}
1 & 0\\
0 & 1
\end{bmatrix} - \begin{bmatrix}
1 & 2\\
-1 & 3
\end{bmatrix}
```

```math
5A^{-1} = \begin{bmatrix}
4 & 0\\
0 & 4
\end{bmatrix} - \begin{bmatrix}
1 & 2\\
-1 & 3
\end{bmatrix} \longrightarrow 5A^{-1} = \begin{bmatrix}
3 & -2\\
1 & 1
\end{bmatrix}
```

Final result for $A^{-1}$:
```math
A^{-1} = \frac{1}{5} \begin{bmatrix}
3 & -2\\
1 & 1
\end{bmatrix}
```

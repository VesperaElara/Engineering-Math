# Engineering Mathematics: Eigenvalues and Eigenvectors

## 1. Fundamental Definitions
To analyze the transformation characteristics of a square matrix, we use the concepts of characteristic matrices and equations.

*   **Characteristic Matrix**: For a square matrix $A$ of order $n$, the matrix $(A - \lambda I)$ is known as the characteristic matrix, where $\lambda$ is a scalar variable and $I$ is the identity matrix.
*   **Characteristic Equation**: The equation obtained by setting the determinant of the characteristic matrix to zero, $|A - \lambda I| = 0$, is the characteristic equation.
*   **Eigenvalues**: The roots of the characteristic equation are called Eigenvalues (or Latent/Characteristic roots).
*   **Eigenvectors**: A non-zero vector $X$ that satisfies the homogeneous linear system $(A - \lambda I)X = 0$ is the Eigenvector corresponding to the eigenvalue $\lambda$.

---

## 2. The Working Algorithm
The logical flow for solving these problems consists of three primary stages:

1.  **Formulate the Characteristic Equation**: Construct the determinant $|A - \lambda I|$ and set it to zero.
2.  **Determine Eigenvalues**: Solve the resulting polynomial for $\lambda$.
3.  **Solve for Eigenvectors**: For every individual $\lambda$ value, solve the system $(A - \lambda I)X = 0$ using Gaussian elimination or row transformations.

---

## 3. Step-by-Step Transformation Example
We will find the eigenvalues and eigenvectors for matrix $A$:
```math
A = \begin{bmatrix}
5 & 4 \\
1 & 2
\end{bmatrix}
```


### Step 1: Solve the Characteristic Equation
Set $|A - \lambda I| = 0$:
```math
\begin{vmatrix}
5 - \lambda & 4 \\
1 & 2 - \lambda
\end{vmatrix} = 0
```
Expanding the determinant:

$$(5 - \lambda)(2 - \lambda) - (4 \times 1) = 0$$

$$10 - 7\lambda + \lambda^{2} - 4 = 0$$

$$\lambda^{2} - 7\lambda + 6 = 0$$

Factoring the quadratic:

$$(\lambda - 1)(\lambda - 6) = 0$$

The **Eigenvalues** are $\lambda_{1} = 1$ and $\lambda_{2} = 6$.

### Step 2: Find Eigenvector for $\lambda = 1$
Substitute $\lambda = 1$ into $(A - \lambda I)X = 0$:
```math
\begin{bmatrix}
5 - 1 & 4 \\
1 & 2 - 1
\end{bmatrix}
\begin{bmatrix}
x_{1} \\
x_{2}
\end{bmatrix} = \begin{bmatrix}
0 \\
0
\end{bmatrix}
```
```math
\begin{bmatrix}
4 & 4 \\
1 & 1
\end{bmatrix} \begin{bmatrix}
x_{1} \\
x_{2}
\end{bmatrix} = \begin{bmatrix}
0 \\
0
\end{bmatrix}
```
Applying row transformation $R_{1} \longrightarrow R_{1} \times (\frac{1}{4})$:
```math
\begin{bmatrix}
4 & 4 \\
1 & 1
\end{bmatrix} (R_{1} \to \frac{1}{4}R_{1}) \longrightarrow \begin{bmatrix}
1 & 1 \\
1 & 1
\end{bmatrix}
```
Applying $R_{2} \longrightarrow R_{2} - R_{1}$:
```math
\begin{bmatrix}
1 & 1 \\
1 & 1
\end{bmatrix} (R_{2} \to R_{2} - R_{1}) \longrightarrow \begin{bmatrix}
1 & 1 \\
0 & 0
\end{bmatrix}
```
This gives the equation $x_{1} + x_{2} = 0$, or $x_{1} = -x_{2}$.
Let $x_{2} = -k$, then $x_{1} = k$. For $k=1$:
```math
X_{1} = \begin{bmatrix}
1 \\
-1
\end{bmatrix}
```


### Step 3: Find Eigenvector for $\lambda = 6$
Substitute $\lambda = 6$ into $(A - \lambda I)X = 0$:
```math
\begin{bmatrix}
5 - 6 & 4 \\
1 & 2 - 6
\end{bmatrix} \begin{bmatrix}
x_{1} \\
x_{2}
\end{bmatrix} = \begin{bmatrix}
0 \\
0
\end{bmatrix}
```
```math
\begin{bmatrix}
-1 & 4 \\
1 & -4
\end{bmatrix} \begin{bmatrix}
x_{1} \\
x_{2}
\end{bmatrix} = \begin{bmatrix}
0 \\
0
\end{bmatrix}
```
Applying $R_{2} \longrightarrow R_{2} + R_{1}$:
```math
\begin{bmatrix}
-1 & 4 \\
1 & -4
\end{bmatrix} (R_{2} \to R_{2} + R_{1}) \longrightarrow \begin{bmatrix}
-1 & 4 \\
0 & 0
\end{bmatrix}
```
This gives the equation $-x_{1} + 4x_{2} = 0$, or $x_{1} = 4x_{2}$.
Let $x_{2} = 1$, then $x_{1} = 4$:
```math
X_{2} = \begin{bmatrix}
4 \\
1
\end{bmatrix}
```

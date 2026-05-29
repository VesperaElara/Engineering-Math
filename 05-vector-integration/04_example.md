# Vector Integration: Path Independence and Scalar Potential

## 1. Path Independence of Line Integrals

### Name of Concept
Path-Independent Line Integrals and Evaluation via Scalar Potential ($\phi$).

### Core Mathematical Formulas

If a vector field $\bar{F}$ is irrotational ($\nabla \times \bar{F} = \bar{0}$), the line integral along any curve $C$ connecting point $A$ to point $B$ is entirely **path-independent**:

$$\int_C \bar{F} \cdot d\bar{r} = \int_A^B \bar{F} \cdot d\bar{r} = \phi(B) - \phi(A)$$

The components of the vector field are related to the scalar potential by:

$$\frac{\partial \phi}{\partial x} = f_1, \quad \frac{\partial \phi}{\partial y} = f_2$$

### Beginner-Friendly Explanation of Operations



1. **The Trapped Curve Trap:** When a problem asks you to evaluate a complex line integral along a complicated curved arc (like $2x = \pi y^2$), substituting the path equation directly can lead to highly difficult integration steps. 
2. **Checking for Path Independence:** First, check if the vector field is irrotational by taking its curl ($\nabla \times \bar{F}$). If the curl is zero, it means the field is *conservative*. 
3. **The Shortcut:** For a conservative field, the path you take between point $A$ and point $B$ does not matter. The answer will be identical whether you travel along a straight line, a parabola, or a random loop. 
4. **Using the Potential Function ($\phi$):** Instead of integrating along the path, find the underlying scalar potential function $\phi(x, y)$. Once found, calculate the final answer by subtracting the value of the function at the starting point from its value at the ending point: $\phi(\text{End}) - \phi(\text{Start})$. This matches the Fundamental Theorem of Calculus.

---

## 2. Step-by-Step Problem Solution

### Question
Prove that:

$$\int_A^B (2xy^3 - y^2\cos x)dx + (1 - 2y\sin x + 3x^2y^2)dy = \frac{\pi^2}{4}$$

along the arc $2x = \pi y^2$ from $A(0, 0)$ to $B\left(\frac{\pi}{2}, 1\right)$.

### Step 1: Identify the field components
From the given differential form, extract the vector field components $f_1$ and $f_2$ (treating it as a 2D field where $f_3 = 0$):

$$f_1 = 2xy^3 - y^2\cos x$$

$$f_2 = 1 - 2y\sin x + 3x^2y^2$$

### Step 2: Test if the field is irrotational using Curl
Set up the $3 \times 3$ matrix determinant:

$$\nabla \times \bar{F} = \begin{vmatrix} \bar{i} & \bar{j} & \bar{k} \\ \frac{\partial}{\partial x} & \frac{\partial}{\partial y} & \frac{\partial}{\partial z} \\ (2xy^3 - y^2\cos x) & (1 - 2y\sin x + 3x^2y^2) & 0 \end{vmatrix}$$

The $\bar{i}$ and $\bar{j}$ components evaluate to $0$ because there is no $z$ variable in the equations. Evaluate the $\bar{k}$ component:

$$\text{Component } \bar{k} = \bar{k} \left[ \frac{\partial}{\partial x}(1 - 2y\sin x + 3x^2y^2) - \frac{\partial}{\partial y}(2xy^3 - y^2\cos x) \right]$$

Compute the partial derivatives:

$$\frac{\partial f_2}{\partial x} = -2y\cos x + 6xy^2$$

$$\frac{\partial f_1}{\partial y} = 6xy^2 - 2y\cos x$$

Substitute these back into the component brackets:

$$\text{Component } \bar{k} = \bar{k} \left[ (-2y\cos x + 6xy^2) - (6xy^2 - 2y\cos x) \right] = \bar{k}(0)$$

$$\nabla \times \bar{F} = \bar{0}$$

Because the curl is zero, the line integral is **path-independent**. We can bypass the arc constraint equation entirely.

### Step 3: Set up the partial integration equations for $\phi$

$$\frac{\partial \phi}{\partial x} = 2xy^3 - y^2\cos x \quad \text{--- (Equation 1)}$$

$$\frac{\partial \phi}{\partial y} = 1 - 2y\sin x + 3x^2y^2 \quad \text{--- (Equation 2)}$$

### Step 4: Integrate Equation 1 with respect to $x$
Integrate with respect to $x$, treating $y$ as a constant factor. Add a placeholder function of $y$, labeled $f(y)$:

$$\phi = \int (2xy^3 - y^2\cos x) \, dx$$

$$\phi = 2\left(\frac{x^2}{2}\right)y^3 - y^2(\sin x) + f(y)$$

$$\phi = x^2y^3 - y^2\sin x + f(y) \quad \text{--- (Expression A)}$$

### Step 5: Integrate Equation 2 with respect to $y$
Integrate with respect to $y$, treating $x$ as a constant factor. Add a placeholder function of $x$, labeled $g(x)$:

$$\phi = \int (1 - 2y\sin x + 3x^2y^2) \, dy$$

$$\phi = y - 2\left(\frac{y^2}{2}\right)\sin x + 3x^2\left(\frac{y^3}{3}\right) + g(x)$$

$$\phi = y - y^2\sin x + x^2y^3 + g(x) \quad \text{--- (Expression B)}$$

### Step 6: Merge the terms to determine the final scalar potential
Compare **Expression A** and **Expression B**:
* The terms $x^2y^3$ and $-y^2\sin x$ are shared by both expressions.
* The standalone $y$ term in Expression B corresponds to the missing function $f(y)$ from Expression A.

Combine all unique terms (omitting the arbitrary constant $C$ as it cancels during definite evaluation):

$$\phi(x, y) = x^2y^3 - y^2\sin x + y$$

### Step 7: Evaluate the potential at the boundary points
Evaluate $\phi$ at the terminal point $B\left(\frac{\pi}{2}, 1\right)$:

$$\phi(B) = \left(\frac{\pi}{2}\right)^2(1)^3 - (1)^2\sin\left(\frac{\pi}{2}\right) + 1$$

Since $\sin\left(\frac{\pi}{2}\right) = 1$:

$$\phi(B) = \frac{\pi^2}{4} - 1 + 1 = \frac{\pi^2}{4}$$

Evaluate $\phi$ at the starting point $A(0, 0)$:

$$\phi(A) = (0)^2(0)^3 - (0)^2\sin(0) + 0 = 0$$

### Step 8: Subtract to calculate the final line integral value

$$\int_A^B \bar{F} \cdot d\bar{r} = \phi(B) - \phi(A)$$

$$\int_A^B \bar{F} \cdot d\bar{r} = \frac{\pi^2}{4} - 0 = \frac{\pi^2}{4}$$

This matches the target value, completing the proof.
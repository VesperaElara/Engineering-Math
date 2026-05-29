# Vector Differentiation: Scalar Potential of an Irrotational Field

## 1. Scalar Potential of a Conservative Field

### Name of Concept
Conservative Vector Fields and Finding the Scalar Potential ($\phi$).

### Core Mathematical Formula

If a vector field $\bar{F}$ is irrotational ($\nabla \times \bar{F} = \bar{0}$), it can be expressed as the gradient of a scalar function $\phi$. This scalar function $\phi$ is called the **scalar potential**:

$$\bar{F} = \nabla \phi$$

This vector equation expands into three independent scalar differential equations:

$$\frac{\partial \phi}{\partial x} = f_1, \quad \frac{\partial \phi}{\partial y} = f_2, \quad \frac{\partial \phi}{\partial z} = f_3$$

### Beginner-Friendly Explanation of Operations

1. **What is a Scalar Potential?** Think of a vector field $\bar{F}$ as a force field (like gravity or an electric field). If the field is irrotational, it means moving an object along a closed loop costs zero net energy. Because energy is conserved, we can describe the field using a single underlying "hill" or "altitude map" called the scalar potential $\phi$ (similar to potential energy).
2. **Reversing the Derivative (Integration):** The field components $f_1$, $f_2$, and $f_3$ are the partial derivatives of our mystery function $\phi$. To recover $\phi$, we must perform partial integration:
   * Integrate $f_1$ with respect to $x$. When doing this, any term containing *only* $y$ or $z$ acts like a constant and disappears. So, instead of a standard constant $+ C$, we add an unknown function $+ f(y, z)$.
   * Integrate $f_2$ with respect to $y$, adding an unknown function $+ g(x, z)$.
   * Integrate $f_3$ with respect to $z$, adding an unknown function $+ h(x, y)$.
3. **Merging the Results:** Finally, we look at all three integration results and combine them logically. We include every unique term exactly once, along with a final constant number $+ C$.

---

## 2. Step-by-Step Problem Solution

### Question
A vector field is given by $\bar{F} = (x^2 + xy^2)\bar{i} + (y^2 + x^2y)\bar{j}$. Show that $\bar{F}$ is irrotational and find its scalar potential.

### Step 1: Extract the vector components
Identify the scalar function components $f_1$, $f_2$, and $f_3$:

$$f_1 = x^2 + xy^2$$

$$f_2 = y^2 + x^2y$$

$$f_3 = 0$$

### Step 2: Set up and evaluate the curl determinant

$$\nabla \times \bar{F} = \begin{vmatrix} \bar{i} & \bar{j} & \bar{k} \\ \frac{\partial}{\partial x} & \frac{\partial}{\partial y} & \frac{\partial}{\partial z} \\ (x^2 + xy^2) & (y^2 + x^2y) & 0 \end{vmatrix}$$

Expand the determinant component by component:

$$\text{Component } \bar{i} = \bar{i} \left[ \frac{\partial}{\partial y}(0) - \frac{\partial}{\partial z}(y^2 + x^2y) \right] = \bar{i}[0 - 0] = \bar{0}$$

$$\text{Component } \bar{j} = -\bar{j} \left[ \frac{\partial}{\partial x}(0) - \frac{\partial}{\partial z}(x^2 + xy^2) \right] = -\bar{j}[0 - 0] = \bar{0}$$

$$\text{Component } \bar{k} = \bar{k} \left[ \frac{\partial}{\partial x}(y^2 + x^2y) - \frac{\partial}{\partial y}(x^2 + xy^2) \right] = \bar{k}[2xy - 2xy] = \bar{0}$$

Combine the components:

$$\nabla \times \bar{F} = 0\bar{i} - 0\bar{j} + 0\bar{k} = \bar{0}$$

Since $\nabla \times \bar{F} = \bar{0}$, the vector field $\bar{F}$ is proven to be **irrotational**.

### Step 3: Set up the partial differential equations for $\phi$
Since the field is irrotational, set $\bar{F} = \nabla \phi$:

$$\frac{\partial \phi}{\partial x} = x^2 + xy^2 \quad \text{--- (Equation 1)}$$

$$\frac{\partial \phi}{\partial y} = y^2 + x^2y \quad \text{--- (Equation 2)}$$

### Step 4: Integrate Equation 1 with respect to $x$
Integrate both terms with respect to $x$, treating $y$ as a constant factor. Add a placeholder function of $y$, labeled $f(y)$, as the constant of integration:

$$\phi = \int (x^2 + xy^2) \, dx$$

$$\phi = \frac{x^3}{3} + \frac{x^2y^2}{2} + f(y) \quad \text{--- (Expression A)}$$

### Step 5: Integrate Equation 2 with respect to $y$
Integrate both terms with respect to $y$, treating $x$ as a constant factor. Add a placeholder function of $x$, labeled $g(x)$, as the constant of integration:

$$\phi = \int (y^2 + x^2y) \, dy$$

$$\phi = \frac{y^3}{3} + \frac{x^2y^2}{2} + g(x) \quad \text{--- (Expression B)}$$

### Step 6: Compare and merge expressions to find the final scalar potential
Compare **Expression A** and **Expression B** to reconstruct the complete function $\phi$:
* The shared term $\frac{x^2y^2}{2}$ appears in both calculations. We write it down once.
* The term $\frac{x^3}{3}$ from Expression A matches the missing function $g(x)$ in Expression B.
* The term $\frac{y^3}{3}$ from Expression B matches the missing function $f(y)$ in Expression A.

Combine all unique terms and add a final absolute integration constant $C$:

$$\phi = \frac{x^3}{3} + \frac{x^2y^2}{2} + \frac{y^3}{3} + C$$
# Engineering Mathematics Study Note: Unit Normal Vector and Directional Derivative

## 1. IDENTIFY
The concepts presented on this board are:
1. **Unit Vector Normal to a Surface**: Finding a unit vector that is perpendicular (orthogonal) to a given level surface $\phi(x,y,z) = c$ at a specific point.
2. **Directional Derivative along a Given Vector**: Calculating the rate of change of a scalar function along an explicitly provided vector direction (rather than between two points).

---

## 2. THE FORMULA

The Normal Vector ($\mathbf{N}$) to a surface $\phi(x,y,z) = 0$ at any point is given by the Gradient:
$$\mathbf{N} = \nabla\phi$$

The Unit Normal Vector ($\hat{\mathbf{n}}$) is the normal vector divided by its length (magnitude):
$$\hat{\mathbf{n}} = \frac{\nabla\phi}{|\nabla\phi|}$$

The Directional Derivative (D.D) along an explicit vector direction $\mathbf{a}$:
$$\text{D.D} = \frac{\nabla\phi \cdot \mathbf{a}}{|\mathbf{a}|}$$

---

## 3. THE ALGORITHM

### Blueprint A: Finding the Unit Normal Vector to a Surface
### Step 1: Rewrite the equation into standard form
Move all constants to one side so the equation looks like $\phi(x,y,z) - c = 0$. Define this entire expression as your scalar function $\phi$.

### Step 2: Compute the Gradient vector
Calculate the three partial derivatives and assemble them with their respective directional components.
$$\nabla\phi = \mathbf{i}\frac{\partial\phi}{\partial x} + \mathbf{j}\frac{\partial\phi}{\partial y} + \mathbf{k}\frac{\partial\phi}{\partial z}$$

### Step 3: Evaluate the Gradient at the given point
Substitute the numerical coordinates of the specified point into your $\nabla\phi$ expression to obtain the actual normal vector components.

### Step 4: Calculate the magnitude of the Gradient vector
Find the absolute length of this specific normal vector.
$$|\nabla\phi| = \sqrt{(\text{component}_x)^2 + (\text{component}_y)^2 + (\text{component}_z)^2}$$

### Step 5: Normalize the vector
Divide each component of the evaluated gradient vector by its total magnitude to get the final unit normal vector.
$$\hat{\mathbf{n}} = \frac{\nabla\phi}{|\nabla\phi|}$$

---

### Blueprint B: Finding Directional Derivative along a Given Vector
### Step 1: Compute and evaluate the Gradient vector
Find $\nabla\phi$ and immediately substitute the given point coordinates into it.

### Step 2: Use the provided vector directly
Identify the given directional vector $\mathbf{a}$ directly from the problem statement (no subtraction of coordinates needed here, as the vector is explicitly given).

### Step 3: Calculate the magnitude of the given vector
Compute the length of the directional vector.
$$|\mathbf{a}| = \sqrt{(a_x)^2 + (a_y)^2 + (a_z)^2}$$

### Step 4: Compute the final Dot Product ratio
Compute the dot product of the evaluated gradient and the vector $\mathbf{a}$, then divide by the vector's magnitude.
$$\text{D.D} = \frac{\nabla\phi \cdot \mathbf{a}}{|\mathbf{a}|}$$

---

## 4. THE MECHANICS

### The Geometrical Meaning of the Gradient ($\nabla\phi$)
The gradient vector $\nabla\phi$ always points in the direction of the steepest ascent on a surface. Geometrically, it stands completely straight up (at an angle of 90 degrees) relative to the surface plane at that exact point. Because it is perpendicular, it is called the **Normal Vector**.

### Normalizing a Vector
"Normalizing" means changing a vector's total length to exactly $1$ while keeping its pointing direction completely identical. You achieve this by scaling every single item inside the vector down by its total geometric length.
* **Example:** If a vector is $\mathbf{v} = 3\mathbf{i} + 4\mathbf{j}$, its length is $\sqrt{3^2 + 4^2} = \sqrt{25} = 5$. The normalized unit vector is:
$$\hat{\mathbf{v}} = \frac{3}{5}\mathbf{i} + \frac{4}{5}\mathbf{j}$$

### Handling Algebraic Powers during Partial Differentiation
When executing the Power Rule $\frac{d}{dx}(x^n) = n x^{n-1}$ inside a multi-variable term, leave the other variables untouched as multipliers.
* **Example 1:** Differentiating $xy^3z^2$ with respect to $y$:
Treat $x$ and $z^2$ as constant coefficients. Bring the power $3$ down in front of $y$, and decrease its power by 1.
$$\frac{\partial}{\partial y}(xy^3z^2) = x \cdot (3y^2) \cdot z^2 = 3x y^2 z^2$$
* **Example 2:** Differentiating $4xz^3$ with respect to $x$:
The derivative of $x$ is $1$, and $4z^3$ acts as a constant multiplier.
$$\frac{\partial}{\partial x}(4xz^3) = 4(1)z^3 = 4z^3$$

---

## 5. STEP-BY-STEP WORKED EXAMPLE

Based on Problem 1: Find the unit normal vector to $xy^3z^2 = 4$ at $(-1, -1, 2)$.

### Execution of Step 1: Convert to Standard Form
$$\phi = xy^3z^2 - 4$$

### Execution of Step 2: Compute Partial Derivatives
$$\frac{\partial\phi}{\partial x} = (1)y^3z^2 - 0 = y^3z^2$$
$$\frac{\partial\phi}{\partial y} = x(3y^2)z^2 - 0 = 3xy^2z^2$$
$$\frac{\partial\phi}{\partial z} = xy^3(2z) - 0 = 2xy^3z$$

Assemble $\nabla\phi$:
$$\nabla\phi = \mathbf{i}(y^3z^2) + \mathbf{j}(3xy^2z^2) + \mathbf{k}(2xy^3z)$$

### Execution of Step 3: Substitute Point $(-1, -1, 2)$
$$\nabla\phi_{(-1,-1,2)} = \mathbf{i}((-1)^3(2)^2) + \mathbf{j}(3(-1)(-1)^2(2)^2) + \mathbf{k}(2(-1)(-1)^3(2))$$
$$\nabla\phi_{(-1,-1,2)} = \mathbf{i}(-1 \cdot 4) + \mathbf{j}(3 \cdot -1 \cdot 1 \cdot 4) + \mathbf{k}(2 \cdot -1 \cdot -1 \cdot 2)$$
$$\nabla\phi_{(-1,-1,2)} = -4\mathbf{i} - 12\mathbf{j} + 4\mathbf{k}$$

### Execution of Step 4: Calculate Magnitude
$$|\nabla\phi| = \sqrt{(-4)^2 + (-12)^2 + (4)^2}$$
$$|\nabla\phi| = \sqrt{16 + 144 + 16} = \sqrt{176}$$
$$|\nabla\phi| = \sqrt{16 \times 11} = 4\sqrt{11}$$

### Execution of Step 5: Normalize to Find Unit Vector
$$\hat{\mathbf{n}} = \frac{-4\mathbf{i} - 12\mathbf{j} + 4\mathbf{k}}{4\sqrt{11}}$$
$$\hat{\mathbf{n}} = -\frac{1}{\sqrt{11}}\mathbf{i} - \frac{3}{\sqrt{11}}\mathbf{j} + \frac{1}{\sqrt{11}}\mathbf{k}$$
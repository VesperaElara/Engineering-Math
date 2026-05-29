# Engineering Mathematics Study Note: Directional Derivative Calculation

## 1. IDENTIFY
The concept being executed is the calculation of the **Directional Derivative** of a scalar field $\phi$ along an explicitly given vector direction $\mathbf{a} = 2\mathbf{i} + 3\mathbf{j} + 6\mathbf{k}$ at a specific point in 3D space.

---

## 2. THE FORMULA

The Directional Derivative (D.D) of a scalar function $\phi$ along a vector direction $\mathbf{a}$ is given by:
$$\text{D.D} = \nabla\phi \cdot \hat{\mathbf{a}} = \frac{\nabla\phi \cdot \mathbf{a}}{|\mathbf{a}|}$$

Where the Gradient vector $\nabla\phi$ is:
$$\nabla\phi = \mathbf{i}\frac{\partial\phi}{\partial x} + \mathbf{j}\frac{\partial\phi}{\partial y} + \mathbf{k}\frac{\partial\phi}{\partial z}$$

And the unit direction vector $\hat{\mathbf{a}}$ is:
$$\hat{\mathbf{a}} = \frac{\mathbf{a}}{|\mathbf{a}|}$$

---

## 3. THE ALGORITHM

### Step 1: Compute the partial derivatives
Find the derivative of $\phi$ with respect to each variable ($x$, $y$, and $z$) one at a time while holding the remaining two variables constant.
$$\frac{\partial\phi}{\partial x}, \quad \frac{\partial\phi}{\partial y}, \quad \frac{\partial\phi}{\partial z}$$

### Step 2: Construct the Gradient expression
Assemble the partial derivatives into a single three-dimensional vector using the directional unit vectors.
$$\nabla\phi = \mathbf{i}\frac{\partial\phi}{\partial x} + \mathbf{j}\frac{\partial\phi}{\partial y} + \mathbf{k}\frac{\partial\phi}{\partial z}$$

### Step 3: Evaluate the Gradient at the given point
Substitute the numerical values of the coordinates $(x, y, z) = (2, -1, 2)$ into the variables of the gradient vector to get a fixed numerical vector.

### Step 4: Calculate the magnitude of the direction vector
Find the total length of the provided directional vector $\mathbf{a}$ using the 3D Pythagorean distance formula.
$$|\mathbf{a}| = \sqrt{(a_x)^2 + (a_y)^2 + (a_z)^2}$$

### Step 5: Perform the Dot Product and scale
Compute the dot product between the numerical gradient vector (from Step 3) and the directional vector $\mathbf{a}$. Divide that scalar result by the vector's magnitude (from Step 4).

---

## 4. THE MECHANICS

### Resolving Algebraic Multipliers during Partial Differentiation
When a term contains multiple variables multiplied together, isolate the active variable and treat everything else as a single cohesive constant multiplier.
* **Example:** Differentiating $-3x^2y^2z$ with respect to $x$:
Treat the block $(-3y^2z)$ as a single constant number. Apply the power rule only to $x^2$, which becomes $2x$. Then multiply them together:
$$\frac{\partial}{\partial x}(-3x^2y^2z) = (-3y^2z) \cdot (2x) = -6xy^2z$$

### Evaluating Arithmetic with Negative Numbers
When substituting negative coordinate numbers like $y = -1$, keep them strictly enclosed in brackets to avoid sign placement errors, especially when dealing with powers.
* $(-1)^2 = 1$ (A negative number raised to an even power becomes positive)
* $-3(2)^2(2) \cdot 2(-1) = -3(4)(2) \cdot (-2) = -24 \cdot (-2) = +48$

---

## 5. STEP-BY-STEP WORKED SOLUTIONS

### Execution of Step 1 & 2: Finding $\nabla\phi$ analytically

$$\frac{\partial\phi}{\partial x} = \frac{\partial}{\partial x}(4xz^3 - 3x^2y^2z) = 4z^3 - 6xy^2z$$

$$\frac{\partial\phi}{\partial y} = \frac{\partial}{\partial y}(4xz^3 - 3x^2y^2z) = 0 - 6x^2yz = -6x^2yz$$

$$\frac{\partial\phi}{\partial z} = \frac{\partial}{\partial z}(4xz^3 - 3x^2y^2z) = 12xz^2 - 3x^2y^2$$

Now, piece them together into the vector format:
$$\nabla\phi = \mathbf{i}(4z^3 - 6xy^2z) + \mathbf{j}(-6x^2yz) + \mathbf{k}(12xz^2 - 3x^2y^2)$$

### Execution of Step 3: Evaluating $\nabla\phi$ at $(2, -1, 2)$

Substitute $x = 2$, $y = -1$, and $z = 2$:

$$\mathbf{i}\text{-component} = 4(2)^3 - 6(2)(-1)^2(2) = 4(8) - 6(2)(1)(2) = 32 - 24 = 8$$

$$\mathbf{j}\text{-component} = -6(2)^2(-1)(2) = -6(4)(-1)(2) = 48$$

$$\mathbf{k}\text{-component} = 12(2)(2)^2 - 3(2)^2(-1)^2 = 12(2)(4) - 3(4)(1) = 96 - 12 = 84$$

Combine the evaluated components:
$$\nabla\phi_{(2,-1,2)} = 8\mathbf{i} + 48\mathbf{j} + 84\mathbf{k}$$

### Execution of Step 4: Finding Magnitude of $\mathbf{a} = 2\mathbf{i} + 3\mathbf{j} + 6\mathbf{k}$

$$|\mathbf{a}| = \sqrt{2^2 + 3^2 + 6^2}$$

$$|\mathbf{a}| = \sqrt{4 + 9 + 36}$$

$$|\mathbf{a}| = \sqrt{49} = 7$$

### Execution of Step 5: Dot Product and Final Division

$$\text{D.D} = \frac{(8\mathbf{i} + 48\mathbf{j} + 84\mathbf{k}) \cdot (2\mathbf{i} + 3\mathbf{j} + 6\mathbf{k})}{7}$$

$$\text{D.D} = \frac{(8 \times 2) + (48 \times 3) + (84 \times 6)}{7}$$

$$\text{D.D} = \frac{16 + 144 + 504}{7}$$

$$\text{D.D} = \frac{664}{7}$$
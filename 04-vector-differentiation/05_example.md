# Engineering Mathematics Study Note: Directional Derivative Between Two Points

## 1. IDENTIFY
The concept being executed is finding the **Directional Derivative** of a scalar field $\phi$ in the specific direction connecting an initial point $A$ to a terminal point $B$ in 3D space.

---

## 2. THE FORMULA

The Direction Vector $\mathbf{a}$ from point $A(x_1, y_1, z_1)$ to point $B(x_2, y_2, z_2)$ is found by coordinate subtraction:
$$\mathbf{a} = \vec{AB} = (x_2 - x_1)\mathbf{i} + (y_2 - y_1)\mathbf{j} + (z_2 - z_1)\mathbf{k}$$

The Directional Derivative (D.D) of $\phi$ along vector $\mathbf{a}$ is:
$$\text{D.D} = \frac{\nabla\phi \cdot \mathbf{a}}{|\mathbf{a}|}$$

Where the Gradient vector evaluated at the starting point $A$ is:
$$\nabla\phi = \mathbf{i}\frac{\partial\phi}{\partial x} + \mathbf{j}\frac{\partial\phi}{\partial y} + \mathbf{k}\frac{\partial\phi}{\partial z}$$

---

## 3. THE ALGORITHM

### Step 1: Compute the partial derivatives
Find the derivative of $\phi$ with respect to $x$, $y$, and $z$ independently, treating all other variables as numbers.

### Step 2: Construct and evaluate the Gradient vector at point $A$
Assemble $\nabla\phi$ and substitute the coordinates of the *starting point* $A(1, -2, 1)$ into it.

### Step 3: Find the displacement direction vector $\mathbf{a}$
Subtract the coordinates of starting point $A$ from destination point $B$:
$$\mathbf{a} = \vec{AB} = \text{Vector}(B - A)$$

### Step 4: Calculate the magnitude of the displacement vector
Find the geometric length of the direction vector $\mathbf{a}$.
$$|\mathbf{a}| = \sqrt{(a_x)^2 + (a_y)^2 + (a_z)^2}$$

### Step 5: Perform the Dot Product and scale
Multiply the matching directional components of the evaluated gradient vector and vector $\mathbf{a}$ together, add them up, and divide by the magnitude found in Step 4.

---

## 4. THE MECHANICS

### Vector from Point A to Point B ($\vec{AB}$)
To find the vector path between two points, always subtract the *start* from the *finish* ($B - A$). 
* If you start at $x=1$ and finish at $x=2$, your displacement is $2 - 1 = 1$.
* If you start at $y=-2$ and finish at $y=6$, your displacement is $6 - (-2) = 6 + 2 = 8$.

### Cubing Negative Numbers
When evaluating the gradient component for an odd power like $y^3$ where $y = -2$:
* $(-2)^3 = (-2) \times (-2) \times (-2) = -8$
* Multiplying by the constant multiplier 4: $4 \times (-8) = -32$

---

## 5. STEP-BY-STEP WORKED SOLUTION

### Execution of Step 1: Compute Partial Derivatives
$$\frac{\partial\phi}{\partial x} = \frac{\partial}{\partial x}(x^4 + y^4 + z^4) = 4x^3$$
$$\frac{\partial\phi}{\partial y} = \frac{\partial}{\partial y}(x^4 + y^4 + z^4) = 4y^3$$
$$\frac{\partial\phi}{\partial z} = \frac{\partial}{\partial z}(x^4 + y^4 + z^4) = 4z^3$$

### Execution of Step 2: Evaluate Gradient at $A(1, -2, 1)$
$$\nabla\phi = 4x^3\mathbf{i} + 4y^3\mathbf{j} + 4z^3\mathbf{k}$$
$$\nabla\phi_{(1,-2,1)} = 4(1)^3\mathbf{i} + 4(-2)^3\mathbf{j} + 4(1)^3\mathbf{k}$$
$$\nabla\phi_{(1,-2,1)} = 4(1)\mathbf{i} + 4(-8)\mathbf{j} + 4(1)\mathbf{k}$$
$$\nabla\phi_{(1,-2,1)} = 4\mathbf{i} - 32\mathbf{j} + 4\mathbf{k}$$

### Execution of Step 3: Compute Direction Vector $\mathbf{a} = \vec{AB}$
Given $A(1, -2, 1)$ and $B(2, 6, -1)$:
$$\mathbf{a} = (2 - 1)\mathbf{i} + (6 - (-2))\mathbf{j} + (-1 - 1)\mathbf{k}$$
$$\mathbf{a} = 1\mathbf{i} + 8\mathbf{j} - 2\mathbf{k}$$

### Execution of Step 4: Calculate Magnitude $|\mathbf{a}|$
$$|\mathbf{a}| = \sqrt{1^2 + 8^2 + (-2)^2}$$
$$|\mathbf{a}| = \sqrt{1 + 64 + 4}$$
$$|\mathbf{a}| = \sqrt{69}$$

### Execution of Step 5: Dot Product and Final Calculation
$$\text{D.D} = \frac{(4\mathbf{i} - 32\mathbf{j} + 4\mathbf{k}) \cdot (1\mathbf{i} + 8\mathbf{j} - 2\mathbf{k})}{\sqrt{69}}$$

$$\text{D.D} = \frac{(4 \times 1) + (-32 \times 8) + (4 \times -2)}{\sqrt{69}}$$

$$\text{D.D} = \frac{4 - 256 - 8}{\sqrt{69}}$$

$$\text{D.D} = \frac{-260}{\sqrt{69}}$$
# Engineering Mathematics Study Note: Directional Derivative Along a Line

## 1. IDENTIFY
The concept being executed is finding the **Directional Derivative** of a scalar field $\phi$ when the direction is given as a **3D Straight Line Equation in Symmetric Form** instead of a direct vector.

---

## 2. THE FORMULA

A straight line in 3D symmetric form is written as:
$$\frac{x - x_0}{l} = \frac{y - y_0}{m} = \frac{z - z_0}{n}$$

Where the denominators ($l, m, n$) directly represent the direction ratios of the line. Therefore, the direction vector $\mathbf{a}$ parallel to this line is:
$$\mathbf{a} = l\mathbf{i} + m\mathbf{j} + n\mathbf{k}$$

The Directional Derivative (D.D) along this line direction is:
$$\text{D.D} = \frac{\nabla\phi \cdot \mathbf{a}}{|\mathbf{a}|}$$

---

## 3. THE ALGORITHM

### Step 1: Extract the Direction Vector from the Line
Look at the denominators of the given line equation $\frac{x}{l} = \frac{y}{m} = \frac{z}{n}$. These values form the components of your direction vector $\mathbf{a} = l\mathbf{i} + m\mathbf{j} + n\mathbf{k}$.

### Step 2: Compute the Gradient vector ($\nabla\phi$)
Find the standard partial derivatives of the function $\phi$ with respect to $x$, $y$, and $z$.
$$\nabla\phi = \mathbf{i}\frac{\partial\phi}{\partial x} + \mathbf{j}\frac{\partial\phi}{\partial y} + \mathbf{k}\frac{\partial\phi}{\partial z}$$

### Step 3: Evaluate $\nabla\phi$ at the given point
Substitute the given spatial coordinates into your gradient expression to convert variables into static numbers.

### Step 4: Calculate the magnitude of the direction vector
Find the total length of the vector extracted in Step 1.
$$|\mathbf{a}| = \sqrt{l^2 + m^2 + n^2}$$

### Step 5: Compute the Dot Product ratio
Take the dot product of the evaluated gradient vector and the direction vector, then divide by the vector's magnitude.

---

## 4. THE MECHANICS

### Decoding Symmetric Line Equations
When a line is given as $\frac{x}{3} = \frac{y}{4} = \frac{z}{5}$, it means that for every 3 units you move along the x-axis, you must move 4 units along the y-axis and 5 units along the z-axis. The denominators are ready-to-use vector coordinates. You do not need to perform any calculations on the line equation itself to find the vector.

### Simple Partial Differentiation of Squared Terms
Using the power rule $\frac{d}{dx}(x^2) = 2x$:
* When differentiating $\phi = x^2 + y^2 + z^2$ with respect to $x$, the variables $y^2$ and $z^2$ drop out completely to $0$.
$$\frac{\partial\phi}{\partial x} = 2x$$

---

## 5. STEP-BY-STEP WORKED SOLUTION

Based on Problem 1: Find the directional derivative of $\phi = x^2 + y^2 + z^2$ in the direction of the line $\frac{x}{3} = \frac{y}{4} = \frac{z}{5}$ at $(1, 2, 3)$.

### Execution of Step 1: Extract the Direction Vector
The denominators are $3, 4, 5$.
$$\mathbf{a} = 3\mathbf{i} + 4\mathbf{j} + 5\mathbf{k}$$

### Execution of Step 2: Compute Gradient $\nabla\phi$
$$\frac{\partial\phi}{\partial x} = \frac{\partial}{\partial x}(x^2 + y^2 + z^2) = 2x$$
$$\frac{\partial\phi}{\partial y} = \frac{\partial}{\partial y}(x^2 + y^2 + z^2) = 2y$$
$$\frac{\partial\phi}{\partial z} = \frac{\partial}{\partial z}(x^2 + y^2 + z^2) = 2z$$

Assemble the components:
$$\nabla\phi = 2x\mathbf{i} + 2y\mathbf{j} + 2z\mathbf{k}$$

### Execution of Step 3: Evaluate Gradient at $(1, 2, 3)$
Substitute $x = 1, y = 2, z = 3$:
$$\nabla\phi_{(1,2,3)} = 2(1)\mathbf{i} + 2(2)\mathbf{j} + 2(3)\mathbf{k}$$
$$\nabla\phi_{(1,2,3)} = 2\mathbf{i} + 4\mathbf{j} + 6\mathbf{k}$$

### Execution of Step 4: Calculate Magnitude of $\mathbf{a}$
$$|\mathbf{a}| = \sqrt{3^2 + 4^2 + 5^2}$$
$$|\mathbf{a}| = \sqrt{9 + 16 + 25}$$
$$|\mathbf{a}| = \sqrt{50} = \sqrt{25 \times 2} = 5\sqrt{2}$$

### Execution of Step 5: Dot Product and Final Calculation
$$\text{D.D} = \frac{(2\mathbf{i} + 4\mathbf{j} + 6\mathbf{k}) \cdot (3\mathbf{i} + 4\mathbf{j} + 5\mathbf{k})}{5\sqrt{2}}$$

$$\text{D.D} = \frac{(2 \times 3) + (4 \times 4) + (6 \times 5)}{5\sqrt{2}}$$

$$\text{D.D} = \frac{6 + 16 + 30}{5\sqrt{2}}$$

$$\text{D.D} = \frac{52}{5\sqrt{2}}$$

To rationalize the denominator (multiply top and bottom by $\sqrt{2}$):
$$\text{D.D} = \frac{52\sqrt{2}}{5 \times 2}$$
$$\text{D.D} = \frac{52\sqrt{2}}{10} = \frac{26\sqrt{2}}{5}$$
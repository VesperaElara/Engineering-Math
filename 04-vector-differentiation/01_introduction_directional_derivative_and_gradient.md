# Engineering Mathematics Study Note: Directional Derivative and Gradient

## 1. IDENTIFY
The concept presented on this board is the **Gradient of a Scalar Field** and its application in finding the **Directional Derivative (D.D)** of a function along a specific vector direction.

---

## 2. THE FORMULA

The vector differential operator Del ($\nabla$):
$$\nabla = \mathbf{i} \frac{\partial}{\partial x} + \mathbf{j} \frac{\partial}{\partial y} + \mathbf{k} \frac{\partial}{\partial z}$$

The Gradient of a scalar function $\phi$:
$$\nabla \phi = \mathbf{i} \frac{\partial \phi}{\partial x} + \mathbf{j} \frac{\partial \phi}{\partial y} + \mathbf{k} \frac{\partial \phi}{\partial z}$$

The Directional Derivative of $\phi$ in the direction of a vector $\mathbf{a}$:
$$\text{D.D} = \frac{\nabla \phi \cdot \mathbf{a}}{|\mathbf{a}|}$$

The Maximum Directional Derivative:
$$\text{Max D.D} = |\nabla \phi|$$

---

## 3. THE ALGORITHM

To solve a standard Directional Derivative problem at a given point $A$ in the direction of a line segment $AB$ (where point $B$ is given):

### Step 1: Compute the partial derivatives
Find the individual derivatives of the function $\phi$ with respect to $x$, $y$, and $z$ independently.
$$\frac{\partial \phi}{\partial x}, \quad \frac{\partial \phi}{\partial y}, \quad \frac{\partial \phi}{\partial z}$$

### Step 2: Construct the Gradient vector
Multiply each partial derivative by its respective unit vector ($\mathbf{i}, \mathbf{j}, \mathbf{k}$) and sum them to form $\nabla \phi$.
$$\nabla \phi = \mathbf{i} \frac{\partial \phi}{\partial x} + \mathbf{j} \frac{\partial \phi}{\partial y} + \mathbf{k} \frac{\partial \phi}{\partial z}$$

### Step 3: Evaluate the Gradient at the given point
Substitute the numerical coordinates of the initial point $A(x_1, y_1, z_1)$ into the variables of your $\nabla \phi$ expression to get a constant vector.

### Step 4: Find the direction vector
Calculate the displacement vector $\mathbf{a} = \vec{AB}$ by subtracting the coordinates of the starting point $A$ from the destination point $B$.
$$\mathbf{a} = (x_2 - x_1)\mathbf{i} + (y_2 - y_1)\mathbf{j} + (z_2 - z_1)\mathbf{k}$$

### Step 5: Calculate the magnitude of the direction vector
Find the length (modulus) of vector $\mathbf{a}$.
$$|\mathbf{a}| = \sqrt{(a_x)^2 + (a_y)^2 + (a_z)^2}$$

### Step 6: Compute the final Dot Product
Take the dot product of the evaluated gradient vector from Step 3 and the direction vector from Step 4, then divide the result by the magnitude from Step 5.
$$\text{D.D} = \frac{\nabla \phi \cdot \mathbf{a}}{|\mathbf{a}|}$$

---

## 4. THE MECHANICS

### Partial Differentiation ($\frac{\partial}{\partial x}$)
When differentiating partially with respect to one variable, treat all other variables as standard hardcoded numbers (constants).
* **Example 1:** If $\Phi = xz^2$, finding $\frac{\partial \Phi}{\partial x}$ means $z^2$ is treated like a constant multiplier (like the number $5$ in $5x$). The derivative of $x$ is $1$, so the result is $1 \cdot z^2 = z^2$.
* **Example 2:** If $\Phi = -5yz$, finding $\frac{\partial \Phi}{\partial x}$ results in $0$ because there is no $x$ variable present in that term, making the entire term act like a standalone constant.

### Vector Components ($\mathbf{i}, \mathbf{j}, \mathbf{k}$)
These symbols act as placeholders to indicate direction in 3D space.
* $\mathbf{i}$ points along the x-axis.
* $\mathbf{j}$ points along the y-axis.
* $\mathbf{k}$ points along the z-axis.
They do not mix algebraically with each other during addition or subtraction; they keep the values separated into distinct slots.

### The Vector Dot Product ($\cdot$)
When multiplying two vectors using a dot product, multiply matching directional components together and add the resulting values to produce a single regular number (scalar).
$$\mathbf{u} = u_x\mathbf{i} + u_y\mathbf{j} + u_z\mathbf{k}$$
$$\mathbf{v} = v_x\mathbf{i} + v_y\mathbf{j} + v_z\mathbf{k}$$
$$\mathbf{u} \cdot \mathbf{v} = (u_x \cdot v_x) + (u_y \cdot v_y) + (u_z \cdot v_z)$$

---

## 5. STEP-BY-STEP WORKED EXAMPLE

Based on the second problem on the board: Find $\nabla\Phi$ for $\Phi = x z^2 - 5yz + xz$ at the point $(1, -1, 2)$.

### Execution of Step 1: Compute Partial Derivatives

Differentiate $\Phi$ with respect to $x$ (treat $y$ and $z$ as constants):
$$\frac{\partial\Phi}{\partial x} = (1)z^2 - 0 + (1)z$$
$$\frac{\partial\Phi}{\partial x} = z^2 + z$$

Differentiate $\Phi$ with respect to $y$ (treat $x$ and $z$ as constants):
$$\frac{\partial\Phi}{\partial y} = 0 - 5(1)z + 0$$
$$\frac{\partial\Phi}{\partial y} = -5z$$

Differentiate $\Phi$ with respect to $z$ (treat $x$ and $y$ as constants):
$$\frac{\partial\Phi}{\partial z} = x(2z) - 5y(1) + x(1)$$
$$\frac{\partial\Phi}{\partial z} = 2zx - 5y + x$$

### Execution of Step 2: Assemble the Gradient Formula

Combine the components together:
$$\nabla\Phi = \mathbf{i}\left(\frac{\partial\Phi}{\partial x}\right) + \mathbf{j}\left(\frac{\partial\Phi}{\partial y}\right) + \mathbf{k}\left(\frac{\partial\Phi}{\partial z}\right)$$
$$\nabla\Phi = \mathbf{i}(z^2 + z) + \mathbf{j}(-5z) + \mathbf{k}(2zx - 5y + x)$$

### Execution of Step 3: Substitute Point Values

Plug in the values $x = 1$, $y = -1$, and $z = 2$:
$$\nabla\Phi_{(1,-1,2)} = \mathbf{i}(2^2 + 2) + \mathbf{j}(-5 \times 2) + \mathbf{k}(2(2)(1) - 5(-1) + 1)$$
$$\nabla\Phi_{(1,-1,2)} = \mathbf{i}(4 + 2) + \mathbf{j}(-10) + \mathbf{k}(4 + 5 + 1)$$
$$\nabla\Phi = 6\mathbf{i} - 10\mathbf{j} + 10\mathbf{k}$$
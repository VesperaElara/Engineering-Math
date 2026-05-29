# Vector Differentiation: Solenoidal and Irrotational Vector Fields

## 1. Solenoidal Fields

### Name of Concept
Divergence of a Vector Field and Solenoidal Fields.

### Core Mathematical Formula

The **Divergence** of a vector field $\bar{F}$ is computed using the dot product of the del operator ($\nabla$) and the vector field:

$$\text{div } \bar{F} = \nabla \cdot \bar{F} = \frac{\partial f_1}{\partial x} + \frac{\partial f_2}{\partial y} + \frac{\partial f_3}{\partial z}$$

A vector field is defined as **solenoidal** if and only if its divergence evaluates to zero:

$$\nabla \cdot \bar{F} = 0$$

### Beginner-Friendly Explanation of Operations



1. **What is Divergence?** Divergence measures the net outward or inward flow of a vector field from a given point. Think of it like fluid expanding out from a source (positive divergence) or compressing into a drain/sink (negative divergence).
2. **The Dot Product Process:** To calculate divergence, you match components. You take the derivative of the first component ($f_1$) with respect to $x$, add the derivative of the second component ($f_2$) with respect to $y$, and add the derivative of the third component ($f_3$) with respect to $z$.
3. **The Solenoidal Property:** If the final scalar answer is exactly $0$, it means the fluid is completely incompressible. Whatever amount flows into a point must flow out of it simultaneously; there are no hidden sources or drains creating or destroying fluid.

---

## 2. Irrotational Fields Review

### Core Mathematical Formula

$$\text{curl } \bar{F} = \nabla \times \bar{F} = \begin{vmatrix} \bar{i} & \bar{j} & \bar{k} \\ \frac{\partial}{\partial x} & \frac{\partial}{\partial y} & \frac{\partial}{\partial z} \\ f_1 & f_2 & f_3 \end{vmatrix} = \bar{0}$$

### Beginner-Friendly Explanation of Operations

As established previously, if the cross product between the del operator and the vector field expands to equal a net zero vector ($\bar{0}$), it means there are no rotational rotations or loops within the field. 

---

## 3. Step-by-Step Problem Solution

### Question
Show that the vector field $\bar{F} = (y^2 - z^2 + 3yz - 2x)\bar{i} + (3xz + 2xy)\bar{j} + (3xy - 2xz + 2z)\bar{k}$ is both irrotational and solenoidal.

### Step 1: Identify the components of the vector field
Extract the individual scalar components $f_1$, $f_2$, and $f_3$:

$$f_1 = y^2 - z^2 + 3yz - 2x$$

$$f_2 = 3xz + 2xy$$

$$f_3 = 3xy - 2xz + 2z$$

### Step 2: Compute individual partial derivatives for Divergence
Differentiate $f_1$ with respect to $x$ (treat $y$ and $z$ as constants):

$$\frac{\partial f_1}{\partial x} = -2$$

Differentiate $f_2$ with respect to $y$ (treat $x$ and $z$ as constants):

$$\frac{\partial f_2}{\partial y} = 2x$$

Differentiate $f_3$ with respect to $z$ (treat $x$ and $y$ as constants):

$$\frac{\partial f_3}{\partial z} = -2x + 2$$

### Step 3: Sum the results to find Divergence ($\nabla \cdot \bar{F}$)

$$\nabla \cdot \bar{F} = (-2) + (2x) + (-2x + 2)$$

Combine like terms to simplify:

$$\nabla \cdot \bar{F} = -2 + 2x - 2x + 2 = 0$$

Since $\nabla \cdot \bar{F} = 0$, the vector field $\bar{F}$ is **solenoidal**.

### Step 4: Set up the Curl matrix determinant
To prove the field is irrotational, substitute the component equations into the $3 \times 3$ curl matrix:

$$\nabla \times \bar{F} = \begin{vmatrix} \bar{i} & \bar{j} & \bar{k} \\ \frac{\partial}{\partial x} & \frac{\partial}{\partial y} & \frac{\partial}{\partial z} \\ (y^2 - z^2 + 3yz - 2x) & (3xz + 2xy) & (3xy - 2xz + 2z) \end{vmatrix}$$

### Step 5: Expand the determinant for the $\bar{i}$ component

$$\text{Component } \bar{i} = \bar{i} \left[ \frac{\partial}{\partial y}(3xy - 2xz + 2z) - \frac{\partial}{\partial z}(3xz + 2xy) \right]$$

Calculate the inner partial derivatives:

$$\text{Component } \bar{i} = \bar{i} [3x - 3x] = \bar{i}(0)$$

### Step 6: Expand the determinant for the $\bar{j}$ component

$$\text{Component } \bar{j} = -\bar{j} \left[ \frac{\partial}{\partial x}(3xy - 2xz + 2z) - \frac{\partial}{\partial z}(y^2 - z^2 + 3yz - 2x) \right]$$

Calculate the inner partial derivatives:

$$\text{Component } \bar{j} = -\bar{j} [(3y - 2z) - (-2z + 3y)]$$

Simplify the terms inside the bracket:

$$\text{Component } \bar{j} = -\bar{j} [3y - 2z + 2z - 3y] = -\bar{j}(0)$$

### Step 7: Expand the determinant for the $\bar{k}$ component

$$\text{Component } \bar{k} = \bar{k} \left[ \frac{\partial}{\partial x}(3xz + 2xy) - \frac{\partial}{\partial y}(y^2 - z^2 + 3yz - 2x) \right]$$

Calculate the inner partial derivatives:

$$\text{Component } \bar{k} = \bar{k} [(3z + 2y) - (2y + 3z)]$$

Simplify the terms inside the bracket:

$$\text{Component } \bar{k} = \bar{k} [3z + 2y - 2y - 3z] = \bar{k}(0)$$

### Step 8: Combine the vector components

$$\nabla \times \bar{F} = 0\bar{i} - 0\bar{j} + 0\bar{k} = \bar{0}$$

Since $\nabla \times \bar{F} = \bar{0}$, the vector field $\bar{F}$ is **irrotational**.
# Vector Differentiation: Directional Derivative & Surface Angles

## 1. Directional Derivative

### Name of Concept
Directional Derivative (D.D) and Maximum Directional Derivative.

### Core Mathematical Formulas

The Directional Derivative of a scalar function $\phi$ in the direction of a vector $\bar{a}$ is given by:

$$\text{Directional Derivative} = \frac{\nabla \phi \cdot \bar{a}}{|\bar{a}|}$$

The Maximum Directional Derivative occurs in the direction of the gradient vector itself, and its magnitude is given by:

$$\text{Maximum Directional Derivative} = |\nabla \phi|$$

### Beginner-Friendly Explanation of Operations

Vector differentiation allows us to calculate how functions change as we move through space. 

1. **The Gradient ($\nabla \phi$):** The symbol $\nabla$ (pronounced "del" or "nabla") represents the vector differential operator. When applied to a scalar function $\phi(x, y, z)$, it produces a vector called the gradient. It represents the rate and direction of the fastest spatial increase of the function.
2. **The Unit Vector $\left(\frac{\bar{a}}{|\bar{a}|}\right)$:** To check the rate of change in a *specific* direction specified by vector $\bar{a}$, we must eliminate the effect of the vector's length. We do this by dividing $\bar{a}$ by its absolute magnitude $|\bar{a}|$. This creates a unit vector (a vector with a length of 1) pointing in that exact direction.
3. **The Dot Product ($\cdot$):** We compute the dot product between the gradient vector $\nabla \phi$ and the direction's unit vector. The result is a simple scalar number representing exactly how fast the function changes per unit distance in that direction.

---

## 2. Angle Between Two Surfaces

### Name of Concept
Angle of Intersection Between Two Scalar Surfaces.

### Core Mathematical Formula

The angle $\theta$ between two intersecting surfaces at a specific point is equal to the angle between their normal vectors (gradients) at that point:

$$\cos \theta = \frac{\nabla u \cdot \nabla v}{|\nabla u| |\nabla v|}$$

### Beginner-Friendly Explanation of Operations

1. **Represent the Surfaces:** We rewrite the given surface equations in the form $u(x, y, z) = 0$ and $v(x, y, z) = 0$.
2. **Find the Normal Vectors:** The gradient vector $\nabla u$ computed at a specific point is always mathematically perpendicular (normal) to the surface $u$ at that point. By computing $\nabla u$ and $\nabla v$, we obtain two geometric arrows sticking straight out of the two surfaces at their intersection point.
3. **Calculate the Angle:** We use the geometric definition of the vector dot product to extract the cosine of the angle ($\cos \theta$) between these two normal arrows.

---

## 3. Step-by-Step Problem Solution

### Question
Find the angle between the surfaces $x\log z + 1 - y^2 = 0$ and $x^2y + z = 2$ at the point $(1, 1, 1)$.

### Step 1: Define the first scalar surface function
Let the first surface be defined as $u$:

$$u = x\log z + 1 - y^2$$

### Step 2: Set up the gradient formula for the first surface
The gradient operator uses partial derivatives along the three coordinate axes:

$$\nabla u = \bar{i} \frac{\partial u}{\partial x} + \bar{j} \frac{\partial u}{\partial y} + \bar{k} \frac{\partial u}{\partial z}$$

### Step 3: Compute the partial derivatives for $u$
When differentiating with respect to one variable, treat all other variables as constant numbers.

Differentiating $u$ with respect to $x$ treating $y$ and $z$ as constants:

$$\frac{\partial u}{\partial x} = \log z$$

Differentiating $u$ with respect to $y$ treating $x$ and $z$ as constants:

$$\frac{\partial u}{\partial y} = -2y$$

Differentiating $u$ with respect to $z$ treating $x$ and $y$ as constants:

$$\frac{\partial u}{\partial z} = x \cdot \frac{1}{z}$$

### Step 4: Assemble the gradient vector field for $u$
Substitute the partial derivative expressions back into the gradient setup:

$$\nabla u = \bar{i} (\log z) + \bar{j} (-2y) + \bar{k} \left(\frac{x}{z}\right)$$

### Step 5: Evaluate the gradient vector at the point $(1, 1, 1)$
Substitute $x = 1$, $y = 1$, and $z = 1$ into the vector expression. Note that $\log 1 = 0$:

$$\nabla u_{(1,1,1)} = \bar{i} (\log 1) + \bar{j} (-2(1)) + \bar{k} \left(\frac{1}{1}\right)$$

$$\nabla u_{(1,1,1)} = \bar{i} (0) - 2\bar{j} + \bar{k}$$

$$\bar{a} = \nabla u_{(1,1,1)} = -2\bar{j} + \bar{k}$$

This vector $\bar{a}$ represents the normal vector to the first surface at the given point.
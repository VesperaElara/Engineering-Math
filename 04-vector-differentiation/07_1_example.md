# Vector Differentiation: Orthogonal Surfaces

## 1. Orthogonality of Surfaces

### Name of Concept
Orthogonal Surfaces (Perpendicular Surfaces).

### Core Mathematical Formula

Two surfaces are orthogonal (perpendicular to each other) at a given point of intersection if their respective normal vector gradients ($\nabla u$ and $\nabla v$) are perpendicular. This condition is satisfied when their vector dot product equals zero:

$$\nabla u \cdot \nabla v = 0$$

### Beginner-Friendly Explanation of Operations

1. **Orthogonal Means $90^\circ$:** In vector calculus, the word "orthogonal" simply means perpendicular or intersecting at a right angle.
2. **Gradients as Normals:** For any surface equation written in the form $u(x, y, z) = 0$, the gradient $\nabla u$ gives a vector that points straight out of the surface. This is its normal vector.
3. **The Dot Product Condition:** If two surfaces meet at a $90^\circ$ angle, their normal vectors must also meet at a $90^\circ$ angle. The dot product of any two perpendicular vectors is always zero because $\cos(90^\circ) = 0$. We use this algebraic property to set up an equation and solve for unknown constants.
4. **Point of Intersection Constraint:** Since the given point lies on both surfaces, the coordinates of the point must satisfy the equations of both surfaces. This provides an additional algebraic equation to find our unknowns.

---

## 2. Step-by-Step Problem Solution

### Question
Find the constants $a$ and $b$ so that the surface $ax^2 - byz = (a + 2)x$ will be orthogonal to the surface $4x^2y + z^3 = 4$ at the point $(1, -1, 2)$.

### Step 1: Define the functions by moving all terms to one side
Let the first surface be $u$ and the second surface be $v$:

$$u = ax^2 - byz - (a + 2)x$$

$$v = 4x^2y + z^3 - 4$$

### Step 2: Utilize the point constraint on the first surface
Because the point $(1, -1, 2)$ lies directly on the surface $u$, substituting $x = 1$, $y = -1$, and $z = 2$ into the equation of $u$ must equal $0$:

$$a(1)^2 - b(-1)(2) - (a + 2)(1) = 0$$

$$a + 2b - a - 2 = 0$$

$$2b - 2 = 0$$

$$2b = 2$$

$$b = 1$$

### Step 3: Set up and calculate the gradient for the first surface $u$
The gradient vector field formula is:

$$\nabla u = \bar{i} \frac{\partial u}{\partial x} + \bar{j} \frac{\partial u}{\partial y} + \bar{k} \frac{\partial u}{\partial z}$$

Compute the partial derivatives of $u$:

$$\frac{\partial u}{\partial x} = 2ax - (a + 2) = 2ax - a - 2$$

$$\frac{\partial u}{\partial y} = -bz$$

$$\frac{\partial u}{\partial z} = -by$$

Combine them into the gradient vector:

$$\nabla u = \bar{i} (2ax - a - 2) + \bar{j} (-bz) + \bar{k} (-by)$$

### Step 4: Evaluate $\nabla u$ at the point $(1, -1, 2)$
Substitute $x = 1$, $y = -1$, and $z = 2$ into our gradient expression to get the normal vector $\bar{a}$:

$$\bar{a} = \nabla u_{(1,-1,2)} = \bar{i} (2a(1) - a - 2) + \bar{j} (-b(2)) + \bar{k} (-b(-1))$$

$$\bar{a} = \bar{i} (a - 2) + \bar{j} (-2b) + \bar{k} (b)$$

### Step 5: Set up and calculate the gradient for the second surface $v$
The gradient vector field formula is:

$$\nabla v = \bar{i} \frac{\partial v}{\partial x} + \bar{j} \frac{\partial v}{\partial y} + \bar{k} \frac{\partial v}{\partial z}$$

Compute the partial derivatives of $v$:

$$\frac{\partial v}{\partial x} = 8xy$$

$$\frac{\partial v}{\partial y} = 4x^2$$

$$\frac{\partial v}{\partial z} = 3z^2$$

Combine them into the gradient vector:

$$\nabla v = \bar{i} (8xy) + \bar{j} (4x^2) + \bar{k} (3z^2)$$

### Step 6: Evaluate $\nabla v$ at the point $(1, -1, 2)$
Substitute $x = 1$, $y = -1$, and $z = 2$ into our gradient expression to get the normal vector $\bar{b}$:

$$\bar{b} = \nabla v_{(1,-1,2)} = \bar{i} (8(1)(-1)) + \bar{j} (4(1)^2) + \bar{k} (3(2)^2)$$

$$\bar{b} = -8\bar{i} + 4\bar{j} + 12\bar{k}$$

### Step 7: Apply the orthogonality condition ($\bar{a} \cdot \bar{b} = 0$)
Multiply corresponding components ($\bar{i}$ with $\bar{i}$, $\bar{j}$ with $\bar{j}$, $\bar{k}$ with $\bar{k}$) and sum them up:

$$(a - 2)(-8) + (-2b)(4) + (b)(12) = 0$$

$$-8a + 16 - 8b + 12b = 0$$

$$-8a + 16 + 4b = 0$$

### Step 8: Substitute the value of $b$ to solve for $a$
From Step 2, we already know that $b = 1$. Substitute this value into our orthogonality equation:

$$-8a + 16 + 4(1) = 0$$

$$-8a + 20 = 0$$

$$8a = 20$$

$$a = \frac{20}{8}$$

$$a = \frac{5}{2}$$

### Final Answer
The required constant values are:

$$a = \frac{5}{2}$$

$$b = 1$$
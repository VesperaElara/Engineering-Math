# Vector Integration: Stokes' Theorem over a Paraboloid Surface

## 1. Boundary Path Evaluation using Stokes' Theorem

### Name of Concept
Stokes' Theorem (Evaluating a Surface Integral via its Flat Boundary Curve).

### Core Mathematical Formula

$$\oint_C \bar{F} \cdot d\bar{r} = \iint_S (\nabla \times \bar{F}) \cdot \hat{n} \, dS$$

### Beginner-Friendly Explanation of Operations



1. **Simplifying the Path Integration:** The problem asks us to evaluate a line integral along the boundary curve $C$ of an open 3D paraboloid dome ($x^2 + y^2 = 4 - z$). Instead of performing a direct line integration around the rim, Stokes' Theorem lets us analyze the curl of the vector field over the surface capping that rim.
2. **Identifying the Rim ($C$):** The problem specifies that the paraboloid surface exists for $z \geq 0$. The lower rim or boundary curve $C$ occurs exactly where the dome hits the floor ($z = 0$). Substituting $z = 0$ into the paraboloid equation reveals that the boundary is a perfect circle centered at the origin on the flat $xy$-plane.
3. **The Flat Surface Substitute Strategy:** Stokes' Theorem lets us pick *any* surface bounded by the loop $C$. Instead of using the bulging, curved skin of the 3D paraboloid dome, we can choose the perfectly flat, circular 2D disk that seals the bottom of the dome on the $xy$-plane ($z = 0$). 
4. **Evaluating the Curl Vector Field:** We first compute the curl determinant ($\nabla \times \bar{F}$). If the components inside the curl vector happen to subtract and cancel out perfectly, it means the field has zero rotational tendency ($\nabla \times \bar{F} = \bar{0}$). Integrating a zero field over any area yields an immediate result of $0$, completely bypassing any messy coordinate conversions.

---

## 2. Step-by-Step Problem Solution

### Question
Use Stokes' Theorem to evaluate $\oint_C \bar{F} \cdot d\bar{r}$ where $\bar{F} = (x - y - z)\bar{i} + (y - z - x)\bar{j} + (z - x - y)\bar{k}$ over the paraboloid surface $x^2 + y^2 = 4 - z, z \geq 0$.

### Step 1: Extract vector field components
Identify the scalar function parts $f_1$, $f_2$, and $f_3$:

$$f_1 = x - y - z$$

$$f_2 = y - z - x$$

$$f_3 = z - x - y$$

### Step 2: Set up and evaluate the Curl determinant matrix

$$\nabla \times \bar{F} = \begin{vmatrix} \bar{i} & \bar{j} & \bar{k} \\ \frac{\partial}{\partial x} & \frac{\partial}{\partial y} & \frac{\partial}{\partial z} \\ (x - y - z) & (y - z - x) & (z - x - y) \end{vmatrix}$$

Expand the determinant component by component:

$$\text{Component } \bar{i} = \bar{i} \left[ \frac{\partial}{\partial y}(z - x - y) - \frac{\partial}{\partial z}(y - z - x) \right] = \bar{i}[-1 - (-1)] = \bar{i}[-1 + 1] = \bar{0}$$

$$\text{Component } \bar{j} = -\bar{j} \left[ \frac{\partial}{\partial x}(z - x - y) - \frac{\partial}{\partial z}(x - y - z) \right] = -\bar{j}[-1 - (-1)] = -\bar{j}[-1 + 1] = \bar{0}$$

$$\text{Component } \bar{k} = \bar{k} \left[ \frac{\partial}{\partial x}(y - z - x) - \frac{\partial}{\partial y}(x - y - z) \right] = \bar{k}[-1 - (-1)] = \bar{k}[-1 + 1] = \bar{0}$$

Combine the components:

$$\nabla \times \bar{F} = 0\bar{i} - 0\bar{j} + 0\bar{k} = \bar{0}$$

### Step 3: Apply the calculated Curl to Stokes' Theorem template
Substitute the zero vector result of the curl calculation into the surface integration side of the theorem layout:

$$\oint_C \bar{F} \cdot d\bar{r} = \iint_S (\bar{0}) \cdot \hat{n} \, dS$$

The dot product of a zero vector and any normal unit vector $\hat{n}$ is identically zero:

$$\oint_C \bar{F} \cdot d\bar{r} = \iint_S 0 \, dS = 0$$

### Final Answer

$$\oint_C \bar{F} \cdot d\bar{r} = 0$$
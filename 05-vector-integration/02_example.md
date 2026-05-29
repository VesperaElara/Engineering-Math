# Vector Integration: Evaluating a Line Integral Along a Straight Line Path

## 1. Line Integral Parameterization

### Name of Concept
Parametric Representation of a 3D Straight Line Path for Line Integration.

### Core Mathematical Formulas

The symmetric equation of a straight line in 3D passing through points $(x_1, y_1, z_1)$ and $(x_2, y_2, z_2)$ equated to a scalar parameter $t$ is:

$$\frac{x - x_1}{x_2 - x_1} = \frac{y - y_1}{y_2 - y_1} = \frac{z - z_1}{z_2 - z_1} = t$$

The general differential line integral expansion equation is:

$$\int_C \bar{F} \cdot d\bar{r} = \int_C (f_1 \, dx + f_2 \, dy + f_3 \, dz)$$

### Beginner-Friendly Explanation of Operations



1. **The Core Strategy (Parameterization):** A line integral requires us to sum values along a path where $x$, $y$, and $z$ change simultaneously. Integrating with three different variables at once is difficult. To simplify, we express variables $x$, $y$, and $z$ in terms of a single, shared dummy variable $t$ (the parameter). Think of $t$ as a timeline tracking your progress along the path: at the start line $t=0$, and at the destination $t=1$.
2. **Converting the Path Equations:** By using the 3D line formula, we divide the distance traveled along an axis by the total directional length of that axis. Equating these fractions to $t$ allows us to extract explicit individual equations for coordinates: $x(t)$, $y(t)$, and $z(t)$.
3. **Converting the Differentials:** Because the coordinates change in terms of $t$, their microscopic steps ($dx$, $dy$, $dz$) must also be converted to terms of $dt$ using standard differentiation. For example, if $x = 2t$, then taking the derivative gives $\frac{dx}{dt} = 2$, which means $dx = 2 \, dt$. This converts our triple-variable integration problem into a straightforward single-variable calculus integral with respect to $t$.

---

## 2. Step-by-Step Problem Solution

### Question
Evaluate the line integral $\int_C \bar{F} \cdot d\bar{r}$ for the vector field $\bar{F} = 3x^2 \bar{i} + (2xz - y)\bar{j} + z\bar{k}$ along the straight line path joining the origin $(0, 0, 0)$ to the point $(2, 1, 3)$.

### Step 1: Identify components and map the endpoints
Extract the components of the vector field $\bar{F}$:

$$f_1 = 3x^2$$

$$f_2 = 2xz - y$$

$$f_3 = z$$

Assign the coordinate boundary points to the line equation variables:

$$(x_1, y_1, z_1) = (0, 0, 0)$$

$$(x_2, y_2, z_2) = (2, 1, 3)$$

### Step 2: Set up the 3D straight line parametric template
Substitute the boundary point coordinates into the standard symmetric equation:

$$\frac{x - 0}{2 - 0} = \frac{y - 0}{1 - 0} = \frac{z - 0}{3 - 0} = t$$

$$\frac{x}{2} = \frac{y}{1} = \frac{z}{3} = t$$

### Step 3: Solve for $x$, $y$, and $z$ explicitly in terms of $t$
Equate each individual fraction to the parameter $t$:

$$x = 2t$$

$$y = t$$

$$z = 3t$$

### Step 4: Determine the integration limits for the parameter $t$
Find the interval of $t$ that maps the path from start to end:
* At the starting point $(0,0,0)$: substituting $x=0$ into $0 = 2t$ yields $t = 0$.
* At the ending point $(2,1,3)$: substituting $x=2$ into $2 = 2t$ yields $t = 1$.

Thus, our integration boundaries are from $t = 0$ to $t = 1$.

### Step 5: Compute the coordinate differentials in terms of $dt$
Take the derivative of each coordinate equation with respect to $t$:

$$dx = 2 \, dt$$

$$dy = 1 \, dt$$

$$dz = 3 \, dt$$

### Step 6: Substitute the parametric equations into the vector components
Rewrite the field component expressions so they depend only on the variable $t$:

$$f_1 = 3(2t)^2 = 3(4t^2) = 12t^2$$

$$f_2 = 2(2t)(3t) - t = 12t^2 - t$$

$$f_3 = 3t$$

### Step 7: Substitute all expressions into the line integral equation
Assemble the full integral equation by substituting the component functions and differential equations:

$$\int_C \bar{F} \cdot d\bar{r} = \int_{0}^{1} \left[ (12t^2 \cdot 2 \, dt) + ((12t^2 - t) \cdot 1 \, dt) + (3t \cdot 3 \, dt) \right]$$

Factor out the common differential term $dt$ and combine the terms inside the brackets:

$$\int_C \bar{F} \cdot d\bar{r} = \int_{0}^{1} \left[ 24t^2 + 12t^2 - t + 9t \right] dt$$

Combine like algebraic terms to find the final integrated function:

$$\int_C \bar{F} \cdot d\bar{r} = \int_{0}^{1} (36t^2 + 8t) \, dt$$

### Step 8: Compute the single-variable definite integral
Apply standard calculus integration rules ($\int t^n \, dt = \frac{t^{n+1}}{n+1}$):

$$\int_C \bar{F} \cdot d\bar{r} = \left[ 36 \left(\frac{t^3}{3}\right) + 8 \left(\frac{t^2}{2}\right) \right]_{0}^{1}$$

$$\int_C \bar{F} \cdot d\bar{r} = \left[ 12t^3 + 4t^2 \right]_{0}^{1}$$

Evaluate the expression by substituting the upper limit ($1$) and lower limit ($0$):

$$\int_C \bar{F} \cdot d\bar{r} = (12(1)^3 + 4(1)^2) - (12(0)^3 + 4(0)^2)$$

$$\int_C \bar{F} \cdot d\bar{r} = 12 + 4 = 16$$
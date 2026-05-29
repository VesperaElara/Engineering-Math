# Vector Integration: Verifying Green's Theorem

## 1. Verification of Green's Theorem

### Name of Concept
Verification of Green's Theorem (Proving LHS = RHS).

### Core Mathematical Formula

$$\oint_C (P \, dx + Q \, dy) = \iint_R \left( \frac{\partial Q}{\partial x} - \frac{\partial P}{\partial y} \right) dx \, dy$$

### Beginner-Friendly Explanation of Operations

1. **What does "Verify" mean?** To *evaluate* means to compute one side of an equation. To *verify* means you must calculate **both** sides of Green's Theorem independently and show that their final numerical results match exactly.
   * **Left-Hand Side (LHS):** You calculate the line integral directly along the boundary paths. If the boundary is split into multiple distinct curves, you calculate the line integral for each section and add them together: $\int_{C} = \int_{C_1} + \int_{C_2}$.
   * **Right-Hand Side (RHS):** You calculate the double integral over the flat 2D area enclosed by those boundary paths.
2. **Finding Points of Intersection:** Before setting up any integrals, you must find where the boundary curves cross each other. Mechanically, you set the two curve equations equal to each other ($y_1 = y_2$) and solve for the intersecting $x$ and $y$ coordinates. These points act as the start and end positions for your integration paths.

---

## 2. Step-by-Step Problem Verification

### Question
Verify Green's Theorem in the plane for $\oint_C (xy + y^2)dx + x^2 dy$ where $C$ is the closed curve of the region bounded by $y = x$ and $y = x^2$.

### Step 1: Find the intersection points of the boundary curves
Equate the two given path equations to find where they cross:

$$x^2 = x$$

$$x^2 - x = 0$$

$$x(x - 1) = 0$$

This yields two horizontal coordinate roots:

$$x = 0, \quad x = 1$$

Substitute these $x$ values back into $y = x$ to find the corresponding vertical coordinates:
* For $x = 0 \implies y = 0$. The first intersection point is $(0, 0)$.
* For $x = 1 \implies y = 1$. The second intersection point is $(1, 1)$.



---

## Part A: Calculating the Right-Hand Side (RHS)

### Step 2: Extract the components and calculate partial derivatives
Identify $P$ and $Q$ from the given integrand template:

$$P = xy + y^2$$

$$Q = x^2$$

Differentiate $P$ with respect to $y$, treating $x$ as a constant:

$$\frac{\partial P}{\partial y} = x + 2y$$

Differentiate $Q$ with respect to $x$, treating $y$ as a constant:

$$\frac{\partial Q}{\partial x} = 2x$$

### Step 3: Setup the double integral function
Subtract the partial derivatives to build the inner integrand function:

$$\frac{\partial Q}{\partial x} - \frac{\partial P}{\partial y} = (2x) - (x + 2y) = x - 2y$$

### Step 4: Determine the region boundaries for double integration
* **Vertical strip limits ($y$):** Looking at the enclosed region from bottom to top, the lower boundary is the parabola $y = x^2$ and the upper boundary is the straight line $y = x$.
* **Horizontal limits ($x$):** The region spans from the leftmost intersection point $x = 0$ to the rightmost point $x = 1$.

### Step 5: Evaluate the double integral (RHS)
Set up the nested limits and integrate with respect to $y$ first:

$$\text{RHS} = \int_{0}^{1} \int_{x^2}^{x} (x - 2y) \, dy \, dx$$

$$\text{RHS} = \int_{0}^{1} \left[ xy - y^2 \right]_{x^2}^{x} dx$$

Substitute the upper limit ($y = x$) and subtract the lower limit ($y = x^2$):

$$\text{RHS} = \int_{0}^{1} \left[ \left( x(x) - (x)^2 \right) - \left( x(x^2) - (x^2)^2 \right) \right] dx$$

$$\text{RHS} = \int_{0}^{1} \left[ (x^2 - x^2) - (x^3 - x^4) \right] dx$$

$$\text{RHS} = \int_{0}^{1} (-x^3 + x^4) \, dx$$

Integrate with respect to $x$ across the absolute limits:

$$\text{RHS} = \left[ -\frac{x^4}{4} + \frac{x^5}{5} \right]_{0}^{1}$$

$$\text{RHS} = \left( -\frac{1}{4} + \frac{1}{5} \right) - 0 = -\frac{5}{20} + \frac{4}{20} = -\frac{1}{20}$$

---

## Part B: Calculating the Left-Hand Side (LHS)

The closed path $C$ is split into two separate paths:
1. $C_1$: Moving along the lower curve $y = x^2$ from $(0,0)$ to $(1,1)$.
2. $C_2$: Moving along the upper straight line $y = x$ backwards from $(1,1)$ to $(0,0)$.

### Step 6: Evaluate along Path $C_1$ ($y = x^2$)
Differentiate the path constraint to find $dy$:

$$dy = 2x \, dx$$

Substitute $y = x^2$ and $dy = 2x \, dx$ into the line integral line template, integrating from $x = 0$ to $x = 1$:

$$\int_{C_1} = \int_{0}^{1} \left[ (x(x^2) + (x^2)^2)dx + x^2(2x \, dx) \right]$$

$$\int_{C_1} = \int_{0}^{1} \left[ x^3 + x^4 + 2x^3 \right] dx$$

$$\int_{C_1} = \int_{0}^{1} \left[ 3x^3 + x^4 \right] dx$$

Integrate with respect to $x$:

$$\int_{C_1} = \left[ 3\left(\frac{x^4}{4}\right) + \frac{x^5}{5} \right]_{0}^{1} = \frac{3}{4} + \frac{1}{5} = \frac{15}{20} + \frac{4}{20} = \frac{19}{20}$$

### Step 7: Evaluate along Path $C_2$ ($y = x$)
Differentiate the path constraint to find $dy$:

$$dy = dx$$

Substitute $y = x$ and $dy = dx$ into the line integral template. Because we are traveling backward from $(1,1)$ to $(0,0)$, the limits run from $x = 1$ to $x = 0$:

$$\int_{C_2} = \int_{1}^{0} \left[ (x(x) + (x)^2)dx + x^2(dx) \right]$$

$$\int_{C_2} = \int_{1}^{0} \left[ x^2 + x^2 + x^2 \right] dx$$

$$\int_{C_2} = \int_{1}^{0} 3x^2 \, dx$$

Integrate with respect to $x$:

$$\int_{C_2} = \left[ x^3 \right]_{1}^{0} = 0^3 - 1^3 = -1$$

### Step 8: Sum the paths to find total LHS and verify

$$\text{LHS} = \int_{C_1} + \int_{C_2}$$

$$\text{LHS} = \frac{19}{20} + (-1) = \frac{19}{20} - \frac{20}{20} = -\frac{1}{20}$$

Since $\text{LHS} = -\frac{1}{20}$ and $\text{RHS} = -\frac{1}{20}$, we have proven:

$$\text{LHS} = \text{RHS}$$

Green's Theorem is verified.
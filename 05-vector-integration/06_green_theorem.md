# Vector Integration: Green's Theorem in the Plane

## 1. Green's Theorem

### Name of Concept
Green's Theorem in the Plane (Converting a Line Integral to a Double Integral).

### Core Mathematical Formula

$$\oint_C (P \, dx + Q \, dy) = \iint_R \left( \frac{\partial Q}{\partial x} - \frac{\partial P}{\partial y} \right) dx \, dy$$

### Beginner-Friendly Explanation of Operations



1. **Why Use Green's Theorem?** Evaluating a line integral along a closed path with multiple straight segments (like a triangle or rectangle) usually forces you to calculate separate line integrals for each individual side. Green's Theorem is a major shortcut: it translates a difficult multi-stage loop integral along boundary $C$ into a single double integral over the flat 2D region $R$ trapped inside that loop.
2. **Identifying $P$ and $Q$:** Look closely at your line integral. The function multiplied by $dx$ is always labeled $P$, and the function multiplied by $dy$ is always labeled $Q$.
3. **The Cross-Derivative Trick:** Inside the double integral, the order of differentiation is swapped:
   * You differentiate $Q$ (the $dy$ term) with respect to $x$.
   * You differentiate $P$ (the $dx$ term) with respect to $y$.
   * You subtract the second result from the first: $\left( \frac{\partial Q}{\partial x} - \frac{\partial P}{\partial y} \right)$.
4. **Setting Region Limits:** Once the components are subtracted, you integrate the remaining scalar function over the coordinate boundaries ($x$ limits and $y$ limits) that trace out the geometry of the trapped region $R$.

---

## 2. Step-by-Step Problem Solution

### Question
Evaluate by Green's Theorem $\oint_C (e^{-x} \sin y \, dx + e^{-x} \cos y \, dy)$ where $C$ is the rectangle whose vertices are located at $(0, 0)$, $(\pi, 0)$, $\left(\pi, \frac{\pi}{2}\right)$, and $\left(0, \frac{\pi}{2}\right)$.

### Step 1: Extract the components $P$ and $Q$
Match the problem equation to the standard template form $(P \, dx + Q \, dy)$:

$$P = e^{-x} \sin y$$

$$Q = e^{-x} \cos y$$

### Step 2: Compute the required partial derivatives
Differentiate $P$ with respect to $y$, treating $x$ as a constant:

$$\frac{\partial P}{\partial y} = e^{-x} \cos y$$

Differentiate $Q$ with respect to $x$, treating $y$ as a constant:

$$\frac{\partial Q}{\partial x} = -e^{-x} \cos y$$

### Step 3: Setup the subtraction term for the double integrand
Substitute the computed derivative terms into the Green's Theorem component template:

$$\frac{\partial Q}{\partial x} - \frac{\partial P}{\partial y} = (-e^{-x} \cos y) - (e^{-x} \cos y)$$

Combine the matching algebraic items:

$$\frac{\partial Q}{\partial x} - \frac{\partial P}{\partial y} = -2e^{-x} \cos y$$

### Step 4: Determine the integration limits from the rectangular vertices
Analyze the four corners of the rectangular boundary region $R$:
* The horizontal span runs along the x-axis from $x = 0$ to $x = \pi$.
* The vertical span runs along the y-axis from $y = 0$ to $y = \frac{\pi}{2}$.

### Step 5: Assemble the complete double integral expression
Substitute the limits and the simplified internal function into the theorem layout:

$$\oint_C (P \, dx + Q \, dy) = \int_{0}^{\pi} \int_{0}^{\frac{\pi}{2}} \left( -2e^{-x} \cos y \right) dy \, dx$$

### Step 6: Perform the inner integration with respect to $y$
Pull the terms depending purely on $x$ outside the inner integration loop. Integrate $\cos y$ to get $\sin y$:

$$\int_{0}^{\frac{\pi}{2}} -2e^{-x} \cos y \, dy = -2e^{-x} \left[ \sin y \right]_{0}^{\frac{\pi}{2}}$$

Evaluate the boundaries at $\frac{\pi}{2}$ and $0$:

$$-2e^{-x} \left( \sin\left(\frac{\pi}{2}\right) - \sin(0) \right) = -2e^{-x} (1 - 0) = -2e^{-x}$$

### Step 7: Perform the outer integration with respect to $x$
Place the result of the inner calculation into the outer integral loop:

$$\oint_C (P \, dx + Q \, dy) = \int_{0}^{\pi} -2e^{-x} \, dx$$

Apply standard exponential integration rules ($\int e^{-x} \, dx = -e^{-x}$):

$$\oint_C (P \, dx + Q \, dy) = \left[ 2e^{-x} \right]_{0}^{\pi}$$

### Step 8: Evaluate the final numeric boundaries
Substitute the upper limit ($\pi$) and subtract the lower limit ($0$):

$$\oint_C (P \, dx + Q \, dy) = 2e^{-\pi} - 2e^{0}$$

Since any base raised to the power of zero equals $1$ ($e^0 = 1$):

$$\oint_C (P \, dx + Q \, dy) = 2e^{-\pi} - 2(1)$$

Factor out the common scalar multiplier $2$:

$$\oint_C (P \, dx + Q \, dy) = 2\left(e^{-\pi} - 1\right)$$
# Vector Integration: Work Done Around a Closed Elliptical Path

## 1. Work Done and Path Parameterization for an Ellipse

### Name of Concepts
1. Work Done by a Force Field along a Closed Loop.
2. Parametric Representation of a 2D Ellipse ($z=0$).
3. Conservative Field Validation.

### Core Mathematical Formulas

The total work done by a force field $\bar{F}$ moving a particle along a path $C$ is:

$$\text{Work Done} = \oint_C \bar{F} \cdot d\bar{r} = \oint_C (f_1 \, dx + f_2 \, dy + f_3 \, dz)$$

The parametric equations for an ellipse centered at the origin with semi-major axis $a$ and semi-minor axis $b$ are:

$$x = a \cos \theta, \quad y = b \sin \theta$$

To map out the entire elliptical boundary exactly once in the counter-clockwise direction, the angular parameter $\theta$ spans the interval:

$$0 \leq \theta \leq 2\pi$$

### Beginner-Friendly Explanation of Operations



1. **Closed-Loop Line Integral ($\oint$):** The circle on the integration symbol indicates that our path forms a complete, unbroken loop starting and ending at the same location. 
2. **Ellipse Parameterization:** Just like a circle of radius $r$ uses $x = r\cos\theta$ and $y = r\sin\theta$, an ellipse stretches differently along its two axes. We replace the single radius $r$ with the independent horizontal stretch factor $a$ and vertical stretch factor $b$. This allows us to sweep along the entire curve by tracking a single angle variable $\theta$.
3. **Flat 2D Layer ($z = 0$):** Since the problem locks the path to the $z = 0$ plane, the particle never changes its vertical altitude. Therefore, the microscopic vertical step size $dz$ is exactly $0$. Any force component pushing up or down along the $\bar{k}$ axis does zero work and can be completely omitted from the calculation.
4. **Testing for Conservative Nature:** A field is conservative if its curl evaluates to zero ($\nabla \times \bar{F} = \bar{0}$). If a field *is* conservative, the total work done along *any* closed loop must equal exactly $0$ because the starting and ending points are identical. If our final work calculation yields a non-zero number, it serves as immediate proof that the field is non-conservative.

---

## 2. Step-by-Step Problem Solution

### Question
Find the work done in moving a particle once around the ellipse $\frac{x^2}{25} + \frac{y^2}{16} = 1$, $z = 0$ under the field of force given by $\bar{F} = (2x - y + z) \bar{i} + (x + y - z^2)\bar{j} + (3x - 2y + 4z)\bar{k}$. Is the field conservative?

### Step 1: Extract the geometric values of the ellipse
Match the given ellipse equation to the standard form $\frac{x^2}{a^2} + \frac{y^2}{b^2} = 1$:

$$a^2 = 25 \implies a = 5$$

$$b^2 = 16 \implies b = 4$$

### Step 2: Establish the parametric coordinate equations
Substitute the values of $a$ and $b$ into the trigonometric parametric layout. Account for the path constraint $z=0$:

$$x = 5 \cos \theta$$

$$y = 4 \sin \theta$$

$$z = 0$$

### Step 3: Compute the differentials in terms of $d\theta$
Differentiate each coordinate function with respect to $\theta$:

$$\frac{dx}{d\theta} = -5 \sin \theta \implies dx = -5 \sin \theta \, d\theta$$

$$\frac{dy}{d\theta} = 4 \cos \theta \implies dy = 4 \cos \theta \, d\theta$$

$$\frac{dz}{d\theta} = 0 \implies dz = 0$$

### Step 4: Simplify the field components using the $z=0$ constraint
Extract the scalar components of $\bar{F}$ and substitute $z = 0$ to simplify them before integration:

$$f_1 = 2x - y + z = 2x - y + 0 = 2x - y$$

$$f_2 = x + y - z^2 = x + y - 0^2 = x + y$$

$$f_3 = 3x - 2y + 4z = 3x - 2y + 0 = 3x - 2y$$

### Step 5: Substitute coordinates into the active components
Express $f_1$ and $f_2$ purely as functions of our angle variable $\theta$:

$$f_1 = 2(5 \cos \theta) - (4 \sin \theta) = 10 \cos \theta - 4 \sin \theta$$

$$f_2 = (5 \cos \theta) + (4 \sin \theta) = 5 \cos \theta + 4 \sin \theta$$

### Step 6: Set up the scalar work integral equation
Substitute our simplified functions and differentials into the line integral equation, setting the boundary limits from $\theta = 0$ to $2\pi$:

$$\text{Work Done} = \int_{0}^{2\pi} \left[ (f_1)dx + (f_2)dy + (f_3)dz \right]$$

Since $dz = 0$, the third component drops out completely:

$$\text{Work Done} = \int_{0}^{2\pi} \left[ (10 \cos \theta - 4 \sin \theta)(-5 \sin \theta \, d\theta) + (5 \cos \theta + 4 \sin \theta)(4 \cos \theta \, d\theta) \right]$$

### Step 7: Distribute and expand terms inside the integrand
Factor out the common differential operator $d\theta$ and multiply the terms across the parentheses:

$$\text{Work Done} = \int_{0}^{2\pi} \left[ -50 \sin \theta \cos \theta + 20 \sin^2 \theta + 20 \cos^2 \theta + 16 \sin \theta \cos \theta \right] d\theta$$

Combine the matching trigonometric terms:

$$-50 \sin \theta \cos \theta + 16 \sin \theta \cos \theta = -34 \sin \theta \cos \theta$$

Factor out the common coefficient from the squared terms:

$$20 \sin^2 \theta + 20 \cos^2 \theta = 20(\sin^2 \theta + \cos^2 \theta)$$

Apply the fundamental trigonometric identity $\sin^2 \theta + \cos^2 \theta = 1$:

$$20(1) = 20$$

Assemble the simplified expression:

$$\text{Work Done} = \int_{0}^{2\pi} \left[ 20 - 34 \sin \theta \cos \theta \right] d\theta$$

### Step 8: Apply trigonometric identities to ease integration
Use the double-angle identity $2 \sin \theta \cos \theta = \sin(2\theta)$ to simplify the second term:

$$34 \sin \theta \cos \theta = 17(2 \sin \theta \cos \theta) = 17 \sin(2\theta)$$

Substitute this back into the definite integral:

$$\text{Work Done} = \int_{0}^{2\pi} \left[ 20 - 17 \sin(2\theta) \right] d\theta$$

### Step 9: Integrate and evaluate across boundaries
Apply standard calculus integration rules ($\int \sin(2\theta) \, d\theta = \frac{-\cos(2\theta)}{2}$):

$$\text{Work Done} = \left[ 20\theta - 17 \left( \frac{-\cos(2\theta)}{2} \right) \right]_{0}^{2\pi}$$

$$\text{Work Done} = \left[ 20\theta + \frac{17}{2} \cos(2\theta) \right]_{0}^{2\pi}$$

Evaluate the expression by substituting the upper limit ($2\pi$) and subtracting the lower limit ($0$):

$$\text{Work Done} = \left( 20(2\pi) + \frac{17}{2} \cos(4\pi) \right) - \left( 20(0) + \frac{17}{2} \cos(0) \right)$$

Since $\cos(4\pi) = 1$ and $\cos(0) = 1$:

$$\text{Work Done} = \left( 40\pi + \frac{17}{2}(1) \right) - \left( 0 + \frac{17}{2}(1) \right)$$

$$\text{Work Done} = 40\pi + \frac{17}{2} - \frac{17}{2} = 40\pi$$

### Step 10: Determine field conservative status
A force field is conservative if and only if the total work executed along a closed loop path equals exactly zero. 

Because the calculated work done is $40\pi \neq 0$, the vector field $\bar{F}$ is **not conservative**.
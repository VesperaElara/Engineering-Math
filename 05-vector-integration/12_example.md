# Vector Integration: Evaluating a Surface Integral Using Stokes' Theorem

## 1. Inverse Stokes' Theorem Application

### Name of Concept
Using Stokes' Theorem in Reverse (Converting a Surface Integral to a Line Integral).

### Core Mathematical Formula

$$\iint_S (\nabla \times \bar{F}) \cdot d\bar{S} = \oint_C \bar{F} \cdot d\bar{r} = \oint_C (f_1 \, dx + f_2 \, dy + f_3 \, dz)$$

### Beginner-Friendly Explanation of Operations



1. **Why Reverse the Theorem?** The problem asks us to evaluate a double surface integral containing the curl of a vector field ($\iint_S (\nabla \times \bar{F}) \cdot d\bar{S}$). Computing the curl, finding the unit normal vector $\hat{n}$ for an asymmetrical ellipsoid capsule skin, and setting up 2D surface projection limits would be incredibly tedious. 
2. **The Boundary Ring Strategy:** Stokes' Theorem works both ways. Instead of calculating the churning field across the entire open 3D bubble skin ($S$), we can look *only* at the solid perimeter rim ($C$) that acts as the opening of that bubble. The net flux of the curl through the surface matches the line integral of the raw vector field directly along its boundary curve.
3. **Finding the Rim Equation ($C$):** The problem states that the surface $S$ is cut off "above the plane $x = 0$". The boundary rim is the flat, 2D intersection line where the curved ellipsoid shell meets the slicing wall $x = 0$. By substituting $x = 0$ directly into the 3D surface equation, we lock the coordinates to that wall and reveal the exact 2D shape of the bounding loop path.
4. **Simplifying the Differential Path:** Because the boundary rim lies entirely flat against the $x = 0$ plane, the coordinate $x$ is constant at every single millimeter along the loop. Therefore, the microscopic step size along the x-axis ($dx$) is exactly $0$. This eliminates the entire first component of our line integral before we even begin integrating.

---

## 2. Step-by-Step Problem Solution

### Question
Evaluate $\iint_S (\nabla \times \bar{F}) \cdot d\bar{S}$, where $\bar{F} = (x^3 - y^3)\bar{i} - xyz\bar{j} + y^3\bar{k}$ and $S$ is the surface $x^2 + 4y^2 + z^2 - 2x = 4$ above the plane $x = 0$.

### Step 2: Identify the boundary path curve $C$
The boundary curve $C$ is the intersection rim of the ellipsoid surface and the plane $x = 0$. Set $x = 0$ in the surface equation:

$$(0)^2 + 4y^2 + z^2 - 2(0) = 4$$

$$4y^2 + z^2 = 4$$

Convert this to standard ellipse format by dividing all terms by $4$:

$$\frac{4y^2}{4} + \frac{z^2}{4} = \frac{4}{4} \implies \frac{y^2}{1} + \frac{z^2}{4} = 1$$

The boundary curve $C$ is a flat ellipse lying entirely inside the $yz$-plane ($x=0$).

### Step 3: Establish the coordinate values and differentials along curve $C$
Since the path is pinned to the $x = 0$ plane, apply these strict numeric constraints:

$$x = 0$$

$$dx = 0$$

### Step 4: Simplify the line integral using path constraints
Write down the raw line integral component template:

$$\oint_C \bar{F} \cdot d\bar{r} = \oint_C (x^3 - y^3)dx + (-xyz)dy + y^3dz$$

Substitute $x = 0$ and $dx = 0$ into the expression:

$$\oint_C \bar{F} \cdot d\bar{r} = \oint_C (0^3 - y^3)(0) + (-(0)yz)dy + y^3dz$$

Notice that both the $dx$ term and the $dy$ term evaluate to zero:

$$\oint_C \bar{F} \cdot d\bar{r} = \oint_C y^3dz$$

### Step 5: Parameterize the 2D ellipse path in the $yz$-plane
Map the ellipse $y^2 + \frac{z^2}{4} = 1$ using standard trigonometric tracking parameters. Here, the horizontal axis variable is $y$ ($a=1$) and the vertical axis variable is $z$ ($b=2$):

$$y = 1 \cos \theta = \cos \theta$$

$$z = 2 \sin \theta$$

Differentiate the equation for $z$ with respect to $\theta$ to calculate the active differential $dz$:

$$\frac{dz}{d\theta} = 2 \cos \theta \implies dz = 2 \cos \theta \, d\theta$$

To trace out the entire closed elliptical rim exactly once, set the angular boundaries:

$$\theta = 0 \text{ to } 2\pi$$

### Step 6: Substitute the parametric functions into the line integral
Rewrite the remaining line integral expression purely in terms of the angle parameter $\theta$:

$$\oint_C y^3dz = \int_{0}^{2\pi} (\cos \theta)^3 \cdot (2 \cos \theta \, d\theta)$$

$$\oint_C y^3dz = \int_{0}^{2\pi} 2 \cos^4 \theta \, d\theta$$

Pull the constant scalar factor outside the integral limits:

$$\oint_C y^3dz = 2 \int_{0}^{2\pi} \cos^4 \theta \, d\theta$$

### Step 7: Apply quadrant symmetry and Wallis' formula shortcuts
Because $\cos^4 \theta$ contains an even exponent power, exploit the four-quadrant area symmetry trick over a full rotation cycle:

$$\int_{0}^{2\pi} \cos^4 \theta \, d\theta = 4 \int_{0}^{\pi/2} \cos^4 \theta \, d\theta$$

Substitute this symmetry transformation back into our main problem expression:

$$\oint_C y^3dz = 2 \cdot \left( 4 \int_{0}^{\pi/2} \cos^4 \theta \, d\theta \right) = 8 \int_{0}^{\pi/2} \cos^4 \theta \, d\theta$$

Apply Wallis' reduction formula shortcut pattern for an even power ($n=4$) across the first quadrant interval $\left[0, \frac{\pi}{2}\right]$:

$$\int_{0}^{\pi/2} \cos^4 \theta \, d\theta = \left[ \frac{(4-1) \cdot (4-3)}{4 \cdot (4-2)} \right] \times \frac{\pi}{2}$$

$$\int_{0}^{\pi/2} \cos^4 \theta \, d\theta = \left[ \frac{3 \cdot 1}{4 \cdot 2} \right] \times \frac{\pi}{2} = \frac{3}{8} \times \frac{\pi}{2} = \frac{3\pi}{16}$$

### Step 8: Calculate the final numeric value
Multiply the single-quadrant area value by our accumulated constant scalar multiplier:

$$\oint_C \bar{F} \cdot d\bar{r} = 8 \times \left( \frac{3\pi}{16} \right)$$

Simplify the fraction coefficients to find the final result:

$$\oint_C \bar{F} \cdot d\bar{r} = \frac{24\pi}{16} = \frac{3\pi}{2}$$

### Final Answer

$$\iint_S (\nabla \times \bar{F}) \cdot d\bar{S} = \frac{3\pi}{2}$$
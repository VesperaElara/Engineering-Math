# Vector Integration: Trigonometric Parameterization and Wallis' Formula Shortcuts

## 1. Geometric Parameterization and Walli's Reduction Formulas

### Name of Concepts
1. Parametric Coordinate Transformations (Circle vs. Ellipse).
2. Symmetric Definite Integral Multipliers over a Full Period ($2\pi$).
3. Wallis' Reduction Formulas for Even Powers of Sines and Cosines.

### Core Mathematical Formulas

For a circle centered at the origin with radius $a$:

$$x^2 + y^2 = a^2 \implies x = a \cos\theta, \quad y = a \sin\theta$$

For an ellipse centered at the origin with semi-major axis $a$ and semi-minor axis $b$:

$$\frac{x^2}{a^2} + \frac{y^2}{b^2} = 1 \implies x = a \cos\theta, \quad y = b \sin\theta$$

The symmetry transformation rule for an even, periodic function integrated over a full circle loop is:

$$\int_{0}^{2\pi} \sin^n\theta \, d\theta = 4\int_{0}^{\pi/2} \sin^n\theta \, d\theta \quad \text{(where } n \text{ is an even integer)}$$

Wallis' shortcut template for evaluating even powers integrated across the first quadrant boundary $\left[0, \frac{\pi}{2}\right]$ is:

$$\int_{0}^{\pi/2} \cos^n\theta \, d\theta = \frac{(n-1) \cdot (n-3) \dots 1}{n \cdot (n-2) \dots 2} \times \frac{\pi}{2}$$

### Beginner-Friendly Explanation of Operations



1. **Parameterization Refresher:** When evaluating boundary paths for Green's, Stokes', or standard line integrals, we convert Cartesian coordinates ($x, y$) into matching angular coordinates ($\theta$) using standard geometric forms. Circles scale evenly using a single constant radius ($a$), while ellipses use two distinct axial stretch values ($a$ and $b$). Tracing a complete closed loop always means running the angle parameter from $\theta = 0$ directly to $\theta = 2\pi$.
2. **Exploiting Quadrant Symmetry (The "Factor of 4" Trick):** If you sketch out the curves for $\sin^2\theta$, $\cos^2\theta$, or any even power like $\cos^4\theta$, you will notice that the area bounded underneath the wave shape repeats identically in each of the four quadrants. Instead of integrating across the entire clumsy range from $0$ to $2\pi$, we can evaluate the area of just the very first clean quadrant from $0$ to $\frac{\pi}{2}$, and then multiply the result by $4$.
3. **Wallis' Formula Shortcut:** Integrating expressions like $\cos^4\theta$ by hand requires using long, messy double-angle expansion rules over and over. Wallis' reduction formula bypasses this algebra entirely with a simple fraction pattern:
   * **Numerator:** Start with your exponent minus one ($n-1$), then count down by subtracting two each time until you hit $1$.
   * **Denominator:** Start with the raw exponent ($n$), then count down by subtracting two each time until you hit $2$.
   * **The Scaling Factor:** If your original exponent is even, multiply the entire fraction chain by $\frac{\pi}{2}$ at the end.

---

## 2. Step-by-Step Evaluation of Definite Integrals

### Example A: Integrating $\sin^2\theta$ over a full loop

#### Step 1: Apply the quadrant symmetry rule
Convert the full boundary sweep into an isolated first-quadrant integration multiplied by $4$:

$$\int_{0}^{2\pi} \sin^2\theta \, d\theta = 4\int_{0}^{\pi/2} \sin^2\theta \, d\theta$$

#### Step 2: Set up Wallis' formula parameters
Identify the power value: $n = 2$.
* The numerator product sequence stops at: $n - 1 = 2 - 1 = 1$.
* The denominator product sequence stops at: $n = 2$.

#### Step 3: Compute the fractional products

$$\int_{0}^{\pi/2} \sin^2\theta \, d\theta = \frac{1}{2} \times \frac{\pi}{2}$$

#### Step 4: Scale by the symmetry multiplier to find the final result
Multiply the calculated single quadrant value by our 4-quadrant factor:

$$\int_{0}^{2\pi} \sin^2\theta \, d\theta = 4 \times \left[ \frac{1}{2} \times \frac{\pi}{2} \right]$$

$$\int_{0}^{2\pi} \sin^2\theta \, d\theta = 4 \times \left[ \frac{\pi}{4} \right] = \pi$$

---

### Example B: Integrating $\cos^4\theta$ over a full loop

#### Step 1: Apply the quadrant symmetry rule
Convert the full loop range into a single quadrant calculation scaled by $4$:

$$\int_{0}^{2\pi} \cos^4\theta \, d\theta = 4\int_{0}^{\pi/2} \cos^4\theta \, d\theta$$

#### Step 2: Set up Wallis' formula parameters
Identify the power value: $n = 4$.
* Build the numerator by starting at $(4-1)=3$ and subtracting two: $3 \cdot 1$.
* Build the denominator by starting at $4$ and subtracting two: $4 \cdot 2$.

#### Step 3: Compute the fractional products
Combine the descending chains and multiply by the even power scaling constant $\frac{\pi}{2}$:

$$\int_{0}^{\pi/2} \cos^4\theta \, d\theta = \left[ \frac{3 \cdot 1}{4 \cdot 2} \right] \times \frac{\pi}{2} = \frac{3}{8} \times \frac{\pi}{2} = \frac{3\pi}{16}$$

#### Step 4: Scale by the symmetry multiplier to find the final result
Multiply the calculated single quadrant value by our 4-quadrant factor:

$$\int_{0}^{2\pi} \cos^4\theta \, d\theta = 4 \times \left[ \frac{3}{4} \cdot \frac{1}{2} \cdot \frac{\pi}{2} \right]$$

$$\int_{0}^{2\pi} \cos^4\theta \, d\theta = 4 \times \left[ \frac{3\pi}{16} \right]$$

Simplify the fraction coefficients to finish the evaluation:

$$\int_{0}^{2\pi} \cos^4\theta \, d\theta = \frac{3\pi}{4}$$
## Question 3 (Composite Functions & Inverse Trigonometry)

### Problem Statement
If $u = \sin^{-1} \left[ \frac{x^{1/4} + y^{1/4}}{x^{1/5} + y^{1/5}} \right]$, prove that:
$$x \frac{\partial u}{\partial x} + y \frac{\partial u}{\partial y} = \frac{1}{20} \tan u$$

---

### Step-by-Step Solution

#### Step 1: Transform the Function to Remove the Outer Non-Homogeneous Wrapper
Because of the outer inverse sine function, $u$ itself is not homogeneous. To eliminate this wrapper, take the sine of both sides to create a new, purely algebraic substitute function, $z$:

$$z = \sin u = \frac{x^{1/4} + y^{1/4}}{x^{1/5} + y^{1/5}}$$

---

#### Step 2: Determine the Degree ($n$) of the Substitute Function $z$
Define the function explicitly:
$$f(x, y) = \frac{x^{1/4} + y^{1/4}}{x^{1/5} + y^{1/5}}$$

Substitute $x \to xt$ and $y \to yt$ into the equation:
$$f(xt, yt) = \frac{(xt)^{1/4} + (yt)^{1/4}}{(xt)^{1/5} + (yt)^{1/5}}$$

Distribute the exponential fractional powers:
$$f(xt, yt) = \frac{x^{1/4} \cdot t^{1/4} + y^{1/4} \cdot t^{1/4}}{x^{1/5} \cdot t^{1/5} + y^{1/5} \cdot t^{1/5}}$$

Factor out $t^{1/4}$ from the numerator and $t^{1/5}$ from the denominator:
$$f(xt, yt) = \frac{t^{1/4} \left( x^{1/4} + y^{1/4} \right)}{t^{1/5} \left( x^{1/5} + y^{1/5} \right)}$$

Simplify the powers of $t$ using the subtraction rule for exponents ($\frac{a^m}{a^n} = a^{m-n}$):
$$n = \frac{1}{4} - \frac{1}{5} = \frac{5 - 4}{20} = \frac{1}{20}$$

$$f(xt, yt) = t^{1/20} \left( \frac{x^{1/4} + y^{1/4}}{x^{1/5} + y^{1/5}} \right) = t^{1/20} z$$

This confirms that the substitute function $z$ is a homogeneous function with a degree of $n = \frac{1}{20}$.

---

#### Step 3: Apply Euler's Theorem to $z$
By Euler's Theorem, applying the differential operators to our homogeneous function $z$ gives:
$$x \frac{\partial z}{\partial x} + y \frac{\partial z}{\partial y} = n z$$

Substitute the calculated degree $n = \frac{1}{20}$:
$$x \frac{\partial z}{\partial x} + y \frac{\partial z}{\partial y} = \frac{1}{20} z \quad \text{--- (Equation 1)}$$

---

#### Step 4: Convert Partial Derivatives of $z$ Back to $u$ via Chain Rule
Since $z = \sin u$, and $u$ depends on both $x$ and $y$, calculate the partial derivatives of $z$ using the chain rule:

$$\frac{\partial z}{\partial x} = \frac{d z}{d u} \cdot \frac{\partial u}{\partial x} = \cos u \cdot \frac{\partial u}{\partial x}$$

$$\frac{\partial z}{\partial y} = \frac{d z}{d u} \cdot \frac{\partial u}{\partial y} = \cos u \cdot \frac{\partial u}{\partial y}$$

Substitute these chain-rule expressions directly back into the left-hand side of Equation 1:
$$x \left( \cos u \cdot \frac{\partial u}{\partial x} \right) + y \left( \cos u \cdot \frac{\partial u}{\partial y} \right) = \frac{1}{20} z$$

Factor out the common term $\cos u$:
$$\cos u \cdot \left( x \frac{\partial u}{\partial x} + y \frac{\partial u}{\partial y} \right) = \frac{1}{20} z$$

Substitute our original definition of $z$ ($z = \sin u$) into the right-hand side:
$$\cos u \cdot \left( x \frac{\partial u}{\partial x} + y \frac{\partial u}{\partial y} \right) = \frac{1}{20} \sin u$$

Divide both sides by $\cos u$ to isolate our target expression:
$$x \frac{\partial u}{\partial x} + y \frac{\partial u}{\partial y} = \frac{1}{20} \left( \frac{\sin u}{\cos u} \right)$$

Using the trigonometric identity $\frac{\sin u}{\cos u} = \tan u$:
$$x \frac{\partial u}{\partial x} + y \frac{\partial u}{\partial y} = \frac{1}{20} \tan u = \text{RHS}$$

Hence, proved.
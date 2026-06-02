## Question 1 (Second-Order Corollary)

### Problem Statement
If $u = \frac{x^3y + y^3x}{y - x}$, prove that:
$$x^2 \frac{\partial^2 u}{\partial x^2} + 2xy \frac{\partial^2 u}{\partial x \partial y} + y^2 \frac{\partial^2 u}{\partial y^2} = 6 \left( \frac{x^3y + y^3x}{y - x} \right)$$

---

### Step-by-Step Solution

#### Step 1: Verify Homogeneity and Find the Degree ($n$)
Define the function explicitly:
$$f(x, y) = \frac{x^3y + y^3x}{y - x}$$

Substitute $x \to xt$ and $y \to yt$ into the function:
$$f(xt, yt) = \frac{(xt)^3(yt) + (yt)^3(xt)}{(yt) - (xt)}$$

Expand the power terms in both components of the numerator:
$$f(xt, yt) = \frac{(x^3t^3 \cdot yt) + (y^3t^3 \cdot xt)}{yt - xt}$$

$$f(xt, yt) = \frac{x^3y \cdot t^4 + y^3x \cdot t^4}{yt - xt}$$

Factor out $t^4$ from the numerator and $t^1$ from the denominator:
$$f(xt, yt) = \frac{t^4(x^3y + y^3x)}{t^1(y - x)}$$

Simplify the powers of $t$ using the exponent quotient rule $\frac{t^4}{t^1} = t^{4-1} = t^3$:
$$f(xt, yt) = t^3 \left( \frac{x^3y + y^3x}{y - x} \right)$$

Substitute the original definition of $u$ back into the equation:
$$f(xt, yt) = t^3 u$$

This confirms that $u$ is a homogeneous function with a degree of $n = 3$.

---

#### Step 2: Apply the Second-Order Extension of Euler's Theorem
The second-order corollary formula for a homogeneous function of degree $n$ states:
$$x^2 \frac{\partial^2 u}{\partial x^2} + 2xy \frac{\partial^2 u}{\partial x \partial y} + y^2 \frac{\partial^2 u}{\partial y^2} = n(n - 1)u$$

Substitute the value $n = 3$ directly into the formula:
$$\text{RHS} = 3(3 - 1)u$$

$$\text{RHS} = 3(2)u = 6u$$

Substitute the original algebraic definition of $u$ back into the right-hand expression:
$$\text{RHS} = 6 \left( \frac{x^3y + y^3x}{y - x} \right)$$

Equating the left-hand side operator to our calculated right-hand side gives:
$$x^2 \frac{\partial^2 u}{\partial x^2} + 2xy \frac{\partial^2 u}{\partial x \partial y} + y^2 \frac{\partial^2 u}{\partial y^2} = 6 \left( \frac{x^3y + y^3x}{y - x} \right) = \text{RHS}$$

Hence, proved.
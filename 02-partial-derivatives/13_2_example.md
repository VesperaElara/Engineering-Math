# Engineering Mathematics Study Notes: Advanced Application of Modified Euler's Theorem

This note breaks down the step-by-step solution for a complex second-order differential operator involving a radical and an inverse cosecant wrapper function. We will utilize **Modified Euler's Theorem** to resolve the expression cleanly without resorting to direct partial differentiation.

---

## Problem Statement

If $u = \csc^{-1} \sqrt{\frac{x^{1/2} + y^{1/2}}{x^{1/3} + y^{1/3}}}$, prove that:
$$x^2 \frac{\partial^2 u}{\partial x^2} + 2xy \frac{\partial^2 u}{\partial x \partial y} + y^2 \frac{\partial^2 u}{\partial y^2} = \frac{\tan u}{144} (13 + \tan^2 u)$$

---

## Complete Step-by-Step Derivation

### Step 1: Transform the Function to Remove the Non-Linear Wrapper
The function $u$ is not homogeneous in its raw form due to the outer inverse cosecant function and the square root. We eliminate these step-by-step by taking the cosecant of both sides and squaring the result to isolate a core algebraic function $z$:
$$\csc u = \sqrt{\frac{x^{1/2} + y^{1/2}}{x^{1/3} + y^{1/3}}}$$

$$\csc^2 u = \frac{x^{1/2} + y^{1/2}}{x^{1/3} + y^{1/3}}$$

Let our new homogeneous substitute function be $z$:
$$z = \csc^2 u = \frac{x^{1/2} + y^{1/2}}{x^{1/3} + y^{1/3}}$$

---

### Step 2: Determine the Degree of Homogeneity ($n$)
Let the pure algebraic fraction be represented as $f(x, y)$:
$$f(x, y) = \frac{x^{1/2} + y^{1/2}}{x^{1/3} + y^{1/3}}$$

To determine the degree of homogeneity, substitute $x \to xt$ and $y \to yt$:
$$f(xt, yt) = \frac{(xt)^{1/2} + (yt)^{1/2}}{(xt)^{1/3} + (yt)^{1/3}}$$

Factor out the scaling parameter $t$ from both the numerator and the denominator:
$$f(xt, yt) = \frac{t^{1/2}(x^{1/2} + y^{1/2})}{t^{1/3}(x^{1/3} + y^{1/3})}$$

Simplify the exponents of $t$ using the laws of indices:
$$f(xt, yt) = t^{\left(\frac{1}{2} - \frac{1}{3}\right)} \left[ \frac{x^{1/2} + y^{1/2}}{x^{1/3} + y^{1/3}} \right]$$

Calculate the common denominator for the exponent:
$$\frac{1}{2} - \frac{1}{3} = \frac{3 - 2}{6} = \frac{1}{6}$$

$$f(xt, yt) = t^{1/6} f(x, y)$$

Since $t$ factors out with a power of $1/6$, the substitute function $z$ is a homogeneous function with a degree of $n = \frac{1}{6}$.

---

### Step 3: Compute the First-Order Value Expression $g(u)$
According to the Modified Euler's Theorem, if a function is transformed via $z = f(u)$, the first-order partial differential expression simplifies to a single-variable function $g(u)$:
$$x \frac{\partial u}{\partial x} + y \frac{\partial u}{\partial y} = n \cdot \frac{f(u)}{f'(u)} = g(u)$$

From our setup:
$$f(u) = \csc^2 u$$

Differentiate $f(u)$ with respect to $u$ using the chain rule:
$$f'(u) = 2\csc u \cdot (-\csc u \cot u) = -2\csc^2 u \cot u$$

Substitute $n = \frac{1}{6}$, $f(u)$, and $f'(u)$ into the formula to evaluate $g(u)$:
$$g(u) = \frac{1}{6} \cdot \frac{\csc^2 u}{-2\csc^2 u \cot u}$$

Cancel out the common $\csc^2 u$ term from the numerator and denominator:
$$g(u) = \frac{1}{6} \cdot \frac{1}{-2\cot u}$$

$$g(u) = -\frac{1}{12\cot u}$$

Using the trigonometric identity $\frac{1}{\cot u} = \tan u$:
$$g(u) = -\frac{1}{12} \tan u$$

---

### Step 4: Apply the Second-Order Modified Euler's Corollary
The second-order differential operator for a modified homogeneous function is determined by the following expansion identity:
$$x^2 \frac{\partial^2 u}{\partial x^2} + 2xy \frac{\partial^2 u}{\partial x \partial y} + y^2 \frac{\partial^2 u}{\partial y^2} = g(u) \cdot \left[ g'(u) - 1 \right]$$

Find the derivative of $g(u)$ with respect to $u$:
$$g'(u) = \frac{d}{du}\left(-\frac{1}{12} \tan u\right) = -\frac{1}{12} \sec^2 u$$

Substitute the expressions for $g(u)$ and $g'(u)$ into the right-hand side (RHS) of the second-order corollary:
$$\text{RHS} = \left(-\frac{1}{12} \tan u\right) \cdot \left[ -\frac{1}{12} \sec^2 u - 1 \right]$$

---

### Step 5: Expand and Simplify to Match the Target Identity
Factor out the negative sign from the expression inside the brackets to cancel the leading negative sign:
$$\text{RHS} = \left(-\frac{1}{12} \tan u\right) \cdot (-1) \cdot \left[ \frac{1}{12} \sec^2 u + 1 \right]$$

$$\text{RHS} = \frac{1}{12} \tan u \cdot \left[ \frac{\sec^2 u + 12}{12} \right]$$

Multiply the denominators together outside the bracket:
$$\text{RHS} = \frac{\tan u}{144} \cdot \left[ \sec^2 u + 12 \right]$$

To match the target equation format, convert $\sec^2 u$ to its tangent equivalent using the standard Pythagorean identity $\sec^2 u = 1 + \tan^2 u$:
$$\text{RHS} = \frac{\tan u}{144} \cdot \left[ (1 + \tan^2 u) + 12 \right]$$

Combine the constant numerical values inside the bracket:
$$\text{RHS} = \frac{\tan u}{144} \cdot \left[ 13 + \tan^2 u \right]$$

Equating this fully simplified right-hand side back to the second-order differential operator completes the verification:
$$x^2 \frac{\partial^2 u}{\partial x^2} + 2xy \frac{\partial^2 u}{\partial x \partial y} + y^2 \frac{\partial^2 u}{\partial y^2} = \frac{\tan u}{144} (13 + \tan^2 u)$$

Hence, proved.
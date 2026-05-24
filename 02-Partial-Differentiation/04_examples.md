# Engineering Mathematics: Higher-Order Partial Differentiation

## Problem 1 (Mixed Second-Order)

### Statement
If $u = \log(x^2 + y^2)$, prove that:

$$\frac{\partial^2 u}{\partial x \partial y} = \frac{\partial^2 u}{\partial y \partial x}$$

### Step-by-Step Derivation

#### Part 1: Evaluating the Left-Hand Side (LHS)
To compute $\frac{\partial^2 u}{\partial x \partial y}$, follow the right-to-left order of operations: first differentiate $u$ with respect to $y$, then differentiate that result with respect to $x$.

Find the first partial derivative $\frac{\partial u}{\partial y}$ using the log chain rule, treating $x$ as a constant:

$$\frac{\partial u}{\partial y} = \frac{1}{x^2 + y^2} \cdot \frac{\partial}{\partial y}(x^2 + y^2)$$

$$\frac{\partial u}{\partial y} = \frac{2y}{x^2 + y^2}$$

Now, differentiate this result with respect to $x$ by applying the quotient rule, keeping $y$ constant:

$$\frac{\partial^2 u}{\partial x \partial y} = \frac{\partial}{\partial x}\left( \frac{2y}{x^2 + y^2} \right)$$

$$\frac{\partial^2 u}{\partial x \partial y} = \frac{\left[\frac{\partial}{\partial x}(2y)\right] \cdot (x^2 + y^2) - (2y) \cdot \left[\frac{\partial}{\partial x}(x^2 + y^2)\right]}{(x^2 + y^2)^2}$$

$$\frac{\partial^2 u}{\partial x \partial y} = \frac{0 \cdot (x^2 + y^2) - (2y) \cdot (2x)}{(x^2 + y^2)^2}$$

$$\text{LHS} = \frac{\partial^2 u}{\partial x \partial y} = \frac{-4xy}{(x^2 + y^2)^2}$$

#### Part 2: Evaluating the Right-Hand Side (RHS)
To compute $\frac{\partial^2 u}{\partial y \partial x}$, reverse the order: first differentiate $u$ with respect to $x$, then differentiate that result with respect to $y$.

Find the first partial derivative $\frac{\partial u}{\partial x}$ using the log chain rule, treating $y$ as a constant:

$$\frac{\partial u}{\partial x} = \frac{1}{x^2 + y^2} \cdot \frac{\partial}{\partial x}(x^2 + y^2)$$

$$\frac{\partial u}{\partial x} = \frac{2x}{x^2 + y^2}$$

Now, differentiate this result with respect to $y$ using the quotient rule, keeping $x$ constant:

$$\frac{\partial^2 u}{\partial y \partial x} = \frac{\partial}{\partial y}\left( \frac{2x}{x^2 + y^2} \right)$$

$$\frac{\partial^2 u}{\partial y \partial x} = \frac{\left[\frac{\partial}{\partial y}(2x)\right] \cdot (x^2 + y^2) - (2x) \cdot \left[\frac{\partial}{\partial y}(x^2 + y^2)\right]}{(x^2 + y^2)^2}$$

$$\frac{\partial^2 u}{\partial y \partial x} = \frac{0 \cdot (x^2 + y^2) - (2x) \cdot (2y)}{(x^2 + y^2)^2}$$

$$\text{RHS} = \frac{\partial^2 u}{\partial y \partial x} = \frac{-4xy}{(x^2 + y^2)^2}$$

Comparing both final expressions confirms the property:

$$\text{LHS} = \text{RHS}$$

This completes the proof.

---

## Problem 2 (Third-Order Partial Derivative)

### Statement
If $u = e^{x^2 + y^2 + z^2}$, prove that:

$$\frac{\partial^3 u}{\partial x \partial y \partial z} = 8xyzu$$

### Step-by-Step Derivation

When evaluating a multi-variable third-order partial derivative like $\frac{\partial^3 u}{\partial x \partial y \partial z}$, work sequentially from right to left:
1. Differentiate with respect to $z$ first.
2. Differentiate that result with respect to $y$.
3. Differentiate that final result with respect to $x$.

#### Step 1: Differentiate with respect to $z$
Apply the exponential chain rule, treating $x$ and $y$ as constants:

$$\frac{\partial u}{\partial z} = e^{x^2 + y^2 + z^2} \cdot \frac{\partial}{\partial z}(x^2 + y^2 + z^2)$$

$$\frac{\partial u}{\partial z} = e^{x^2 + y^2 + z^2} \cdot (2z)$$

$$\frac{\partial u}{\partial z} = 2z e^{x^2 + y^2 + z^2}$$

#### Step 2: Differentiate the result with respect to $y$
Differentiate $2z e^{x^2 + y^2 + z^2}$ with respect to $y$. Since $2z$ acts as a constant multiplier here, apply the exponential chain rule directly to the exponential term:

$$\frac{\partial^2 u}{\partial y \partial z} = \frac{\partial}{\partial y}\left( 2z e^{x^2 + y^2 + z^2} \right)$$

$$\frac{\partial^2 u}{\partial y \partial z} = 2z \cdot \left[ e^{x^2 + y^2 + z^2} \cdot \frac{\partial}{\partial y}(x^2 + y^2 + z^2) \right]$$

$$\frac{\partial^2 u}{\partial y \partial z} = 2z \cdot \left[ e^{x^2 + y^2 + z^2} \cdot (2y) \right]$$

$$\frac{\partial^2 u}{\partial y \partial z} = 4yz e^{x^2 + y^2 + z^2}$$

#### Step 3: Differentiate the result with respect to $x$
Differentiate $4yz e^{x^2 + y^2 + z^2}$ with respect to $x$. Since $4yz$ acts as a constant multiplier here, apply the exponential chain rule directly to the exponential term:

$$\frac{\partial^3 u}{\partial x \partial y \partial z} = \frac{\partial}{\partial x}\left( 4yz e^{x^2 + y^2 + z^2} \right)$$

$$\frac{\partial^3 u}{\partial x \partial y \partial z} = 4yz \cdot \left[ e^{x^2 + y^2 + z^2} \cdot \frac{\partial}{\partial x}(x^2 + y^2 + z^2) \right]$$

$$\frac{\partial^3 u}{\partial x \partial y \partial z} = 4yz \cdot \left[ e^{x^2 + y^2 + z^2} \cdot (2x) \right]$$

$$\frac{\partial^3 u}{\partial x \partial y \partial z} = 8xyz e^{x^2 + y^2 + z^2}$$

Substitute the original function expression $u = e^{x^2 + y^2 + z^2}$ back into the equation:

$$\frac{\partial^3 u}{\partial x \partial y \partial z} = 8xyzu$$

$$\text{LHS} = \text{RHS}$$

This completes the proof.

---

## Problem 3

### Statement
If $u = \log(x^3 + y^3 + z^3 - 3xyz)$, prove that:

$$\left( \frac{\partial}{\partial x} + \frac{\partial}{\partial y} + \frac{\partial}{\partial z} \right)^2 u = \frac{-9}{(x + y + z)^2}$$

### Step-by-Step Derivation

To make this problem simple, let's understand what the squared operator means. The expression $\left( \frac{\partial}{\partial x} + \frac{\partial}{\partial y} + \frac{\partial}{\partial z} \right)^2 u$ means we apply the sum of the partial derivatives twice:

$$\left( \frac{\partial}{\partial x} + \frac{\partial}{\partial y} + \frac{\partial}{\partial z} \right) \left[ \frac{\partial u}{\partial x} + \frac{\partial u}{\partial y} + \frac{\partial u}{\partial z} \right]$$

#### Step 1: Find the sum of the first-order partial derivatives
Differentiate $u$ with respect to $x$ using the chain rule, keeping $y$ and $z$ constant:

$$\frac{\partial u}{\partial x} = \frac{1}{x^3 + y^3 + z^3 - 3xyz} \cdot \frac{\partial}{\partial x}(x^3 + y^3 + z^3 - 3xyz)$$

$$\frac{\partial u}{\partial x} = \frac{3x^2 - 3yz}{x^3 + y^3 + z^3 - 3xyz}$$

By symmetry, we can write down the partial derivatives with respect to $y$ and $z$ directly without repeating the full work:

$$\frac{\partial u}{\partial y} = \frac{3y^2 - 3zx}{x^3 + y^3 + z^3 - 3xyz}$$

$$\frac{\partial u}{\partial z} = \frac{3z^2 - 3xy}{x^3 + y^3 + z^3 - 3xyz}$$

Now, add these three partial derivatives together:

$$\frac{\partial u}{\partial x} + \frac{\partial u}{\partial y} + \frac{\partial u}{\partial z} = \frac{3x^2 - 3yz + 3y^2 - 3zx + 3z^2 - 3xy}{x^3 + y^3 + z^3 - 3xyz}$$

Factor out $3$ from the numerator:

$$\frac{\partial u}{\partial x} + \frac{\partial u}{\partial y} + \frac{\partial u}{\partial z} = \frac{3(x^2 + y^2 + z^2 - xy - yz - zx)}{x^3 + y^3 + z^3 - 3xyz}$$

Apply the standard algebraic factorization identity for the denominator: $x^3 + y^3 + z^3 - 3xyz = (x + y + z)(x^2 + y^2 + z^2 - xy - yz - zx)$:

$$\frac{\partial u}{\partial x} + \frac{\partial u}{\partial y} + \frac{\partial u}{\partial z} = \frac{3(x^2 + y^2 + z^2 - xy - yz - zx)}{(x + y + z)(x^2 + y^2 + z^2 - xy - yz - zx)}$$

Cancel out the identical quadratic terms from the numerator and denominator:

$$\frac{\partial u}{\partial x} + \frac{\partial u}{\partial y} + \frac{\partial u}{\partial z} = \frac{3}{x + y + z}$$

#### Step 2: Apply the outer differential operator
Now, substitute this simplified result back into our operator expression:

$$\left( \frac{\partial}{\partial x} + \frac{\partial}{\partial y} + \frac{\partial}{\partial z} \right) \left[ \frac{3}{x + y + z} \right]$$

$$\text{LHS} = \frac{\partial}{\partial x}\left( \frac{3}{x + y + z} \right) + \frac{\partial}{\partial y}\left( \frac{3}{x + y + z} \right) + \frac{\partial}{\partial z}\left( \frac{3}{x + y + z} \right)$$

Differentiate the term with respect to $x$ using the power chain rule by viewing it as $3(x+y+z)^{-1}$:

$$\frac{\partial}{\partial x}\left[ 3(x + y + z)^{-1} \right] = -3(x + y + z)^{-2} \cdot (1) = \frac{-3}{(x + y + z)^2}$$

By symmetry, the partial derivatives with respect to $y$ and $z$ yield the exact same result:

$$\frac{\partial}{\partial y}\left[ 3(x + y + z)^{-1} \right] = \frac{-3}{(x + y + z)^2}$$

$$\frac{\partial}{\partial z}\left[ 3(x + y + z)^{-1} \right] = \frac{-3}{(x + y + z)^2}$$

Combine all three calculated parts together:

$$\text{LHS} = \frac{-3}{(x + y + z)^2} + \frac{-3}{(x + y + z)^2} + \frac{-3}{(x + y + z)^2}$$

$$\text{LHS} = \frac{-9}{(x + y + z)^2}$$

$$\text{LHS} = \text{RHS}$$

This completes the proof.

---

## Problem 4

### Statement
If $u = (1 - 2xy + y^2)^{-1/2}$, prove that:

$$\frac{\partial}{\partial x} \left[ (1 - x^2) \frac{\partial u}{\partial x} \right] + \frac{\partial}{\partial y} \left[ y^2 \frac{\partial u}{\partial y} \right] = 0$$

### Step-by-Step Derivation

#### Part 1: Finding the first expression term
Find the first partial derivative $\frac{\partial u}{\partial x}$ using the power chain rule:

$$\frac{\partial u}{\partial x} = -\frac{1}{2}(1 - 2xy + y^2)^{-3/2} \cdot \frac{\partial}{\partial x}(1 - 2xy + y^2)$$

$$\frac{\partial u}{\partial x} = -\frac{1}{2}(1 - 2xy + y^2)^{-3/2} \cdot (-2y)$$

$$\frac{\partial u}{\partial x} = y(1 - 2xy + y^2)^{-3/2}$$

Multiply this result by $(1 - x^2)$:

$$(1 - x^2) \frac{\partial u}{\partial x} = y(1 - x^2)(1 - 2xy + y^2)^{-3/2}$$

Differentiate this product expression with respect to $x$. Since $y$ acts as a constant multiplier, use the product rule on $(1-x^2)$ and $(1 - 2xy + y^2)^{-3/2}$:

$$\frac{\partial}{\partial x} \left[ (1 - x^2) \frac{\partial u}{\partial x} \right] = y \cdot \left[ \frac{\partial}{\partial x}(1 - x^2) \cdot (1 - 2xy + y^2)^{-3/2} + (1 - x^2) \cdot \frac{\partial}{\partial x}(1 - 2xy + y^2)^{-3/2} \right]$$

$$\frac{\partial}{\partial x} \left[ (1 - x^2) \frac{\partial u}{\partial x} \right] = y \cdot \left[ -2x(1 - 2xy + y^2)^{-3/2} + (1 - x^2) \cdot \left( -\frac{3}{2}(1 - 2xy + y^2)^{-5/2} \cdot (-2y) \right) \right]$$

$$\frac{\partial}{\partial x} \left[ (1 - x^2) \frac{\partial u}{\partial x} \right] = y \cdot \left[ -2x(1 - 2xy + y^2)^{-3/2} + 3y(1 - x^2)(1 - 2xy + y^2)^{-5/2} \right]$$

Factor out $(1 - 2xy + y^2)^{-5/2}$ to make combining terms easier later:

$$\frac{\partial}{\partial x} \left[ (1 - x^2) \frac{\partial u}{\partial x} \right] = y(1 - 2xy + y^2)^{-5/2} \cdot \left[ -2x(1 - 2xy + y^2) + 3y(1 - x^2) \right]$$

$$\frac{\partial}{\partial x} \left[ (1 - x^2) \frac{\partial u}{\partial x} \right] = y(1 - 2xy + y^2)^{-5/2} \cdot \left[ -2x + 4x^2y - 2xy^2 + 3y - 3x^2y \right]$$

$$\frac{\partial}{\partial x} \left[ (1 - x^2) \frac{\partial u}{\partial x} \right] = y(1 - 2xy + y^2)^{-5/2} \cdot \left[ -2x + x^2y - 2xy^2 + 3y \right]$$

---

#### Part 2: Finding the second expression term
Find the first partial derivative $\frac{\partial u}{\partial y}$ using the power chain rule:

$$\frac{\partial u}{\partial y} = -\frac{1}{2}(1 - 2xy + y^2)^{-3/2} \cdot \frac{\partial}{\partial y}(1 - 2xy + y^2)$$

$$\frac{\partial u}{\partial y} = -\frac{1}{2}(1 - 2xy + y^2)^{-3/2} \cdot (-2x + 2y)$$

$$\frac{\partial u}{\partial y} = (x - y)(1 - 2xy + y^2)^{-3/2}$$

Multiply this result by $y^2$:

$$y^2 \frac{\partial u}{\partial y} = y^2(x - y)(1 - 2xy + y^2)^{-3/2}$$

$$y^2 \frac{\partial u}{\partial y} = (xy^2 - y^3)(1 - 2xy + y^2)^{-3/2}$$

Differentiate this expression with respect to $y$ using the product rule:

$$\frac{\partial}{\partial y} \left[ y^2 \frac{\partial u}{\partial y} \right] = \frac{\partial}{\partial y}(xy^2 - y^3) \cdot (1 - 2xy + y^2)^{-3/2} + (xy^2 - y^3) \cdot \frac{\partial}{\partial y}(1 - 2xy + y^2)^{-3/2}$$

$$\frac{\partial}{\partial y} \left[ y^2 \frac{\partial u}{\partial y} \right] = (2xy - 3y^2)(1 - 2xy + y^2)^{-3/2} + (xy^2 - y^3) \cdot \left( -\frac{3}{2}(1 - 2xy + y^2)^{-5/2} \cdot (-2x + 2y) \right)$$

Factor out $-2$ from the last derivative term to simplify the fraction fraction multiplier:

$$\frac{\partial}{\partial y} \left[ y^2 \frac{\partial u}{\partial y} \right] = (2xy - 3y^2)(1 - 2xy + y^2)^{-3/2} + (xy^2 - y^3) \cdot \left( 3(x - y)(1 - 2xy + y^2)^{-5/2} \right)$$

Factor out $y^2$ from the term $(xy^2 - y^3)$ to match our goal structure:

$$\frac{\partial}{\partial y} \left[ y^2 \frac{\partial u}{\partial y} \right] = (2xy - 3y^2)(1 - 2xy + y^2)^{-3/2} + 3y^2(x - y)^2(1 - 2xy + y^2)^{-5/2}$$

Factor out the shared base term $y(1 - 2xy + y^2)^{-5/2}$:

$$\frac{\partial}{\partial y} \left[ y^2 \frac{\partial u}{\partial y} \right] = y(1 - 2xy + y^2)^{-5/2} \cdot \left[ (2x - 3y)(1 - 2xy + y^2) + 3y(x - y)^2 \right]$$

Expand the polynomial bracket terms inside the expression:

$$\frac{\partial}{\partial y} \left[ y^2 \frac{\partial u}{\partial y} \right] = y(1 - 2xy + y^2)^{-5/2} \cdot \left[ (2x - 4x^2y + 2xy^2 - 3y + 6xy^2 - 3y^3) + 3y(x^2 - 2xy + y^2) \right]$$

$$\frac{\partial}{\partial y} \left[ y^2 \frac{\partial u}{\partial y} \right] = y(1 - 2xy + y^2)^{-5/2} \cdot \left[ 2x - 4x^2y + 8xy^2 - 3y - 3y^3 + 3x^2y - 6xy^2 + 3y^3 \right]$$

Combine like variables to find the final formatted version of Part 2:

$$\frac{\partial}{\partial y} \left[ y^2 \frac{\partial u}{\partial y} \right] = y(1 - 2xy + y^2)^{-5/2} \cdot \left[ 2x - x^2y + 2xy^2 - 3y \right]$$

---

#### Part 3: Combining the Terms
Now, add the results of Part 1 and Part 2 together to check the complete Left-Hand Side (LHS):

$$\text{LHS} = y(1 - 2xy + y^2)^{-5/2} \cdot \left[ (-2x + x^2y - 2xy^2 + 3y) + (2x - x^2y + 2xy^2 - 3y) \right]$$

Notice how every single term inside the brackets cancels perfectly with its exact opposite sign counterpart:

$$\text{LHS} = y(1 - 2xy + y^2)^{-5/2} \cdot [0]$$

$$\text{LHS} = 0$$

$$\text{LHS} = \text{RHS}$$

This completes the proof.

---
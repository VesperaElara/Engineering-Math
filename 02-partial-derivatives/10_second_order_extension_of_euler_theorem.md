# Engineering Mathematics: Second-Order Extension (Corollary) of Euler's Theorem

When dealing with higher-order partial differential equations, calculating second-order derivatives ($ \frac{\partial^2 u}{\partial x^2} $, $ \frac{\partial^2 u}{\partial x \partial y} $, $\frac{\partial^2 u}{\partial y^2}$) manually becomes incredibly tedious. This standard corollary extends Euler's Theorem to handle second-order operations directly using the degree $n$.

---

## The Theorem (Second-Order Form)

If $u$ is a **homogeneous function** of independent variables $x$ and $y$ with a degree of $n$, then:

$$x^2 \frac{\partial^2 u}{\partial x^2} + 2xy \frac{\partial^2 u}{\partial x \partial y} + y^2 \frac{\partial^2 u}{\partial y^2} = n(n - 1)u$$

---

## Step-by-Step Proof

The proof builds directly upon the first-order Euler's Theorem by differentiating it partially with respect to $x$ and $y$.

By Euler's standard theorem, we know:
$$x \frac{\partial u}{\partial x} + y \frac{\partial u}{\partial y} = nu \quad \text{--- (Equation 1)}$$

---

### Step 1: Differentiate Equation 1 Partially with Respect to $x$

Apply the operator $\frac{\partial}{\partial x}$ to both sides of Equation 1:
$$\frac{\partial}{\partial x} \left( x \frac{\partial u}{\partial x} + y \frac{\partial u}{\partial y} \right) = \frac{\partial}{\partial x} (nu)$$

Distribute the derivative. Use the **Product Rule** on the first term ($x \cdot \frac{\partial u}{\partial x}$) and treat $y$ as a constant in the second term:
$$\left[ x \frac{\partial^2 u}{\partial x^2} + \frac{\partial u}{\partial x} \cdot (1) \right] + y \frac{\partial^2 u}{\partial x \partial y} = n \frac{\partial u}{\partial x}$$

Rearrange the equation to group the higher-order terms together:
$$x \frac{\partial^2 u}{\partial x^2} + y \frac{\partial^2 u}{\partial x \partial y} = n \frac{\partial u}{\partial x} - \frac{\partial u}{\partial x}$$

Factor out the first derivative on the right side:
$$x \frac{\partial^2 u}{\partial x^2} + y \frac{\partial^2 u}{\partial x \partial y} = (n - 1) \frac{\partial u}{\partial x}$$

Multiply this entire equation by $x$ to scale the order properly:
$$x^2 \frac{\partial^2 u}{\partial x^2} + xy \frac{\partial^2 u}{\partial x \partial y} = (n - 1) x \frac{\partial u}{\partial x} \quad \text{--- (Equation 2)}$$

---

### Step 2: Differentiate Equation 1 Partially with Respect to $y$

Apply the operator $\frac{\partial}{\partial y}$ to both sides of Equation 1:
$$\frac{\partial}{\partial y} \left( x \frac{\partial u}{\partial x} + y \frac{\partial u}{\partial y} \right) = \frac{\partial}{\partial y} (nu)$$

Distribute the derivative. Treat $x$ as a constant in the first term, and apply the **Product Rule** on the second term ($y \cdot \frac{\partial u}{\partial y}$):
$$x \frac{\partial^2 u}{\partial y \partial x} + \left[ y \frac{\partial^2 u}{\partial y^2} + \frac{\partial u}{\partial y} \cdot (1) \right] = n \frac{\partial u}{\partial y}$$

Assuming the function is continuous and well-behaved, the mixed partial derivatives are equal ($\frac{\partial^2 u}{\partial y \partial x} = \frac{\partial^2 u}{\partial x \partial y}$). Rearrange the terms:
$$x \frac{\partial^2 u}{\partial x \partial y} + y \frac{\partial^2 u}{\partial y^2} = n \frac{\partial u}{\partial y} - \frac{\partial u}{\partial y}$$

Factor out the first derivative on the right side:
$$x \frac{\partial^2 u}{\partial x \partial y} + y \frac{\partial^2 u}{\partial y^2} = (n - 1) \frac{\partial u}{\partial y}$$

Multiply this entire equation by $y$ to scale the order properly:
$$xy \frac{\partial^2 u}{\partial x \partial y} + y^2 \frac{\partial^2 u}{\partial y^2} = (n - 1) y \frac{\partial u}{\partial y} \quad \text{--- (Equation 3)}$$

---

### Step 3: Add Equation 2 and Equation 3 Together

Combine the left-hand sides and right-hand sides of both equations:
$$\text{LHS} = \left( x^2 \frac{\partial^2 u}{\partial x^2} + xy \frac{\partial^2 u}{\partial x \partial y} \right) + \left( xy \frac{\partial^2 u}{\partial x \partial y} + y^2 \frac{\partial^2 u}{\partial y^2} \right)$$

$$\text{RHS} = (n - 1) x \frac{\partial u}{\partial x} + (n - 1) y \frac{\partial u}{\partial y}$$

Simplify the Left-Hand Side by combining the two identical $xy \frac{\partial^2 u}{\partial x \partial y}$ terms:
$$\text{LHS} = x^2 \frac{\partial^2 u}{\partial x^2} + 2xy \frac{\partial^2 u}{\partial x \partial y} + y^2 \frac{\partial^2 u}{\partial y^2}$$

Factor out the shared term $(n - 1)$ on the Right-Hand Side:
$$\text{RHS} = (n - 1) \left( x \frac{\partial u}{\partial x} + y \frac{\partial u}{\partial y} \right)$$

Notice that the bracketed expression remaining on the right-hand side is exactly our original first-order Euler's Theorem expression from Equation 1. Substitute $\left( x \frac{\partial u}{\partial x} + y \frac{\partial u}{\partial y} \right) = nu$:
$$\text{RHS} = (n - 1) (nu)$$

$$\text{RHS} = n(n - 1)u$$

Equating LHS and RHS gives:
$$x^2 \frac{\partial^2 u}{\partial x^2} + 2xy \frac{\partial^2 u}{\partial x \partial y} + y^2 \frac{\partial^2 u}{\partial y^2} = n(n - 1)u$$

Hence, proved.
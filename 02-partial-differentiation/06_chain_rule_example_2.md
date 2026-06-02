# Engineering Mathematics: Partial Differentiation (Chain Rule)

## Problem Statement

Given that $z = f(x, y)$, where $x$ and $y$ are functions of independent variables $u$ and $v$:
$$x = e^u \cos v$$

$$y = e^u \sin v$$

Prove that:
1. $x \frac{\partial z}{\partial v} + y \frac{\partial z}{\partial u} = e^{2u} \frac{\partial z}{\partial y}$
2. $\left(\frac{\partial z}{\partial u}\right)^2 + \left(\frac{\partial z}{\partial v}\right)^2 = e^{2u} \left[ \left(\frac{\partial z}{\partial x}\right)^2 + \left(\frac{\partial z}{\partial y}\right)^2 \right]$

```text
       [ z ]
       /   \
      /     \
    [x]     [y]
      \     /
       \   /
       [u,v]
```

---

## Prerequisites: Partial Derivatives of $x$ and $y$

Before proving the statements, calculate the partial derivatives of $x$ and $y$ with respect to $u$ and $v$.

### Differentiating $x = e^u \cos v$
$$\frac{\partial x}{\partial u} = e^u \cos v = x$$

$$\frac{\partial x}{\partial v} = -e^u \sin v = -y$$

### Differentiating $y = e^u \sin v$
$$\frac{\partial y}{\partial u} = e^u \sin v = y$$

$$\frac{\partial y}{\partial v} = e^u \cos v = x$$

---

## Establishing the Chain Rule Equations

Since $z$ depends on $x$ and $y$, and both $x$ and $y$ depend on $u$ and $v$, the total chain rule structure is:

$$\frac{\partial z}{\partial u} = \frac{\partial z}{\partial x} \frac{\partial x}{\partial u} + \frac{\partial z}{\partial y} \frac{\partial y}{\partial u}$$

$$\frac{\partial z}{\partial v} = \frac{\partial z}{\partial x} \frac{\partial x}{\partial v} + \frac{\partial z}{\partial y} \frac{\partial y}{\partial v}$$

Substitute the known partial derivatives into these chain rule equations:

$$\frac{\partial z}{\partial u} = x \frac{\partial z}{\partial x} + y \frac{\partial z}{\partial y} \quad \text{--- (Equation 1)}$$

$$\frac{\partial z}{\partial v} = -y \frac{\partial z}{\partial x} + x \frac{\partial z}{\partial y} \quad \text{--- (Equation 2)}$$

---

## Part 1: Verification of Statement (i)

We need to evaluate the Left-Hand Side (LHS):
$$\text{LHS} = x \frac{\partial z}{\partial v} + y \frac{\partial z}{\partial u}$$

Substitute Equation 1 and Equation 2 into the expression:
$$\text{LHS} = x \left( -y \frac{\partial z}{\partial x} + x \frac{\partial z}{\partial y} \right) + y \left( x \frac{\partial z}{\partial x} + y \frac{\partial z}{\partial y} \right)$$

Expand the terms:
$$\text{LHS} = -xy \frac{\partial z}{\partial x} + x^2 \frac{\partial z}{\partial y} + xy \frac{\partial z}{\partial x} + y^2 \frac{\partial z}{\partial y}$$

Cancel the counteracting terms:
$$\text{LHS} = (x^2 + y^2) \frac{\partial z}{\partial y}$$

Simplify $(x^2 + y^2)$ using the original expressions for $x$ and $y$:
$$x^2 + y^2 = (e^u \cos v)^2 + (e^u \sin v)^2$$

$$x^2 + y^2 = e^{2u} \cos^2 v + e^{2u} \sin^2 v$$

$$x^2 + y^2 = e^{2u} (\cos^2 v + \sin^2 v)$$

$$x^2 + y^2 = e^{2u}$$

Substitute this value back into the expression:
$$\text{LHS} = e^{2u} \frac{\partial z}{\partial y} = \text{RHS}$$

Hence, proved.

---

## Part 2: Verification of Statement (ii)

We need to evaluate the Left-Hand Side (LHS):
$$\text{LHS} = \left(\frac{\partial z}{\partial u}\right)^2 + \left(\frac{\partial z}{\partial v}\right)^2$$

Substitute Equation 1 and Equation 2 into the expression:
$$\text{LHS} = \left( x \frac{\partial z}{\partial x} + y \frac{\partial z}{\partial y} \right)^2 + \left( -y \frac{\partial z}{\partial x} + x \frac{\partial z}{\partial y} \right)^2$$

Expand both squared brackets using $(a+b)^2 = a^2 + 2ab + b^2$ and $(a-b)^2 = a^2 - 2ab + b^2$:
$$\left( x \frac{\partial z}{\partial x} + y \frac{\partial z}{\partial y} \right)^2 = x^2 \left(\frac{\partial z}{\partial x}\right)^2 + 2xy \frac{\partial z}{\partial x}\frac{\partial z}{\partial y} + y^2 \left(\frac{\partial z}{\partial y}\right)^2$$

$$\left( -y \frac{\partial z}{\partial x} + x \frac{\partial z}{\partial y} \right)^2 = y^2 \left(\frac{\partial z}{\partial x}\right)^2 - 2xy \frac{\partial z}{\partial x}\frac{\partial z}{\partial y} + x^2 \left(\frac{\partial z}{\partial y}\right)^2$$

Add the two expanded expressions together:
$$\text{LHS} = x^2 \left(\frac{\partial z}{\partial x}\right)^2 + y^2 \left(\frac{\partial z}{\partial y}\right)^2 + y^2 \left(\frac{\partial z}{\partial x}\right)^2 + x^2 \left(\frac{\partial z}{\partial y}\right)^2$$

Group the common derivative terms:
$$\text{LHS} = (x^2 + y^2) \left(\frac{\partial z}{\partial x}\right)^2 + (x^2 + y^2) \left(\frac{\partial z}{\partial y}\right)^2$$

Factor out $(x^2 + y^2)$:
$$\text{LHS} = (x^2 + y^2) \left[ \left(\frac{\partial z}{\partial x}\right)^2 + \left(\frac{\partial z}{\partial y}\right)^2 \right]$$

Substitute $x^2 + y^2 = e^{2u}$:
$$\text{LHS} = e^{2u} \left[ \left(\frac{\partial z}{\partial x}\right)^2 + \left(\frac{\partial z}{\partial y}\right)^2 \right] = \text{RHS}$$

Hence, proved.


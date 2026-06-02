# Engineering Mathematics: Higher-Order Partial Differentiation

## Introduction to Higher-Order Partial Derivatives

Just like ordinary derivatives, you can differentiate a partial derivative multiple times to find higher-order derivatives. When dealing with multiple variables, this introduces the concept of **mixed partial derivatives**.

The notation can look intimidating at first glance, but it follows a strict directional rule.

---

## 1. Pure Second-Order Partial Derivatives

These represent differentiating twice with respect to the **same** variable.

### With Respect to $x$
Differentiate the first partial derivative $\frac{\partial z}{\partial x}$ one more time with respect to $x$:

$$\frac{\partial^2 z}{\partial x^2} = \frac{\partial}{\partial x} \left( \frac{\partial z}{\partial x} \right) = f_{xx} = u_{xx}$$

### With Respect to $y$
Differentiate the first partial derivative $\frac{\partial z}{\partial y}$ one more time with respect to $y$:

$$\frac{\partial^2 z}{\partial y^2} = \frac{\partial}{\partial y} \left( \frac{\partial z}{\partial y} \right) = f_{yy} = u_{yy}$$

---

## 2. Mixed Second-Order Partial Derivatives

These represent differentiating with respect to **one variable first**, and then differentiating that result with respect to a **different variable**.

### Differentiating $y$ First, then $x$
Look closely at the denominator of the Leibniz notation. Read it from **right to left**:

$$\frac{\partial^2 z}{\partial x \partial y} = \frac{\partial}{\partial x} \left( \frac{\partial z}{\partial y} \right) = f_{xy} = u_{xy}$$

* **Leibniz Notation ($\frac{\partial^2 z}{\partial x \partial y}$):** Read right-to-left. The variable closest to $z$ ($\partial y$) is evaluated first.
* **Subscript Notation ($f_{xy}$):** Read left-to-right. The variable written first ($x$) is evaluated first.

### Differentiating $x$ First, then $y$
Similarly, to differentiate with respect to $x$ first and then $y$:

$$\frac{\partial^2 z}{\partial y \partial x} = \frac{\partial}{\partial y} \left( \frac{\partial z}{\partial x} \right) = f_{yx} = u_{yx}$$

---

## Important Property: Clairaut's Theorem

For almost every well-behaved, continuous function you will encounter in engineering mathematics, the order of mixed differentiation does not change the final outcome:

$$f_{xy} = f_{yx}$$

$$\frac{\partial^2 z}{\partial x \partial y} = \frac{\partial^2 z}{\partial y \partial x}$$
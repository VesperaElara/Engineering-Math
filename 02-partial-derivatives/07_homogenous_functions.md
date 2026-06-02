# Engineering Mathematics: Homogeneous Functions

A function is said to be homogeneous if scaling all its independent variables by a constant factor results in scaling the overall function value by a proportional power of that factor. Identifying homogeneous functions and determining their degree is a critical prerequisite for applying **Euler's Theorem** in partial differentiation.

---

## Core Concept: What is a Homogeneous Function?

A function $f(x, y, z)$ is called a **homogeneous function of degree $n$** if, when replacing $x$ with $xt$, $y$ with $yt$, and $z$ with $zt$ (where $t$ is a non-zero scaling factor), it satisfies the algebraic identity:

$$f(xt, yt, zt) = t^n f(x, y, z)$$

Here, $n$ represents the **degree** of homogeneity. The degree can be any real number: positive, negative, zero, or a fraction.

---

## Example 1: Basic Algebraic Homogeneous Function

### Problem Statement
Determine if the function $u = x^2 + y^2 + z^2$ is homogeneous, and find its degree.

### Step-by-Step Verification

Define the function algebraically:
$$f(x, y, z) = x^2 + y^2 + z^2$$

Substitute $x \to xt$, $y \to yt$, and $z \to zt$ into the function:
$$f(xt, yt, zt) = (xt)^2 + (yt)^2 + (zt)^2$$

Expand the individual squared terms:
$$f(xt, yt, zt) = x^2 t^2 + y^2 t^2 + z^2 t^2$$

Factor out the common term $t^2$ from the entire expression:
$$f(xt, yt, zt) = t^2 (x^2 + y^2 + z^2)$$

Substitute back the original function identity $u = f(x, y, z)$:
$$f(xt, yt, zt) = t^2 u = t^2 f(x, y, z)$$

### Conclusion
Because the function cleanly factored into the form $t^2 f(x, y, z)$, the function $u$ is a **homogeneous function of degree 2**.

---

## Example 2: Logarithmic/Fractional Composition (Non-Homogeneous Overall)

### Problem Statement
Analyze the function $u = \log\left(\frac{x^3 + y^3}{x^2 + y^2}\right)$ to determine if it satisfies the structural conditions of homogeneity.

### Step-by-Step Analysis

Define the inner algebraic rational expression as a distinct function:
$$f(x, y) = \frac{x^3 + y^3}{x^2 + y^2}$$

Substitute $x \to xt$ and $y \to yt$ into this inner algebraic component:
$$f(xt, yt) = \frac{(xt)^3 + (yt)^3}{(xt)^2 + (yt)^2}$$

Expand the exponential powers across both numerator and denominator terms:
$$f(xt, yt) = \frac{x^3 t^3 + y^3 t^3}{x^2 t^2 + y^2 t^2}$$

Factor out $t^3$ in the numerator and $t^2$ in the denominator:
$$f(xt, yt) = \frac{t^3 (x^3 + y^3)}{t^2 (x^2 + y^2)}$$

Simplify the powers of $t$ using the exponent law $\frac{a^m}{a^n} = a^{m-n}$:
$$\frac{t^3}{t^2} = t^{3-2} = t^1$$

Rewrite the expression to isolate the parameter $t$:
$$f(xt, yt) = t^1 \cdot \left(\frac{x^3 + y^3}{x^2 + y^2}\right) = t^1 f(x, y)$$

Thus, the *inner algebraic argument* is homogeneous of degree 1. Now, substitute this result back into the full definition of the logarithmic expression $u$:
$$u(xt, yt) = \log\left( t^1 \cdot \left(\frac{x^3 + y^3}{x^2 + y^2}\right) \right)$$

### Conclusion
Because of the outer logarithmic wrapper, you cannot factor $t$ completely outside the function to achieve the form $t^n u$. Therefore, **the overall function $u$ is not homogeneous**. 

> **Crucial Transition for Euler's Theorem:** While $u$ itself is not homogeneous, the inner component is. In upcoming Euler's Theorem applications, you will learn to drop the outer logarithm by transforming the equation to $e^u = \frac{x^3 + y^3}{x^2 + y^2}$, creating a new substitute function that *is* perfectly homogeneous of degree 1.
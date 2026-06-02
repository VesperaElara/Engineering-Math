# Engineering Mathematics: Euler's Theorem on Homogeneous Functions

The proof relies on just two foundational tools you already know: the **product rule** and the **chain rule**. Once you see how the variables decouple, the math practically does the work for itself.

---

## The Theorem

If $z$ is a **homogeneous function** of independent variables $x$ and $y$ with a degree of $n$, then:

$$x \frac{\partial z}{\partial x} + y \frac{\partial z}{\partial y} = nz$$

---

## Core Concept: The Alternating Form of Homogeneity

Before diving into the calculus, there is an alternative way to express any homogeneous function. If $z = f(x,y)$ is homogeneous of degree $n$, we can pull out $x^n$ completely, leaving the inside as a pure ratio of $\frac{y}{x}$:

$$z = x^n \cdot \phi\left(\frac{y}{x}\right)$$

> **Why does this work?** Think of it this way: if you factor out $x^n$ from an expression where every term has a combined power of $n$, every $y$ term left behind gets divided by an equivalent power of $x$, grouping cleanly into $\left(\frac{y}{x}\right)$. We use $\phi$ (or $f$ as written by the teacher) to represent this new function of the single combined variable $\frac{y}{x}$.

### Visualizing the $\frac{y}{x}$ Form with an Example

To understand why the inner term remains $\frac{y}{x}$ rather than $\frac{y}{x^n}$, consider a homogeneous function of degree 3 ($n = 3$):
$$z = x^3 + x^2y + y^3$$

Forcefully factor out $x^3$ from every single term:
$$z = x^3 \left( \frac{x^3}{x^3} + \frac{x^2y}{x^3} + \frac{y^3}{x^3} \right)$$

Simplify the ratios inside the parentheses using standard exponent rules:
$$z = x^3 \left[ 1 + \left(\frac{y}{x}\right) + \left(\frac{y}{x}\right)^3 \right]$$

Notice that every variable inside the bracket has collapsed into a variation of the single ratio $\left(\frac{y}{x}\right)$. This allows us to represent the entire bracketed expression as a general function of that ratio, denoted as $\phi\left(\frac{y}{x}\right)$:
$$z = x^3 \cdot \phi\left(\frac{y}{x}\right)$$

---

## Step-by-Step Proof

To prove the theorem, we will find the partial derivatives $\frac{\partial z}{\partial x}$ and $\frac{\partial z}{\partial y}$ using our alternating form, and then evaluate $x \frac{\partial z}{\partial x} + y \frac{\partial z}{\partial y}$.

### Step 1: Finding $\frac{\partial z}{\partial x}$
Because $x$ appears both in $x^n$ and inside the function $\phi\left(\frac{y}{x}\right)$, we must apply the **Product Rule**: $\frac{\partial}{\partial x}[u \cdot v] = u \frac{\partial v}{\partial x} + v \frac{\partial u}{\partial x}$.

$$\frac{\partial z}{\partial x} = x^n \cdot \frac{\partial}{\partial x}\left[\phi\left(\frac{y}{x}\right)\right] + \phi\left(\frac{y}{x}\right) \cdot \frac{\partial}{\partial x}[x^n]$$

Now use the **Chain Rule** to differentiate the inner term $\frac{y}{x}$ with respect to $x$ (treating $y$ as a constant):
$$\frac{\partial}{\partial x}\left[\phi\left(\frac{y}{x}\right)\right] = \phi'\left(\frac{y}{x}\right) \cdot \frac{\partial}{\partial x}\left(\frac{y}{x}\right) = \phi'\left(\frac{y}{x}\right) \cdot \left(-\frac{y}{x^2}\right)$$

Substitute this back into the product rule expansion:
$$\frac{\partial z}{\partial x} = x^n \cdot \phi'\left(\frac{y}{x}\right) \cdot \left(-\frac{y}{x^2}\right) + \phi\left(\frac{y}{x}\right) \cdot n x^{n-1}$$

Simplify the first term's algebraic exponent rules ($\frac{x^n}{x^2} = x^{n-2}$):
$$\frac{\partial z}{\partial x} = -x^{n-2} \cdot y \cdot \phi'\left(\frac{y}{x}\right) + n x^{n-1} \cdot \phi\left(\frac{y}{x}\right)$$

Multiply this entire equation by $x$ to match the first term of Euler's Theorem:
$$x \frac{\partial z}{\partial x} = -x^{n-1} \cdot y \cdot \phi'\left(\frac{y}{x}\right) + n x^n \cdot \phi\left(\frac{y}{x}\right) \quad \text{--- (Equation 1)}$$

---

### Step 2: Finding $\frac{\partial z}{\partial y}$
Now differentiate $z = x^n \cdot \phi\left(\frac{y}{x}\right)$ with respect to $y$. Here, $x^n$ acts as a pure constant multiplier:

$$\frac{\partial z}{\partial y} = x^n \cdot \frac{\partial}{\partial y}\left[\phi\left(\frac{y}{x}\right)\right]$$

Apply the chain rule to the inner term with respect to $y$ (treating $x$ as a constant):
$$\frac{\partial}{\partial y}\left(\frac{y}{x}\right) = \frac{1}{x}$$

$$\frac{\partial z}{\partial y} = x^n \cdot \phi'\left(\frac{y}{x}\right) \cdot \frac{1}{x}$$

Simplify the algebraic exponents ($\frac{x^n}{x} = x^{n-1}$):
$$\frac{\partial z}{\partial y} = x^{n-1} \cdot \phi'\left(\frac{y}{x}\right)$$

Multiply this entire equation by $y$ to match the second term of Euler's Theorem:
$$y \frac{\partial z}{\partial y} = x^{n-1} \cdot y \cdot \phi'\left(\frac{y}{x}\right) \quad \text{--- (Equation 2)}$$

---

### Step 3: Combining the Terms
Now add Equation 1 and Equation 2 together:

$$\text{LHS} = x \frac{\partial z}{\partial x} + y \frac{\partial z}{\partial y}$$

$$\text{LHS} = \left[-x^{n-1} \cdot y \cdot \phi'\left(\frac{y}{x}\right) + n x^n \cdot \phi\left(\frac{y}{x}\right)\right] + \left[x^{n-1} \cdot y \cdot \phi'\left(\frac{y}{x}\right)\right]$$

Notice that the complex derivative terms completely cancel each other out:
$$\text{LHS} = n x^n \cdot \phi\left(\frac{y}{x}\right)$$

Substitute back our original definition ($z = x^n \cdot \phi\left(\frac{y}{x}\right)$):
$$\text{LHS} = n z = \text{RHS}$$

Hence, proved.
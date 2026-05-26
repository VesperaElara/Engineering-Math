# Engineering Mathematics: Mastering the Chain Rule

## Question 1

### Problem Statement
Express $\frac{\partial w}{\partial r}$ and $\frac{\partial w}{\partial s}$ if:
* $w = x + 2y + z^2$
* $x = \frac{r}{s}$
* $y = r^2 + \log(s)$
* $z = 2r$

### Dependency Analysis
* The primary function $w$ depends directly on three intermediate variables: $x$, $y$, and $z$.
* Each of these intermediate variables depends on the independent variables $r$ and $s$.
* Therefore, to find a derivative with respect to $r$ or $s$, we must sum the contributions passing through all three intermediate channels ($x$, $y$, and $z$).

```text
                  w
               /  |  \
              /   |   \
             x    y    z
            / \  / \  / \
           r   s r  s r  s
```

### Let's Establish the Building Blocks

Before building the full paths, let's find the individual derivative links.

#### Top-to-Intermediate Layer (Differentiating $w$):
* $\frac{\partial w}{\partial x} = 1$
* $\frac{\partial w}{\partial y} = 2$
* $\frac{\partial w}{\partial z} = 2z$

#### Intermediate-to-Bottom Layer (Differentiating with respect to $r$ and $s$):
For $x = r \cdot s^{-1}$:
* $\frac{\partial x}{\partial r} = \frac{1}{s}$
* $\frac{\partial x}{\partial s} = -\frac{r}{s^2}$

For $y = r^2 + \log(s)$:
* $\frac{\partial y}{\partial r} = 2r$
* $\frac{\partial y}{\partial s} = \frac{1}{s}$

For $z = 2r$:
* $\frac{\partial z}{\partial r} = 2$
* $\frac{\partial z}{\partial s} = 0$ *(Since $z$ has no $s$ terms, it behaves as a pure constant)*

---

### Step-by-Step Execution

#### 1. Finding $\frac{\partial w}{\partial r}$
Sum the total derivative contributions through $x$, $y$, and $z$ with respect to $r$:

$$\frac{\partial w}{\partial r} = \left(\frac{\partial w}{\partial x} \cdot \frac{\partial x}{\partial r}\right) + \left(\frac{\partial w}{\partial y} \cdot \frac{\partial y}{\partial r}\right) + \left(\frac{\partial w}{\partial z} \cdot \frac{\partial z}{\partial r}\right)$$

Substitute the building blocks into the expansion formula:

$$\frac{\partial w}{\partial r} = (1) \cdot \left(\frac{1}{s}\right) + (2) \cdot (2r) + (2z) \cdot (2)$$

$$\frac{\partial w}{\partial r} = \frac{1}{s} + 4r + 4z$$

Since the problem requires the answer **in terms of $r$ and $s$**, substitute $z = 2r$ back into the equation:

$$\frac{\partial w}{\partial r} = \frac{1}{s} + 4r + 4(2r)$$

$$\frac{\partial w}{\partial r} = \frac{1}{s} + 12r$$

#### 2. Finding $\frac{\partial w}{\partial s}$
Sum the total derivative contributions through $x$, $y$, and $z$ with respect to $s$:

$$\frac{\partial w}{\partial s} = \left(\frac{\partial w}{\partial x} \cdot \frac{\partial x}{\partial s}\right) + \left(\frac{\partial w}{\partial y} \cdot \frac{\partial y}{\partial s}\right) + \left(\frac{\partial w}{\partial z} \cdot \frac{\partial z}{\partial s}\right)$$

$$\frac{\partial w}{\partial s} = (1) \cdot \left(-\frac{r}{s^2}\right) + (2) \cdot \left(\frac{1}{s}\right) + (2z) \cdot (0)$$

$$\frac{\partial w}{\partial s} = -\frac{r}{s^2} + \frac{2}{s}$$

---

## Question 2

### Problem Statement
If $z = f(x, y)$ where $x = e^u + e^{-v}$ and $y = e^{-u} - e^v$, prove that:

$$\frac{\partial z}{\partial u} - \frac{\partial z}{\partial v} = x\frac{\partial z}{\partial x} - y\frac{\partial z}{\partial y}$$

### Dependency Analysis
* The dependent variable $z$ is a function of intermediate variables $x$ and $y$.
* Both $x$ and $y$ are functions of independent variables $u$ and $v$.
* Any derivative with respect to $u$ or $v$ must split into two parallel tracks: one through $x$ and one through $y$.

```text
              z
             / \
            x   y
           / \ / \
          u  v u  v
```

### Let's Establish the Building Blocks

Since $z = f(x, y)$ is an unspecified function, we leave $\frac{\partial z}{\partial x}$ and $\frac{\partial z}{\partial y}$ intact as operational terms. Let's compute the underlying variable relationships:

* $\frac{\partial x}{\partial u} = \frac{\partial}{\partial u}(e^u + e^{-v}) = e^u$
* $\frac{\partial x}{\partial v} = \frac{\partial}{\partial v}(e^u + e^{-v}) = -e^{-v}$
* $\frac{\partial y}{\partial u} = \frac{\partial}{\partial u}(e^{-u} - e^v) = -e^{-u}$
* $\frac{\partial y}{\partial v} = \frac{\partial}{\partial v}(e^{-u} - e^v) = -e^v$

---

### Step-by-Step Proof

#### Step 1: Write out the total derivative expansions for the LHS
Using the chain rule expansions, write out the expressions for $\frac{\partial z}{\partial u}$ and $\frac{\partial z}{\partial v}$:

$$\frac{\partial z}{\partial u} = \frac{\partial z}{\partial x}\frac{\partial x}{\partial u} + \frac{\partial z}{\partial y}\frac{\partial y}{\partial u} = \frac{\partial z}{\partial x}(e^u) + \frac{\partial z}{\partial y}(-e^{-u})$$

$$\frac{\partial z}{\partial v} = \frac{\partial z}{\partial x}\frac{\partial x}{\partial v} + \frac{\partial z}{\partial y}\frac{\partial y}{\partial v} = \frac{\partial z}{\partial x}(-e^{-v}) + \frac{\partial z}{\partial y}(-e^v)$$

#### Step 2: Evaluate Left-Hand Side ($\text{LHS} = \frac{\partial z}{\partial u} - \frac{\partial z}{\partial v}$)
Subtract the second expansion expression from the first expression:

$$\text{LHS} = \left[ e^u \frac{\partial z}{\partial x} - e^{-u} \frac{\partial z}{\partial y} \right] - \left[ -e^{-v} \frac{\partial z}{\partial x} - e^v \frac{\partial z}{\partial y} \right]$$

Distribute the negative sign carefully across both terms:

$$\text{LHS} = e^u \frac{\partial z}{\partial x} - e^{-u} \frac{\partial z}{\partial y} + e^{-v} \frac{\partial z}{\partial x} + e^v \frac{\partial z}{\partial y}$$

Group the common derivative factors together:

$$\text{LHS} = (e^u + e^{-v})\frac{\partial z}{\partial x} + (e^v - e^{-u})\frac{\partial z}{\partial y}$$

#### Step 3: Compare with the Right-Hand Side (RHS)
Refer back to your original structural variables given in the prompt:
* $x = e^u + e^{-v}$
* $-y = -(e^{-u} - e^v) = e^v - e^{-u}$

Substitute these exact variable values directly back into your grouped expression:

$$\text{LHS} = (x)\frac{\partial z}{\partial x} + (-y)\frac{\partial z}{\partial y}$$

$$\text{LHS} = x\frac{\partial z}{\partial x} - y\frac{\partial z}{\partial y} = \text{RHS}$$

This completes the proof.
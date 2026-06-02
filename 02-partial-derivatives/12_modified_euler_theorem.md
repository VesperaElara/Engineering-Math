# Engineering Mathematics: Total Derivatives & Modified Euler's Theorems

When working with multi-variable calculus, variables often depend on each other through intermediate paths, or functions are wrapped inside non-linear operations (like $\log$, $\sin^{-1}$, or $\tan^{-1}$). This set of notes covers **Total Derivatives (Chain Rule with Tree Diagrams)** and the **Modified (Composite) Euler’s Theorems** used to solve these systems efficiently.

---

## 1. Total Derivatives & Composite Functions (Chain Rule)

When a variable $z$ depends on $x$ and $y$, and those variables themselves depend on other parameters (like $u$ and $v$), we use the multi-variable chain rule. 

To prevent tracking errors, we map the dependencies using a **Tree Diagram**.

### Case A: $z = f(x, y)$ where $x = x(t)$ and $y = y(t)$
Here, $z$ ultimately depends on a single independent variable $t$. The derivative is called the **Total Derivative** ($\frac{dz}{dt}$):

$$\frac{dz}{dt} = \frac{\partial z}{\partial x} \cdot \frac{dx}{dt} + \frac{\partial z}{\partial y} \cdot \frac{dy}{dt}$$

### Case B: $z = f(x, y)$ where $x = x(u, v)$ and $y = y(u, v)$
Here, $z$ ultimately depends on two independent variables, $u$ and $v$. We must use partial derivatives ($\frac{\partial z}{\partial u}$ and $\frac{\partial z}{\partial v}$):

$$\frac{\partial z}{\partial u} = \frac{\partial z}{\partial x} \cdot \frac{\partial x}{\partial u} + \frac{\partial z}{\partial y} \cdot \frac{\partial y}{\partial u}$$

$$\frac{\partial z}{\partial v} = \frac{\partial z}{\partial x} \cdot \frac{\partial x}{\partial v} + \frac{\partial z}{\partial y} \cdot \frac{\partial y}{\partial v}$$

### Visualizing with a Tree Diagram
To write these equations automatically without memorization:
1. Start at the top variable ($z$).
2. Draw branches downward to its immediate intermediate variables ($x$ and $y$). Write partial derivatives ($\frac{\partial z}{\partial x}$, $\frac{\partial z}{\partial y}$) along these branches.
3. From $x$ and $y$, draw branches down to the final independent variables ($u$ and $v$). Write their respective derivatives along those paths.
4. **Rule:** Multiply down a single branch path; add distinct branch paths together.

---

## 2. First-Order Modified Euler's Theorem

### The Scenario
You are given a function equation $u = F(x, y)$, but $u$ is **not** homogeneous because it is trapped inside a non-linear wrapper (e.g., $u = \log(\dots)$ or $u = \tan^{-1}(\dots)$). 

However, if you isolate the algebraic core by transforming it into a substitute function $z = f(u)$, you find that $z$ **is** homogeneous with a degree of $n$.

### The Formula
Instead of working out the tedious partial derivatives of the wrapper manually, you can compute the first-order differential expression directly using:

$$x \frac{\partial u}{\partial x} + y \frac{\partial u}{\partial y} = n \cdot \frac{f(u)}{f'(u)} = g(u)$$

Where:
* $f(u)$ is the isolated algebraic function ($z$).
* $f'(u)$ is the derivative of that function with respect to $u$.
* $n$ is the degree of homogeneity of $z$.
* $g(u)$ is the resulting simplified expression.

### Common Shortcuts for $g(u)$
| If the wrapper is... | Isolated form $f(u) = z$ | Derivative $f'(u)$ | Value of $g(u) = n \cdot \frac{f(u)}{f'(u)}$ |
| :--- | :--- | :--- | :--- |
| $u = \log(\text{core})$ | $e^u$ | $e^u$ | $n$ |
| $u = \sin^{-1}(\text{core})$ | $\sin u$ | $\cos u$ | $n \tan u$ |
| $u = \cos^{-1}(\text{core})$ | $\cos u$ | $-\sin u$ | $-n \cot u$ |
| $u = \tan^{-1}(\text{core})$ | $\tan u$ | $\sec^2 u$ | $n \sin u \cos u = \frac{n}{2} \sin 2u$ |

---

## 3. Second-Order Modified Euler's Theorem

### The Formula
If a composite question requires you to find the value of a second-order differential expression, computing it directly by taking second derivatives of wrappers is incredibly error-prone. 

Instead, find the first-order expression $g(u)$ from the step above, and plug it directly into this corollary:

$$x^2 \frac{\partial^2 u}{\partial x^2} + 2xy \frac{\partial^2 u}{\partial x \partial y} + y^2 \frac{\partial^2 u}{\partial y^2} = g(u) \cdot \left[ g'(u) - 1 \right]$$

Where:
* $g(u)$ is the calculation outcome from the First-Order Modified Theorem.
* $g'(u)$ is the derivative of that specific outcome expression with respect to $u$.

---

## Step-by-Step Proof of the First-Order Modified Theorem

Let $z = f(u)$ be a homogeneous function of independent variables $x$ and $y$ with a degree of $n$.

By standard Euler's Theorem, we can state:
$$x \frac{\partial z}{\partial x} + y \frac{\partial z}{\partial y} = n z \quad \text{--- (Equation 1)}$$

Since $z$ is a function of $u$, and $u$ is a function of $x$ and $y$, we can find the partial derivatives of $z$ using the single-variable composite Chain Rule:
$$\frac{\partial z}{\partial x} = \frac{d z}{d u} \cdot \frac{\partial u}{\partial x} = f'(u) \frac{\partial u}{\partial x}$$

$$\frac{\partial z}{\partial y} = \frac{d z}{d u} \cdot \frac{\partial u}{\partial y} = f'(u) \frac{\partial u}{\partial y}$$

Substitute these Chain Rule values back into Equation 1:
$$x \left( f'(u) \frac{\partial u}{\partial x} \right) + y \left( f'(u) \frac{\partial u}{\partial y} \right) = n z$$

Factor out the shared derivative term $f'(u)$ from the left side:
$$f'(u) \cdot \left( x \frac{\partial u}{\partial x} + y \frac{\partial u}{\partial y} \right) = n z$$

Since our original setup defined $z = f(u)$, substitute $f(u)$ back in place of $z$:
$$f'(u) \cdot \left( x \frac{\partial u}{\partial x} + y \frac{\partial u}{\partial y} \right) = n \cdot f(u)$$

Divide both sides by $f'(u)$ to isolate the primary operator expression:
$$x \frac{\partial u}{\partial x} + y \frac{\partial u}{\partial y} = n \cdot \frac{f(u)}{f'(u)}$$

Hence, proved.
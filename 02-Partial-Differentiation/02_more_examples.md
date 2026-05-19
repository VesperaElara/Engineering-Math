# Engineering Mathematics: Introduction to Partial Differentiation

Partial differentiation is a powerful mathematical tool used to analyze functions of multiple independent variables. Unlike ordinary differentiation, where a function depends on a single variable, partial differentiation treats all variables as constants except for the one with respect to which the differentiation is being performed.

---

## Core Concept: The Fundamental Rule

When finding the partial derivative of a function $f(x, y, z, \dots)$ with respect to an independent variable $x$, denoted as $\frac{\partial f}{\partial x}$:

* Treat $x$ as the **only** variable.
* Treat $y, z, \dots$ as **pure constants**.
* Apply the standard rules of single-variable calculus (Chain Rule, Product Rule, Quotient Rule).

---

## Worked Examples

### Problem 1: Logarithmic and Trigonometric Composition
Given the function:
$$u = \log(\tan x + \tan y)$$

Find the partial derivative with respect to $x$, denoted as $\frac{\partial u}{\partial x}$.

#### Step-by-Step Solution
Apply the Chain Rule for differentiation, treating $y$ (and consequently $\tan y$) as a constant:

$$\frac{\partial u}{\partial x} = \frac{1}{\tan x + \tan y} \times \frac{\partial}{\partial x}(\tan x + \tan y)$$

Because $\tan y$ is treated as a constant, its derivative with respect to $x$ is $0$, and the derivative of $\tan x$ is $\sec^2 x$:

$$\frac{\partial u}{\partial x} = \frac{1}{\tan x + \tan y} \times (\sec^2 x + 0)$$

Simplify the expression:

$$\frac{\partial u}{\partial x} = \frac{\sec^2 x}{\tan x + \tan y}$$

---

### Problem 2: Variable Base vs. Variable Exponent
Given the function:
$$z = x^y$$

Find the partial derivatives $\frac{\partial z}{\partial x}$ and $\frac{\partial z}{\partial y}$.

#### Case 1: Differentiating with respect to $x$
Treat $y$ as a constant exponent. This matches the standard power rule form $\frac{d}{dx}(x^n) = n x^{n-1}$:

$$\frac{\partial z}{\partial x} = y x^{y-1}$$

#### Case 2: Differentiating with respect to $y$
Treat $x$ as a constant base. This matches the standard exponential rule form $\frac{d}{dy}(a^y) = a^y \log a$:

$$\frac{\partial z}{\partial y} = x^y \log x$$

---

### Problem 3: Exponential Composition
Given the function:
$$z = e^{x+y}$$

Find the partial derivative with respect to $x$, denoted as $\frac{\partial z}{\partial x}$.

#### Step-by-Step Solution
Apply the Chain Rule, treating $y$ as a constant:

$$\frac{\partial z}{\partial x} = e^{x+y} \times \frac{\partial}{\partial x}(x+y)$$

Evaluate the inner derivative:

$$\frac{\partial z}{\partial x} = e^{x+y} \times (1 + 0)$$

Simplify the expression:

$$\frac{\partial z}{\partial x} = e^{x+y}$$

---

### Problem 4: Radical Composition inside a Trigonometric Function
Given the function:
$$u = \cos(\sqrt{x} + \sqrt{y})$$

Find the partial derivative with respect to $x$, denoted as $\frac{\partial u}{\partial x}$.

#### Step-by-Step Solution
Apply the Chain Rule, treating $y$ (and $\sqrt{y}$) as a constant:

$$\frac{\partial u}{\partial x} = -\sin(\sqrt{x} + \sqrt{y}) \times \frac{\partial}{\partial x}(\sqrt{x} + \sqrt{y})$$

Evaluate the inner partial derivative using the rule $\frac{d}{dx}(x^{1/2}) = \frac{1}{2\sqrt{x}}$:

$$\frac{\partial u}{\partial x} = -\sin(\sqrt{x} + \sqrt{y}) \times \left(\frac{1}{2\sqrt{x}} + 0\right)$$

Simplify the final product:

$$\frac{\partial u}{\partial x} = -\frac{1}{2\sqrt{x}} \sin(\sqrt{x} + \sqrt{y})$$

---

### Problem 5: Missing Term Fill-in (Three Variables)
Given the incomplete derivation step for $u = e^{x^2 + y^2 + z^2}$ to find $\frac{\partial u}{\partial z}$:

$$\frac{\partial u}{\partial z} = e^{x^2 + y^2 + z^2} \times \frac{\partial}{\partial z}(x^2 + y^2 + z^2)$$

$$\frac{\partial u}{\partial z} = e^{x^2 + y^2 + z^2} \times (2z + \dots )$$

#### Complete Analysis
Treat $x$ and $y$ as constants. Therefore, $\frac{\partial}{\partial z}(x^2) = 0$ and $\frac{\partial}{\partial z}(y^2) = 0$.

The complete structural step evaluates to:

$$\frac{\partial u}{\partial z} = e^{x^2 + y^2 + z^2} \times (2z + 0 + 0)$$

$$\frac{\partial u}{\partial z} = 2z e^{x^2 + y^2 + z^2}$$

---

### Problem 6: Polynomial Terms
Given the function:
$$u = x^2 y^3 + x^3 y^2$$

Find the partial derivative with respect to $x$, denoted as $\frac{\partial u}{\partial x}$.

#### Step-by-Step Solution
Apply the sum rule and factor out the constant $y$ terms from each differential term:

$$\frac{\partial u}{\partial x} = y^3 \frac{\partial}{\partial x}(x^2) + y^2 \frac{\partial}{\partial x}(x^3)$$

Compute the derivatives using the power rule:

$$\frac{\partial u}{\partial x} = y^3(2x) + y^2(3x^2)$$

Rearrange terms into standard algebraic notation:

$$\frac{\partial u}{\partial x} = 2x y^3 + 3x^2 y^2$$

---

### Problem 7: Product of Independent Functions
Given the function:
$$u = 10^x \cos y$$

Find the partial derivative with respect to $x$, denoted as $\frac{\partial u}{\partial x}$.

#### Step-by-Step Solution
Because $\cos y$ acts entirely as a constant coefficient when differentiating with respect to $x$, pull it out of the derivative:

$$\frac{\partial u}{\partial x} = \cos y \times \frac{\partial}{\partial x}(10^x)$$

Apply the exponential rule $\frac{d}{dx}(a^x) = a^x \log a$:

$$\frac{\partial u}{\partial x} = \cos y \times (10^x \log 10)$$

Reorder the factors:

$$\frac{\partial u}{\partial x} = 10^x \log 10 \cdot \cos y$$

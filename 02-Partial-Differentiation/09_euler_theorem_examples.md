# Engineering Mathematics: Applying Euler's Theorem

Here are the step-by-step solutions for the two practical problems from the lecture notes. These examples showcase how to quickly solve partial differential equations using Euler's Theorem by finding the degree $n$ of a homogeneous function.

---

## Question 1

### Problem Statement
If $u = \frac{x + y}{x^2 + y^2}$, find the value of:
$$x \frac{\partial u}{\partial x} + y \frac{\partial u}{\partial y}$$

### Step-by-Step Solution

Define the function explicitly:
$$f(x, y) = \frac{x + y}{x^2 + y^2}$$

Substitute $x \to xt$ and $y \to yt$ to verify homogeneity and extract the degree:
$$f(xt, yt) = \frac{(xt) + (yt)}{(xt)^2 + (yt)^2}$$

Factor out the scaling parameter $t$ from the numerator and denominator:
$$f(xt, yt) = \frac{t(x + y)}{t^2(x^2 + y^2)}$$

Simplify the powers of $t$ using the exponent rule $\frac{t^1}{t^2} = t^{1-2} = t^{-1}$:
$$f(xt, yt) = t^{-1} \left( \frac{x + y}{x^2 + y^2} \right)$$

Substitute the original definition of $u$ back into the equation:
$$f(xt, yt) = t^{-1} u$$

This proves that $u$ is a homogeneous function with a degree of $n = -1$.

By applying **Euler's Theorem** ($x \frac{\partial u}{\partial x} + y \frac{\partial u}{\partial y} = nu$):
$$x \frac{\partial u}{\partial x} + y \frac{\partial u}{\partial y} = -1 \cdot u = -u$$

### Final Answer
$$x \frac{\partial u}{\partial x} + y \frac{\partial u}{\partial y} = -\frac{x + y}{x^2 + y^2}$$

---

## Question 2

### Problem Statement
If $u = \frac{\sqrt{x} + \sqrt{y}}{x + y}$, find the value of:
$$x \frac{\partial u}{\partial x} + y \frac{\partial u}{\partial y}$$

### Step-by-Step Solution

Define the function explicitly:
$$f(x, y) = \frac{\sqrt{x} + \sqrt{y}}{x + y}$$

Substitute $x \to xt$ and $y \to yt$ into the equation:
$$f(xt, yt) = \frac{\sqrt{xt} + \sqrt{yt}}{(xt) + (yt)}$$

Distribute the square roots in the numerator using $\sqrt{ab} = \sqrt{a}\sqrt{b}$:
$$f(xt, yt) = \frac{\sqrt{t}\sqrt{x} + \sqrt{t}\sqrt{y}}{xt + yt}$$

Factor out $\sqrt{t}$ (which is $t^{1/2}$) in the numerator and $t$ (which is $t^1$) in the denominator:
$$f(xt, yt) = \frac{t^{1/2}(\sqrt{x} + \sqrt{y})}{t^1(x + y)}$$

Simplify the powers of $t$ using the exponent rule $\frac{t^{1/2}}{t^1} = t^{1/2 - 1} = t^{-1/2}$:
$$f(xt, yt) = t^{-1/2} \left( \frac{\sqrt{x} + \sqrt{y}}{x + y} \right)$$

Substitute the original definition of $u$ back into the equation:
$$f(xt, yt) = t^{-1/2} u$$

This confirms that $u$ is a homogeneous function with a degree of $n = -\frac{1}{2}$.

By applying **Euler's Theorem** ($x \frac{\partial u}{\partial x} + y \frac{\partial u}{\partial y} = nu$):
$$x \frac{\partial u}{\partial x} + y \frac{\partial u}{\partial y} = -\frac{1}{2}u$$

### Final Answer
$$x \frac{\partial u}{\partial x} + y \frac{\partial u}{\partial y} = -\frac{1}{2}\left(\frac{\sqrt{x} + \sqrt{y}}{x + y}\right)$$

---

## Question 3

### Problem Statement
If $z = \log(x^2 + y^2) + \frac{x^2 + y^2}{x + y} - 2\log(x + y)$, prove that:
$$x \frac{\partial z}{\partial x} + y \frac{\partial z}{\partial y} = \frac{x^2 + y^2}{x + y}$$

### Step-by-Step Solution

#### Step 1: Simplify the Function using Logarithmic Properties
Before evaluating homogeneity, group the logarithmic terms together using the standard power law $b\log(a) = \log(a^b)$:
$$z = \log(x^2 + y^2) - \log(x + y)^2 + \frac{x^2 + y^2}{x + y}$$

Apply the quotient rule for logarithms, $\log(m) - \log(n) = \log\left(\frac{m}{n}\right)$:
$$z = \log\left( \frac{x^2 + y^2}{(x + y)^2} \right) + \frac{x^2 + y^2}{x + y}$$

To make this expression easier to manage, split it into two independent substitute functions, $u$ and $v$:
$$z = u + v$$

Where:
$$u = \log\left( \frac{x^2 + y^2}{(x + y)^2} \right)$$

$$v = \frac{x^2 + y^2}{x + y}$$

#### Step 2: Analyze Part 1 ($u$) for Homogeneity
Let the inner rational component of the logarithm be a distinct function:
$$f(x, y) = \frac{x^2 + y^2}{(x + y)^2} = \frac{x^2 + y^2}{x^2 + 2xy + y^2}$$

Substitute $x \to xt$ and $y \to yt$ into this inner algebraic component:
$$f(xt, yt) = \frac{(xt)^2 + (yt)^2}{(xt)^2 + 2(xt)(yt) + (yt)^2}$$

Factor out the common parameter $t^2$ from the numerator and denominator:
$$f(xt, yt) = \frac{t^2(x^2 + y^2)}{t^2(x^2 + 2xy + y^2)}$$

Cancel out the $t^2$ terms ($\frac{t^2}{t^2} = t^{2-2} = t^0$):
$$f(xt, yt) = t^0 \left( \frac{x^2 + y^2}{(x + y)^2} \right) = t^0 f(x, y)$$

Thus, the inner function is homogeneous of degree 0. Substitute this back into the full expression for $u$:
$$u(xt, yt) = \log\left( t^0 \cdot \frac{x^2 + y^2}{(x + y)^2} \right)$$

Because the scale factor has a power of $0$, we can rewrite it using log properties ($\log(t^0 \cdot M) = \log(1 \cdot M)$):
$$u(xt, yt) = \log\left( \frac{x^2 + y^2}{(x + y)^2} \right) = u(x, y)$$

This means the overall function $u$ itself behaves as a homogeneous function with a degree of $n_1 = 0$.

Applying **Euler's Theorem** to $u$:
$$x \frac{\partial u}{\partial x} + y \frac{\partial u}{\partial y} = 0 \cdot u = 0 \quad \text{--- (Equation 1)}$$

#### Step 3: Analyze Part 2 ($v$) for Homogeneity
Define the second function explicitly:
$$v(x, y) = \frac{x^2 + y^2}{x + y}$$

Substitute $x \to xt$ and $y \to yt$:
$$v(xt, yt) = \frac{(xt)^2 + (yt)^2}{(xt) + (yt)}$$

Factor out $t^2$ from the numerator and $t^1$ from the denominator:
$$v(xt, yt) = \frac{t^2(x^2 + y^2)}{t^1(x + y)}$$

Simplify the powers of $t$ using the rule $\frac{t^2}{t^1} = t^{2-1} = t^1$:
$$v(xt, yt) = t^1 \left( \frac{x^2 + y^2}{x + y} \right) = t^1 v(x, y)$$

This confirms that $v$ is a homogeneous function with a degree of $n_2 = 1$.

Applying **Euler's Theorem** to $v$:
$$x \frac{\partial v}{\partial x} + y \frac{\partial v}{\partial y} = 1 \cdot v = v \quad \text{--- (Equation 2)}$$

#### Step 4: Combine the Results using Linearity
Because differentiation is a linear operation, we can combine our separate differential operators back into our main target expression:

$$x \frac{\partial z}{\partial x} + y \frac{\partial z}{\partial y} = x \frac{\partial}{\partial x}(u + v) + y \frac{\partial}{\partial y}(u + v)$$

Distribute and re-group the terms into our known sub-equations:
$$x \frac{\partial z}{\partial x} + y \frac{\partial z}{\partial y} = \left( x \frac{\partial u}{\partial x} + y \frac{\partial u}{\partial y} \right) + \left( x \frac{\partial v}{\partial x} + y \frac{\partial v}{\partial y} \right)$$

Substitute Equation 1 and Equation 2 directly into this combined structure:
$$x \frac{\partial z}{\partial x} + y \frac{\partial z}{\partial y} = 0 + v$$

$$x \frac{\partial z}{\partial x} + y \frac{\partial z}{\partial y} = v$$

Substitute the original definition of $v$ back into the finalized solution:
$$x \frac{\partial z}{\partial x} + y \frac{\partial z}{\partial y} = \frac{x^2 + y^2}{x + y} = \text{RHS}$$

Hence, proved.
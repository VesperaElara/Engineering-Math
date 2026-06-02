# Engineering Mathematics: Fundamentals of Partial Differentiation

## 1. Theoretical Core: What is Partial Differentiation?

In standard calculus, a function depends on a single independent variable (e.g., $f(x)$). However, physical and engineering systems typically depend on multiple independent variables simultaneously. 

Partial differentiation is the mathematical operation used to determine the rate of change of a multivariable function with respect to *one* specific variable, while holding all other independent variables strictly constant.

### Mathematical Notation
The symbol $\partial$ (pronounced "curly d" or "partial") distinguishes partial derivatives from ordinary derivatives ($d$).

* $\frac{\partial}{\partial x}$: Differentiate with respect to $x$; treat all other variables (like $y, z$) as constants.
* $\frac{\partial}{\partial y}$: Differentiate with respect to $y$; treat all other variables (like $x, z$) as constants.
* $\frac{\partial}{\partial z}$: Differentiate with respect to $z$; treat all other variables (like $x, y$) as constants.

---

## 2. Core Operational Rules

When executing a partial derivative, standard differentiation rules (Power Rule, Product Rule, Chain Rule) apply, supplemented by one fundamental logical constraint:

> **The Constant Rule of Partial Differentiation:**
> If $u = f(x, y)$, then when computing $\frac{\partial u}{\partial x}$, the variable $y$ behaves exactly like a real number constant (e.g., $5, \pi, k$). Therefore:
> 
> $\frac{\partial}{\partial x}(y) = 0$
> 
> $\frac{\partial}{\partial x}(y \cdot x) = y \cdot \frac{\partial}{\partial x}(x) = y \cdot 1 = y$

---

## 3. Comprehensive Step-by-Step Problem Breakdown

### Problem 1: Polynomial and Trigonometric Combination
Given the function:
$$u = x^3y + y^2x + y \sin x$$

#### Part A: Compute $\frac{\partial u}{\partial x}$
* **Logic:** Treat $y$ as a constant. Apply standard derivative rules to $x$ terms.
* **Step-by-step Expansion:**

    $$\frac{\partial u}{\partial x} = \frac{\partial}{\partial x}(x^3y) + \frac{\partial}{\partial x}(y^2x) + \frac{\partial}{\partial x}(y \sin x)$$
  
    $$\frac{\partial u}{\partial x} = y \cdot \frac{\partial}{\partial x}(x^3) + y^2 \cdot \frac{\partial}{\partial x}(x) + y \cdot \frac{\partial}{\partial x}(\sin x)$$
  
    $$\frac{\partial u}{\partial x} = y \cdot (3x^2) + y^2 \cdot (1) + y \cdot (\cos x)$$
* **Final Simplified Expression:**
    $$\frac{\partial u}{\partial x} = 3x^2y + y^2 + y \cos x$$

#### Part B: Compute $\frac{\partial u}{\partial y}$
* **Logic:** Treat $x$ as a constant. Apply standard derivative rules to $y$ terms.
* **Step-by-step Expansion:**
  
    $$\frac{\partial u}{\partial y} = \frac{\partial}{\partial y}(x^3y) + \frac{\partial}{\partial y}(y^2x) + \frac{\partial}{\partial y}(y \sin x)$$
  
    $$\frac{\partial u}{\partial y} = x^3 \cdot \frac{\partial}{\partial y}(y) + x \cdot \frac{\partial}{\partial y}(y^2) + \sin x \cdot \frac{\partial}{\partial y}(y)$$
  
    $$\frac{\partial u}{\partial y} = x^3 \cdot (1) + x \cdot (2y) + \sin x \cdot (1)$$
* **Final Simplified Expression:**
    $$\frac{\partial u}{\partial y} = x^3 + 2xy + \sin x$$

---

### Problem 2: Higher-Degree Polynomial Analysis
Given the function:
$$u = x^5y^2 + 3x^2y^2 + 5xy$$

#### Compute $\frac{\partial u}{\partial x}$
* **Logic:** Treat $y$ as a constant. Differentiate exclusively with respect to $x$.
* **Step-by-step Expansion:**
  
    $$\frac{\partial u}{\partial x} = \frac{\partial}{\partial x}(x^5y^2) + \frac{\partial}{\partial x}(3x^2y^2) + \frac{\partial}{\partial x}(5xy)$$

    $$\frac{\partial u}{\partial x} = y^2 \cdot \frac{\partial}{\partial x}(x^5) + 3y^2 \cdot \frac{\partial}{\partial x}(x^2) + 5y \cdot \frac{\partial}{\partial x}(x)$$
  
    $$\frac{\partial u}{\partial x} = y^2 \cdot (5x^4) + 3y^2 \cdot (2x) + 5y \cdot (1)$$
* **Final Simplified Expression:**
    $$\frac{\partial u}{\partial x} = 5x^4y^2 + 6xy^2 + 5y$$

---

### Problem 3: Composite Function using Chain Rule (Trigonometric)
Given the function:
$$u = \sin(5x + y)$$

#### Compute $\frac{\partial u}{\partial x}$
* **Logic:** This is a composite function of the form $f(g(x,y))$. We must apply the **Chain Rule**: derivative of the outer function multiplied by the partial derivative of the inner function.
* **Step-by-step Expansion:**
    1. Differentiate the outer function ($\sin \theta \rightarrow \cos \theta$):
       $$\frac{\partial u}{\partial x} = \cos(5x + y) \cdot \frac{\partial}{\partial x}(5x + y)$$
    2. Compute the partial derivative of the inner expression $(5x + y)$ with respect to $x$ (treating $y$ as $0$):
       $$\frac{\partial}{\partial x}(5x + y) = \frac{\partial}{\partial x}(5x) + \frac{\partial}{\partial x}(y) = 5(1) + 0 = 5$$
    3. Synthesize the terms:
       $$\frac{\partial u}{\partial x} = \cos(5x + y) \cdot 5$$
* **Final Simplified Expression:**
    $$\frac{\partial u}{\partial x} = 5\cos(5x + y)$$

---

### Problem 4: Composite Function using Chain Rule (Logarithmic)
Given the function:
$$u = \log(9x + y^2)$$

#### Compute $\frac{\partial u}{\partial y}$
* **Logic:** Apply the Chain Rule. The derivative of the outer logarithmic function is $\frac{\partial}{\partial \theta}(\log \theta) = \frac{1}{\theta}$. Then, multiply by the partial derivative of the inner function with respect to $y$.
* **Step-by-step Expansion:**
    1. Differentiate the outer logarithmic structure:
       $$\frac{\partial u}{\partial y} = \frac{1}{9x + y^2} \cdot \frac{\partial}{\partial y}(9x + y^2)$$
    2. Compute the partial derivative of the inner expression $(9x + y^2)$ with respect to $y$ (treating $9x$ as a constant component, which becomes $0$):
       $$\frac{\partial}{\partial y}(9x + y^2) = \frac{\partial}{\partial y}(9x) + \frac{\partial}{\partial y}(y^2) = 0 + 2y = 2y$$
    3. Synthesize the terms:
       $$\frac{\partial u}{\partial y} = \frac{1}{9x + y^2} \cdot (2y)$$
* **Final Simplified Expression:**
    $$\frac{\partial u}{\partial y} = \frac{2y}{9x + y^2}$$

---

## 4. Algorithmic Checklist for Partial Differentiation

To systematically solve any partial differential equation without error, execute these three steps:

| Step | Action | Mental Framework |
| :--- | :--- | :--- |
| **1** | Identify the Target Variable | Look at the denominator of the operator ($\partial x$, $\partial y$, or $\partial z$). This is your only active variable. |
| **2** | Isolate Foreign Variables | Treat all other variable symbols exactly like integers or coefficients. They do not change. |
| **3** | Apply Standard Calculus Rules | Execute standard differentiation (Power, Product, Quotient, Chain Rule). If a term contains *only* foreign variables, its derivative is unconditionally $0$. |

# Engineering Mathematics: Partial Differentiation Study Notes

## Introduction to Partial Differentiation

When working with a function of multiple variables, a **partial derivative** measures how the function changes when one variable varies while all other variables are treated as constants.

The notation used for partial differentiation is $\partial$ (read as "curly d" or "partial"). 

* $\frac{\partial z}{\partial x}$: Differentiate $z$ with respect to $x$, keeping $y$ constant.
* $\frac{\partial z}{\partial y}$: Differentiate $z$ with respect to $y$, keeping $x$ constant.

---

## Problem 1

### Statement
If $z(x + y) = x^2 + y^2$, prove that:

$$\left( \frac{\partial z}{\partial x} - \frac{\partial z}{\partial y} \right)^2 = 4 \left( 1 - \frac{\partial z}{\partial x} - \frac{\partial z}{\partial y} \right)$$

### Step-by-Step Derivation

First, express $z$ explicitly in terms of $x$ and $y$:

$$z = \frac{x^2 + y^2}{x + y}$$

To find $\frac{\partial z}{\partial x}$, apply the quotient rule $\left( \frac{u}{v} \right)' = \frac{u'v - uv'}{v^2}$ with respect to $x$, treating $y$ as a constant:

$$\frac{\partial z}{\partial x} = \frac{\frac{\partial}{\partial x}(x^2 + y^2) \cdot (x + y) - (x^2 + y^2) \cdot \frac{\partial}{\partial x}(x + y)}{(x + y)^2}$$

$$\frac{\partial z}{\partial x} = \frac{2x(x + y) - (x^2 + y^2)(1)}{(x + y)^2}$$

$$\frac{\partial z}{\partial x} = \frac{2x^2 + 2xy - x^2 - y^2}{(x + y)^2}$$

$$\frac{\partial z}{\partial x} = \frac{x^2 + 2xy - y^2}{(x + y)^2}$$

Similarly, find $\frac{\partial z}{\partial y}$ by applying the quotient rule with respect to $y$, treating $x$ as a constant:

$$\frac{\partial z}{\partial y} = \frac{\frac{\partial}{\partial y}(x^2 + y^2) \cdot (x + y) - (x^2 + y^2) \cdot \frac{\partial}{\partial y}(x + y)}{(x + y)^2}$$

$$\frac{\partial z}{\partial y} = \frac{2y(x + y) - (x^2 + y^2)(1)}{(x + y)^2}$$

$$\frac{\partial z}{\partial y} = \frac{2xy + 2y^2 - x^2 - y^2}{(x + y)^2}$$

$$\frac{\partial z}{\partial y} = \frac{y^2 + 2xy - x^2}{(x + y)^2}$$

Now, calculate the terms for the Left-Hand Side (LHS). Find the difference between the two partial derivatives:

$$\frac{\partial z}{\partial x} - \frac{\partial z}{\partial y} = \frac{(x^2 + 2xy - y^2) - (y^2 + 2xy - x^2)}{(x + y)^2}$$

$$\frac{\partial z}{\partial x} - \frac{\partial z}{\partial y} = \frac{x^2 + 2xy - y^2 - y^2 - 2xy + x^2}{(x + y)^2}$$

$$\frac{\partial z}{\partial x} - \frac{\partial z}{\partial y} = \frac{2x^2 - 2y^2}{(x + y)^2}$$

$$\frac{\partial z}{\partial x} - \frac{\partial z}{\partial y} = \frac{2(x^2 - y^2)}{(x + y)^2}$$

Apply the algebraic identity $x^2 - y^2 = (x - y)(x + y)$ to simplify the expression:

$$\frac{\partial z}{\partial x} - \frac{\partial z}{\partial y} = \frac{2(x - y)(x + y)}{(x + y)^2}$$

$$\frac{\partial z}{\partial x} - \frac{\partial z}{\partial y} = \frac{2(x - y)}{x + y}$$

Square this result to get the final expression for the LHS:

$$\text{LHS} = \left( \frac{\partial z}{\partial x} - \frac{\partial z}{\partial y} \right)^2 = \left[ \frac{2(x - y)}{x + y} \right]^2$$

$$\text{LHS} = \frac{4(x - y)^2}{(x + y)^2}$$

Next, calculate the terms for the Right-Hand Side (RHS). First, find the sum of the two partial derivatives:

$$\frac{\partial z}{\partial x} + \frac{\partial z}{\partial y} = \frac{(x^2 + 2xy - y^2) + (y^2 + 2xy - x^2)}{(x + y)^2}$$

$$\frac{\partial z}{\partial x} + \frac{\partial z}{\partial y} = \frac{4xy}{(x + y)^2}$$

Substitute this sum into the parenthetical term of the RHS:

$$1 - \frac{\partial z}{\partial x} - \frac{\partial z}{\partial y} = 1 - \left( \frac{\partial z}{\partial x} + \frac{\partial z}{\partial y} \right)$$

$$1 - \frac{\partial z}{\partial x} - \frac{\partial z}{\partial y} = 1 - \frac{4xy}{(x + y)^2}$$

Find a common denominator to combine the terms:

$$1 - \frac{\partial z}{\partial x} - \frac{\partial z}{\partial y} = \frac{(x + y)^2 - 4xy}{(x + y)^2}$$

$$1 - \frac{\partial z}{\partial x} - \frac{\partial z}{\partial y} = \frac{(x^2 + 2xy + y^2) - 4xy}{(x + y)^2}$$

$$1 - \frac{\partial z}{\partial x} - \frac{\partial z}{\partial y} = \frac{x^2 - 2xy + y^2}{(x + y)^2}$$

Apply the algebraic identity $x^2 - 2xy + y^2 = (x - y)^2$:

$$1 - \frac{\partial z}{\partial x} - \frac{\partial z}{\partial y} = \frac{(x - y)^2}{(x + y)^2}$$

Multiply by $4$ to find the complete RHS expression:

$$\text{RHS} = 4 \left( 1 - \frac{\partial z}{\partial x} - \frac{\partial z}{\partial y} \right) = \frac{4(x - y)^2}{(x + y)^2}$$

Comparing both sides confirms the proof:

$$\text{LHS} = \text{RHS}$$

---

## Problem 2

### Statement
If $u = \cos(\sqrt{x} + \sqrt{y})$, prove that:

$$x \frac{\partial u}{\partial x} + y \frac{\partial u}{\partial y} + \frac{1}{2}(\sqrt{x} + \sqrt{y}) \sin(\sqrt{x} + \sqrt{y}) = 0$$

### Step-by-Step Derivation

To find $\frac{\partial u}{\partial x}$, apply the chain rule. Differentiate the outer cosine function, then differentiate the inner function $(\sqrt{x} + \sqrt{y})$ with respect to $x$, keeping $y$ constant:

$$\frac{\partial u}{\partial x} = -\sin(\sqrt{x} + \sqrt{y}) \cdot \frac{\partial}{\partial x}(\sqrt{x} + \sqrt{y})$$

$$\frac{\partial u}{\partial x} = -\sin(\sqrt{x} + \sqrt{y}) \cdot \left( \frac{1}{2\sqrt{x}} + 0 \right)$$

$$\frac{\partial u}{\partial x} = -\frac{\sin(\sqrt{x} + \sqrt{y})}{2\sqrt{x}}$$

Multiply this partial derivative by $x$:

$$x \frac{\partial u}{\partial x} = x \cdot \left[ -\frac{\sin(\sqrt{x} + \sqrt{y})}{2\sqrt{x}} \right]$$

Since $\frac{x}{\sqrt{x}} = \sqrt{x}$, the expression simplifies to:

$$x \frac{\partial u}{\partial x} = -\frac{\sqrt{x}}{2} \sin(\sqrt{x} + \sqrt{y})$$

To find $\frac{\partial u}{\partial y}$, apply the chain rule with respect to $y$, keeping $x$ constant:

$$\frac{\partial u}{\partial y} = -\sin(\sqrt{x} + \sqrt{y}) \cdot \frac{\partial}{\partial y}(\sqrt{x} + \sqrt{y})$$

$$\frac{\partial u}{\partial y} = -\sin(\sqrt{x} + \sqrt{y}) \cdot \left( 0 + \frac{1}{2\sqrt{y}} \right)$$

$$\frac{\partial u}{\partial y} = -\frac{\sin(\sqrt{x} + \sqrt{y})}{2\sqrt{y}}$$

Multiply this partial derivative by $y$:

$$y \frac{\partial u}{\partial y} = y \cdot \left[ -\frac{\sin(\sqrt{x} + \sqrt{y})}{2\sqrt{y}} \right]$$

Since $\frac{y}{\sqrt{y}} = \sqrt{y}$, the expression simplifies to:

$$y \frac{\partial u}{\partial y} = -\frac{\sqrt{y}}{2} \sin(\sqrt{x} + \sqrt{y})$$

Substitute these two expressions back into the first two terms of the proof statement:

$$x \frac{\partial u}{\partial x} + y \frac{\partial u}{\partial y} = -\frac{\sqrt{x}}{2} \sin(\sqrt{x} + \sqrt{y}) - \frac{\sqrt{y}}{2} \sin(\sqrt{x} + \sqrt{y})$$

Factor out the common term $-\frac{1}{2}\sin(\sqrt{x} + \sqrt{y})$:

$$x \frac{\partial u}{\partial x} + y \frac{\partial u}{\partial y} = -\frac{1}{2}(\sqrt{x} + \sqrt{y}) \sin(\sqrt{x} + \sqrt{y})$$

Add $\frac{1}{2}(\sqrt{x} + \sqrt{y}) \sin(\sqrt{x} + \sqrt{y})$ to both sides of the equation:

$$x \frac{\partial u}{\partial x} + y \frac{\partial u}{\partial y} + \frac{1}{2}(\sqrt{x} + \sqrt{y}) \sin(\sqrt{x} + \sqrt{y}) = 0$$

This completes the proof.

---

## Problem 3

### Statement
If $u = \log(\tan x + \tan y)$, prove that:

$$\sin 2x \frac{\partial u}{\partial x} + \sin 2y \frac{\partial u}{\partial y} = 2$$

### Step-by-Step Derivation

To find $\frac{\partial u}{\partial x}$, apply the chain rule. Differentiate the outer log function first, then multiply by the derivative of the inner function $(\tan x + \tan y)$ with respect to $x$, keeping $y$ constant:

$$\frac{\partial u}{\partial x} = \frac{1}{\tan x + \tan y} \cdot \frac{\partial}{\partial x}(\tan x + \tan y)$$

$$\frac{\partial u}{\partial x} = \frac{1}{\tan x + \tan y} \cdot (\sec^2 x + 0)$$

$$\frac{\partial u}{\partial x} = \frac{\sec^2 x}{\tan x + \tan y}$$

Multiply this partial derivative by $\sin 2x$:

$$\sin 2x \frac{\partial u}{\partial x} = \sin 2x \cdot \frac{\sec^2 x}{\tan x + \tan y}$$

Apply the trigonometric identities $\sin 2x = 2 \sin x \cos x$ and $\sec^2 x = \frac{1}{\cos^2 x}$ to simplify the numerator:

$$\sin 2x \frac{\partial u}{\partial x} = \frac{2 \sin x \cos x \cdot \frac{1}{\cos^2 x}}{\tan x + \tan y}$$

$$\sin 2x \frac{\partial u}{\partial x} = \frac{\frac{2 \sin x}{\cos x}}{\tan x + \tan y}$$

$$\sin 2x \frac{\partial u}{\partial x} = \frac{2 \tan x}{\tan x + \tan y}$$

Similarly, find $\frac{\partial u}{\partial y}$ by applying the chain rule with respect to $y$, keeping $x$ constant:

$$\frac{\partial u}{\partial y} = \frac{1}{\tan x + \tan y} \cdot \frac{\partial}{\partial y}(\tan x + \tan y)$$

$$\frac{\partial u}{\partial y} = \frac{1}{\tan x + \tan y} \cdot (0 + \sec^2 y)$$

$$\frac{\partial u}{\partial y} = \frac{\sec^2 y}{\tan x + \tan y}$$

Multiply this partial derivative by $\sin 2y$:

$$\sin 2y \frac{\partial u}{\partial y} = \sin 2y \cdot \frac{\sec^2 y}{\tan x + \tan y}$$

Apply the identities $\sin 2y = 2 \sin y \cos y$ and $\sec^2 y = \frac{1}{\cos^2 y}$:

$$\sin 2y \frac{\partial u}{\partial y} = \frac{2 \sin y \cos y \cdot \frac{1}{\cos^2 y}}{\tan x + \tan y}$$

$$\sin 2y \frac{\partial u}{\partial y} = \frac{\frac{2 \sin y}{\cos y}}{\tan x + \tan y}$$

$$\sin 2y \frac{\partial u}{\partial y} = \frac{2 \tan y}{\tan x + \tan y}$$

Now, add the two expressions together to evaluate the Left-Hand Side (LHS):

$$\text{LHS} = \sin 2x \frac{\partial u}{\partial x} + \sin 2y \frac{\partial u}{\partial y}$$

$$\text{LHS} = \frac{2 \tan x}{\tan x + \tan y} + \frac{2 \tan y}{\tan x + \tan y}$$

Combine the terms over the common denominator:

$$\text{LHS} = \frac{2 \tan x + 2 \tan y}{\tan x + \tan y}$$

$$\text{LHS} = \frac{2(\tan x + \tan y)}{\tan x + \tan y}$$

$$\text{LHS} = 2$$

$$\text{LHS} = \text{RHS}$$

This completes the proof.

---

## Problem 4

### Statement
If $u = (1 - 2xy + y^2)^{-1/2}$, prove that:

$$x \frac{\partial u}{\partial x} - y \frac{\partial u}{\partial y} = y^2 u^3$$

### Step-by-Step Derivation

To find $\frac{\partial u}{\partial x}$, apply the power chain rule. Differentiate the expression with respect to the exponent, then differentiate the inner terms with respect to $x$, keeping $y$ constant:

$$\frac{\partial u}{\partial x} = -\frac{1}{2}(1 - 2xy + y^2)^{-3/2} \cdot \frac{\partial}{\partial x}(1 - 2xy + y^2)$$

$$\frac{\partial u}{\partial x} = -\frac{1}{2}(1 - 2xy + y^2)^{-3/2} \cdot (0 - 2y + 0)$$

$$\frac{\partial u}{\partial x} = -\frac{1}{2}(1 - 2xy + y^2)^{-3/2} \cdot (-2y)$$

$$\frac{\partial u}{\partial x} = y(1 - 2xy + y^2)^{-3/2}$$

Multiply this partial derivative by $x$:

$$x \frac{\partial u}{\partial x} = xy(1 - 2xy + y^2)^{-3/2}$$

Similarly, find $\frac{\partial u}{\partial y}$ by differentiating with respect to $y$, keeping $x$ constant:

$$\frac{\partial u}{\partial y} = -\frac{1}{2}(1 - 2xy + y^2)^{-3/2} \cdot \frac{\partial}{\partial y}(1 - 2xy + y^2)$$

$$\frac{\partial u}{\partial y} = -\frac{1}{2}(1 - 2xy + y^2)^{-3/2} \cdot (0 - 2x + 2y)$$

$$\frac{\partial u}{\partial y} = -\frac{1}{2}(1 - 2xy + y^2)^{-3/2} \cdot (-2x + 2y)$$

Factor out $-2$ from the inner derivative term to cancel out the $-\frac{1}{2}$:

$$\frac{\partial u}{\partial y} = -\frac{1}{2}(1 - 2xy + y^2)^{-3/2} \cdot 2(-x + y)$$

$$\frac{\partial u}{\partial y} = (x - y)(1 - 2xy + y^2)^{-3/2}$$

Multiply this partial derivative by $y$:

$$y \frac{\partial u}{\partial y} = y(x - y)(1 - 2xy + y^2)^{-3/2}$$

$$y \frac{\partial u}{\partial y} = (xy - y^2)(1 - 2xy + y^2)^{-3/2}$$

Now, substitute these expressions into the Left-Hand Side (LHS) of the proof statement:

$$\text{LHS} = x \frac{\partial u}{\partial x} - y \frac{\partial u}{\partial y}$$

$$\text{LHS} = xy(1 - 2xy + y^2)^{-3/2} - (xy - y^2)(1 - 2xy + y^2)^{-3/2}$$

Factor out the common term $(1 - 2xy + y^2)^{-3/2}$:

$$\text{LHS} = [xy - (xy - y^2)] \cdot (1 - 2xy + y^2)^{-3/2}$$

$$\text{LHS} = [xy - xy + y^2] \cdot (1 - 2xy + y^2)^{-3/2}$$

$$\text{LHS} = y^2(1 - 2xy + y^2)^{-3/2}$$

From the problem statement, we know that $u = (1 - 2xy + y^2)^{-1/2}$. Raising both sides to the power of $3$ gives:

$$u^3 = \left[ (1 - 2xy + y^2)^{-1/2} \right]^3 = (1 - 2xy + y^2)^{-3/2}$$

Substitute $u^3$ back into the LHS expression:

$$\text{LHS} = y^2 u^3$$

$$\text{LHS} = \text{RHS}$$

This completes the proof.

---

## Problem 5

### Notation Note
In calculus, subscript notation is frequently used as a shorthand for partial derivatives:

$$u_x = \frac{\partial u}{\partial x}$$

$$u_y = \frac{\partial u}{\partial y}$$


### Statement
If $u = \frac{e^{x+y}}{e^x + e^y}$, prove that:

$$u_x + u_y = u$$

### Step-by-Step Derivation

To simplify the math before differentiating, rewrite the numerator using exponent rules:

$$u = \frac{e^x \cdot e^y}{e^x + e^y}$$

To find $u_x$, apply the quotient rule $\left( \frac{f}{g} \right)' = \frac{f'g - fg'}{g^2}$ with respect to $x$, keeping $y$ constant:

$$u_x = \frac{\left[ \frac{\partial}{\partial x}(e^x \cdot e^y) \right] \cdot (e^x + e^y) - (e^x \cdot e^y) \cdot \left[ \frac{\partial}{\partial x}(e^x + e^y) \right]}{(e^x + e^y)^2}$$

$$u_x = \frac{(e^x \cdot e^y) \cdot (e^x + e^y) - (e^x \cdot e^y) \cdot (e^x + 0)}{(e^x + e^y)^2}$$

Factor out the common term $(e^x \cdot e^y)$ from the numerator:

$$u_x = \frac{(e^x \cdot e^y) \cdot [(e^x + e^y) - e^x]}{(e^x + e^y)^2}$$

$$u_x = \frac{(e^x \cdot e^y) \cdot (e^y)}{(e^x + e^y)^2}$$

$$u_x = \frac{e^x \cdot e^{2y}}{(e^x + e^y)^2}$$

Similarly, find $u_y$ by applying the quotient rule with respect to $y$, keeping $x$ constant:

$$u_y = \frac{\left[ \frac{\partial}{\partial y}(e^x \cdot e^y) \right] \cdot (e^x + e^y) - (e^x \cdot e^y) \cdot \left[ \frac{\partial}{\partial y}(e^x + e^y) \right]}{(e^x + e^y)^2}$$

$$u_y = \frac{(e^x \cdot e^y) \cdot (e^x + e^y) - (e^x \cdot e^y) \cdot (0 + e^y)}{(e^x + e^y)^2}$$

Factor out the common term $(e^x \cdot e^y)$ from the numerator:

$$u_y = \frac{(e^x \cdot e^y) \cdot [(e^x + e^y) - e^y]}{(e^x + e^y)^2}$$

$$u_y = \frac{(e^x \cdot e^y) \cdot (e^x)}{(e^x + e^y)^2}$$

$$u_y = \frac{e^{2x} \cdot e^y}{(e^x + e^y)^2}$$

Now, add the two partial derivatives together to evaluate the Left-Hand Side (LHS):

$$\text{LHS} = u_x + u_y$$

$$\text{LHS} = \frac{e^x \cdot e^{2y}}{(e^x + e^y)^2} + \frac{e^{2x} \cdot e^y}{(e^x + e^y)^2}$$

Combine the expressions over the common denominator:

$$\text{LHS} = \frac{e^x \cdot e^{2y} + e^{2x} \cdot e^y}{(e^x + e^y)^2}$$

Factor out the shared term $(e^x \cdot e^y)$ from the numerator:

$$\text{LHS} = \frac{(e^x \cdot e^y) \cdot (e^y + e^x)}{(e^x + e^y)^2}$$

Since $(e^y + e^x) = (e^x + e^y)$, cancel out one power of the denominator:

$$\text{LHS} = \frac{e^x \cdot e^y}{e^x + e^y}$$

Using exponent rules to combine the numerator powers reveals the original function:

$$\text{LHS} = \frac{e^{x+y}}{e^x + e^y}$$

$$\text{LHS} = u$$

$$\text{LHS} = \text{RHS}$$

This completes the proof.

---

## Problem 6

### Statement
If $\theta = t^n e^{-r^2 / 4t}$, find the value of $n$ which will make:

$$\frac{\partial \theta}{\partial t} = \frac{1}{r^2} \frac{\partial}{\partial r} \left( r^2 \frac{\partial \theta}{\partial r} \right)$$

---

### Step-by-Step Derivation

#### Part 1: Finding the Left-Hand Side (LHS)

To find $\frac{\partial \theta}{\partial t}$, apply the product rule $(uv)' = u'v + uv'$ with respect to $t$, treating $r$ as a constant:

$$\frac{\partial \theta}{\partial t} = \frac{\partial}{\partial t}(t^n) \cdot e^{-r^2 / 4t} + t^n \cdot \frac{\partial}{\partial t}\left( e^{-r^2 / 4t} \right)$$

$$\frac{\partial \theta}{\partial t} = n t^{n-1} \cdot e^{-r^2 / 4t} + t^n \cdot \left[ e^{-r^2 / 4t} \cdot \frac{\partial}{\partial t}\left( -\frac{r^2}{4} t^{-1} \right) \right]$$

$$\frac{\partial \theta}{\partial t} = n t^{n-1} e^{-r^2 / 4t} + t^n \cdot \left[ e^{-r^2 / 4t} \cdot \left( \frac{r^2}{4t^2} \right) \right]$$

$$\frac{\partial \theta}{\partial t} = n t^{n-1} e^{-r^2 / 4t} + \frac{r^2}{4} t^{n-2} e^{-r^2 / 4t}$$

Factor out $t^{n-1} e^{-r^2 / 4t}$ to simplify the LHS expression:

$$\text{LHS} = t^{n-1} e^{-r^2 / 4t} \left( n + \frac{r^2}{4t} \right)$$

#### Part 2: Finding the Right-Hand Side (RHS)

First, find the inner partial derivative $\frac{\partial \theta}{\partial r}$ with respect to $r$, treating $t$ as a constant:

$$\frac{\partial \theta}{\partial r} = t^n \cdot \left[ e^{-r^2 / 4t} \cdot \frac{\partial}{\partial r}\left( -\frac{r^2}{4t} \right) \right]$$

$$\frac{\partial \theta}{\partial r} = t^n \cdot \left[ e^{-r^2 / 4t} \cdot \left( -\frac{2r}{4t} \right) \right]$$

$$\frac{\partial \theta}{\partial r} = -\frac{r}{2t} t^n e^{-r^2 / 4t}$$

$$\frac{\partial \theta}{\partial r} = -\frac{r}{2} t^{n-1} e^{-r^2 / 4t}$$

Next, multiply this result by $r^2$:

$$r^2 \frac{\partial \theta}{\partial r} = r^2 \cdot \left( -\frac{r}{2} t^{n-1} e^{-r^2 / 4t} \right)$$

$$r^2 \frac{\partial \theta}{\partial r} = -\frac{r^3}{2} t^{n-1} e^{-r^2 / 4t}$$

Now, differentiate this entire group with respect to $r$ using the product rule:

$$\frac{\partial}{\partial r} \left( r^2 \frac{\partial \theta}{\partial r} \right) = \frac{\partial}{\partial r}\left( -\frac{r^3}{2} \right) \cdot t^{n-1} e^{-r^2 / 4t} + \left( -\frac{r^3}{2} \right) \cdot \frac{\partial}{\partial r}\left( t^{n-1} e^{-r^2 / 4t} \right)$$

$$\frac{\partial}{\partial r} \left( r^2 \frac{\partial \theta}{\partial r} \right) = -\frac{3r^2}{2} t^{n-1} e^{-r^2 / 4t} - \frac{r^3}{2} t^{n-1} \cdot \left[ e^{-r^2 / 4t} \cdot \left( -\frac{2r}{4t} \right) \right]$$

$$\frac{\partial}{\partial r} \left( r^2 \frac{\partial \theta}{\partial r} \right) = -\frac{3r^2}{2} t^{n-1} e^{-r^2 / 4t} + \frac{r^4}{4t} t^{n-1} e^{-r^2 / 4t}$$

Finally, multiply by $\frac{1}{r^2}$ to complete the RHS expression:

$$\text{RHS} = \frac{1}{r^2} \left[ -\frac{3r^2}{2} t^{n-1} e^{-r^2 / 4t} + \frac{r^4}{4t} t^{n-1} e^{-r^2 / 4t} \right]$$

$$\text{RHS} = -\frac{3}{2} t^{n-1} e^{-r^2 / 4t} + \frac{r^2}{4t} t^{n-1} e^{-r^2 / 4t}$$

Factor out $t^{n-1} e^{-r^2 / 4t}$ from the RHS expression:

$$\text{RHS} = t^{n-1} e^{-r^2 / 4t} \left( -\frac{3}{2} + \frac{r^2}{4t} \right)$$

#### Part 3: Equating LHS and RHS to Find $n$

Set the simplified expressions for LHS and RHS equal to one another:

$$t^{n-1} e^{-r^2 / 4t} \left( n + \frac{r^2}{4t} \right) = t^{n-1} e^{-r^2 / 4t} \left( -\frac{3}{2} + \frac{r^2}{4t} \right)$$

Divide both sides by the common non-zero exponential factor $t^{n-1} e^{-r^2 / 4t}$:

$$n + \frac{r^2}{4t} = -\frac{3}{2} + \frac{r^2}{4t}$$

Subtract $\frac{r^2}{4t}$ from both sides to isolate $n$:

$$n = -\frac{3}{2}$$

---


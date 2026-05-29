# Vector Differentiation: Gradient of $r^n$

## 1. Gradient of a Power of Radius

### Name of Concept
Gradient of a Radial Power Function ($r^n$).

### Core Mathematical Formula

$$\nabla r^n = n r^{n-2} \bar{r}$$

### Beginner-Friendly Explanation of Operations

1. **Leveraging a Known Identity:** Instead of calculating the partial derivatives with respect to $x$, $y$, and $z$ from scratch every single time, we can use a previously proven shortcut: the general formula for the gradient of any radial function, $\nabla f(r) = f'(r) \frac{\bar{r}}{r}$.
2. **Applying the Power Rule:** We treat $r^n$ like a standard single-variable calculus term. To find its derivative with respect to $r$, we pull the power $n$ to the front and decrease the exponent by $1$, giving us $n r^{n-1}$.
3. **Combining Exponents (Laws of Indices):** When we combine our derivative with the baseline formula, we end up dividing a base of $r$ by another base of $r$. According to exponent rules:

$$\frac{r^{n-1}}{r^1} = r^{(n-1) - 1} = r^{n-2}$$

This simple subtraction of exponents explains why the final formula features $r^{n-2}$ instead of $r^{n-1}$.

---

## 2. Step-by-Step Proof

### Question
Prove that $\nabla r^n = n r^{n-2} \bar{r}$.

### Step 1: Recall the standard radial gradient identity
We begin with the established identity for the gradient of any scalar function depending solely on distance $r$:

$$\nabla f(r) = f'(r) \frac{\bar{r}}{r}$$

### Step 2: Define the specific function and find its derivative
Assign our specific function to $f(r)$:

$$f(r) = r^n$$

Differentiate $f(r)$ with respect to $r$ using the standard calculus power rule:

$$f'(r) = n r^{n-1}$$

### Step 3: Substitute the derivative back into the identity
Replace $f'(r)$ in our primary equation with the calculated power rule expression:

$$\nabla r^n = \left( n r^{n-1} \right) \frac{\bar{r}}{r}$$

### Step 4: Group the scalar components together
Rearrange the terms to group all scalar operations involving $r$ away from the position vector $\bar{r}$:

$$\nabla r^n = \left( n \cdot \frac{r^{n-1}}{r} \right) \bar{r}$$

### Step 5: Simplify the exponents to reach the final form
Apply the laws of indices ($\frac{x^a}{x^b} = x^{a-b}$) to simplify the fraction:

$$\nabla r^n = \left( n \cdot r^{(n-1)-1} \right) \bar{r}$$

$$\nabla r^n = n r^{n-2} \bar{r}$$
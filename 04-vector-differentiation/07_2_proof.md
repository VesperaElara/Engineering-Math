# Vector Differentiation: Gradient of a Function of Radius

## 1. Gradient of a Radial Scalar Function

### Name of Concept
Gradient of a Function of Distance ($r$), or the Vector Chain Rule for Spherical Symmetry.

### Core Mathematical Formula

$$\nabla f(r) = f'(r) \frac{\bar{r}}{r}$$

### Beginner-Friendly Explanation of Operations

1. **The Position Vector ($\bar{r}$):** This represents a vector pointing from the origin $(0,0,0)$ to any point space $(x, y, z)$. It is written as $\bar{r} = x\bar{i} + y\bar{j} + z\bar{k}$.
2. **The Magnitude ($r$):** The scalar letter $r$ (without the bar) represents the straight-line distance from the origin to that point. It is computed using the 3D Pythagorean theorem: $r = \sqrt{x^2 + y^2 + z^2}$.
3. **The Single-Variable Derivative ($f'(r)$):** Since $f(r)$ depends *only* on the distance $r$ and not directly on individual $x, y, z$ coordinates, $f'(r)$ is just the standard derivative of that function with respect to $r$ (like differentiating $x^2$ to get $2x$).
4. **The Unit Position Vector $\left(\frac{\bar{r}}{r}\right)$:** This is a vector of length 1 pointing directly outward from the origin. The formula shows that the gradient of any radial function points straight outward, and its strength depends on the regular derivative $f'(r)$.



---

## 2. Analogous Example (The Chain Rule)

To understand why the derivative splits into two parts, remember the standard calculus Chain Rule. 

If you differentiate a nested function like $\sin(x^2 + 1)$ with respect to $x$:
* First, you differentiate the outer function: $\sin(\dots) \rightarrow \cos(\dots)$
* Second, you multiply by the partial derivative of the inner function: $\frac{\partial}{\partial x}(x^2 + 1)$

$$\frac{\partial}{\partial x} \sin(x^2 + 1) = \cos(x^2 + 1) \cdot 2x$$

We use this exact same logic for $\frac{\partial}{\partial x} f(r)$. Because $r$ depends on $x$, you take the derivative of the outer function $f(r)$ with respect to $r$ (which is $f'(r)$), then multiply it by the partial derivative of the inside variable with respect to $x$ (which is $\frac{\partial r}{\partial x}$).

---

## 3. Step-by-Step Proof

### Question
Prove that $\nabla f(r) = f'(r) \frac{\bar{r}}{r}$.

### Step 1: Establish the relationship between coordinates and radius
Define the position vector $\bar{r}$ and its scalar magnitude $r$:

$$\bar{r} = x\bar{i} + y\bar{j} + z\bar{k}$$

$$r = \sqrt{x^2 + y^2 + z^2}$$

Square both sides to eliminate the radical sign:

$$r^2 = x^2 + y^2 + z^2$$

### Step 2: Differentiate the radius relationship partially with respect to $x$
Differentiate both sides with respect to $x$, treating $y$ and $z$ as constants. Remember to use the chain rule on the left side ($r^2 \rightarrow 2r \cdot \frac{\partial r}{\partial x}$):

$$2r \frac{\partial r}{\partial x} = 2x + 0 + 0$$

$$2r \frac{\partial r}{\partial x} = 2x$$

Divide both sides by $2r$ to isolate the partial derivative:

$$\frac{\partial r}{\partial x} = \frac{x}{r}$$

### Step 3: Find the corresponding derivatives for $y$ and $z$
By following the exact same algebraic steps for the other axes, we find symmetric results:

$$\frac{\partial r}{\partial y} = \frac{y}{r}$$

$$\frac{\partial r}{\partial z} = \frac{z}{r}$$

### Step 4: Apply the vector gradient operator to $f(r)$
The general definition for the gradient of any scalar field is:

$$\nabla \phi = \bar{i} \frac{\partial \phi}{\partial x} + \bar{j} \frac{\partial \phi}{\partial y} + \bar{k} \frac{\partial \phi}{\partial z}$$

Substitute $\phi = f(r)$ into the operator equation:

$$\nabla f(r) = \bar{i} \frac{\partial f(r)}{\partial x} + \bar{j} \frac{\partial f(r)}{\partial y} + \bar{k} \frac{\partial f(r)}{\partial z}$$

### Step 5: Expand each component using the chain rule
Apply the chain rule to each partial derivative term:

$$\frac{\partial f(r)}{\partial x} = f'(r) \frac{\partial r}{\partial x}$$

$$\frac{\partial f(r)}{\partial y} = f'(r) \frac{\partial r}{\partial y}$$

$$\frac{\partial f(r)}{\partial z} = f'(r) \frac{\partial r}{\partial z}$$

Substitute these back into our full gradient expression:

$$\nabla f(r) = \bar{i} \left[ f'(r) \frac{\partial r}{\partial x} \right] + \bar{j} \left[ f'(r) \frac{\partial r}{\partial y} \right] + \bar{k} \left[ f'(r) \frac{\partial r}{\partial z} \right]$$

### Step 6: Substitute the calculated components and simplify
Substitute the specific values for $\frac{\partial r}{\partial x}$, $\frac{\partial r}{\partial y}$, and $\frac{\partial r}{\partial z}$ found in Step 2 and Step 3:

$$\nabla f(r) = \bar{i} \left[ f'(r) \frac{x}{r} \right] + \bar{j} \left[ f'(r) \frac{y}{r} \right] + \bar{k} \left[ f'(r) \frac{z}{r} \right]$$

Factor out the common scalar term $f'(r)$ and the common denominator $r$:

$$\nabla f(r) = \frac{f'(r)}{r} \left( x\bar{i} + y\bar{j} + z\bar{k} \right)$$

### Step 7: Substitute the original position vector back in
Since $\bar{r} = x\bar{i} + y\bar{j} + z\bar{k}$, replace the parenthesis term with $\bar{r}$:

$$\nabla f(r) = \frac{f'(r)}{r} \bar{r}$$

Rearrange the terms to match the target layout:

$$\nabla f(r) = f'(r) \frac{\bar{r}}{r}$$
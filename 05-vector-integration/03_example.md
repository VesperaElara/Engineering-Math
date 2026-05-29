# Vector Integration: Evaluating a Line Integral Along a Curved Path

## 1. Line Integral Parameterization Using an Existing Coordinate

### Name of Concept
Line Integration along an Intersecting Space Curve parameterized by a single coordinate variable ($x$).

### Core Mathematical Formulas

The expansion of the vector line integral into its scalar coordinate components is:

$$\int_C \bar{F} \cdot d\bar{r} = \int_C (f_1 \, dx + f_2 \, dy + f_3 \, dz)$$

The given constraint equations of the space curve path $C$ are:

$$y = \frac{x^2}{4}, \quad z = \frac{3x^3}{8}$$

### Beginner-Friendly Explanation of Operations

1. **Choosing $x$ as the Parameter:** In the previous problem, we introduced a completely separate variable $t$. However, if the path constraints already express $y$ and $z$ directly as functions of $x$, we can bypass $t$ entirely. We choose $x$ itself as our primary parameter.
2. **Expressing the Dependent Variables:** Because $y$ and $z$ are bound to the behavior of $x$ along this curved track, we rearrange the given path equations to isolate $y$ and $z$:
   * $y$ becomes $\frac{x^2}{4}$
   * $z$ becomes $\frac{3x^3}{8}$
3. **Converting the Differentials ($dy$ and $dz$):** We differentiate our expressions for $y$ and $z$ with respect to $x$ using standard power rules to establish equations for the differential steps $dy$ and $dz$ in terms of $dx$:
   * Differentiating $y = \frac{1}{4}x^2$ yields $\frac{dy}{dx} = \frac{2x}{4} = \frac{x}{2}$, meaning $dy = \frac{x}{2} \, dx$.
   * Differentiating $z = \frac{3}{8}x^3$ yields $\frac{dz}{dx} = \frac{9x^2}{8}$, meaning $dz = \frac{9x^2}{8} \, dx$.
4. **Simplification to a Single-Variable Integral:** By substituting these equations into our line integral layout, every instance of $y$, $z$, $dy$, and $dz$ is replaced with an equivalent expression containing only $x$ and $dx$. This reduces the problem to a standard definite single-variable calculus integral from the starting limit $x=0$ to the ending limit $x=2$.

---

## 2. Step-by-Step Problem Solution

### Question
Evaluate the line integral $\int_C \bar{F} \cdot d\bar{r}$ for the vector field $\bar{F} = 3x^2 \bar{i} + (2xz - y)\bar{j} + z\bar{k}$ along the curve defined by $x^2 = 4y$ and $3x^3 = 8z$ from $x = 0$ to $x = 2$.

### Step 1: Identify components and map path constraints
Extract the components of the vector field $\bar{F}$:

$$f_1 = 3x^2$$

$$f_2 = 2xz - y$$

$$f_3 = z$$

Isolate $y$ and $z$ from the given curve boundary equations:

$$y = \frac{x^2}{4}$$

$$z = \frac{3x^3}{8}$$

### Step 2: Calculate the coordinate differentials in terms of $dx$
Take the derivative of each isolated coordinate equation with respect to $x$:

$$\frac{dy}{dx} = \frac{2x}{4} = \frac{x}{2} \implies dy = \frac{x}{2} \, dx$$

$$\frac{dz}{dx} = \frac{3(3x^2)}{8} = \frac{9x^2}{8} \implies dz = \frac{9x^2}{8} \, dx$$

### Step 3: Rewrite vector components purely in terms of $x$
Substitute the expressions for $y$ and $z$ into the components $f_2$ and $f_3$:

$$f_1 = 3x^2$$

$$f_2 = 2x\left(\frac{3x^3}{8}\right) - \left(\frac{x^2}{4}\right) = \frac{6x^4}{8} - \frac{x^2}{4} = \frac{3x^4}{4} - \frac{x^2}{4}$$

$$f_3 = \frac{3x^3}{8}$$

### Step 4: Substitute all expressions into the line integral formula
Assemble the total scalar integral component structure:

$$\int_C \bar{F} \cdot d\bar{r} = \int_{0}^{2} \left[ (f_1) \, dx + (f_2) \, dy + (f_3) \, dz \right]$$

Substitute the component functions and their corresponding differentials:

$$\int_C \bar{F} \cdot d\bar{r} = \int_{0}^{2} \left[ \left(3x^2\right)dx + \left(\frac{3x^4}{4} - \frac{x^2}{4}\right)\left(\frac{x}{2} \, dx\right) + \left(\frac{3x^3}{8}\right)\left(\frac{9x^2}{8} \, dx\right) \right]$$

### Step 5: Expand and distribute the terms inside the brackets
Multiply out the terms within each individual component group:

$$\int_C \bar{F} \cdot d\bar{r} = \int_{0}^{2} \left[ 3x^2 \, dx + \left(\frac{3x^5}{8} - \frac{x^3}{8}\right)dx + \left(\frac{27x^5}{64}\right)dx \right]$$

### Step 6: Combine like algebraic terms over a common denominator
Group all terms under a single factor of $dx$:

$$\int_C \bar{F} \cdot d\bar{r} = \int_{0}^{2} \left[ 3x^2 - \frac{x^3}{8} + \left(\frac{3x^5}{8} + \frac{27x^5}{64}\right) \right] dx$$

Find a common denominator of $64$ for the $x^5$ terms to merge them:

$$\frac{3x^5}{8} = \frac{3 \cdot 8 \cdot x^5}{8 \cdot 8} = \frac{24x^5}{64}$$

$$\frac{24x^5}{64} + \frac{27x^5}{64} = \frac{51x^5}{64}$$

Substitute this simplified term back into the complete integrand:

$$\int_C \bar{F} \cdot d\bar{r} = \int_{0}^{2} \left[ 3x^2 - \frac{x^3}{8} + \frac{51x^5}{64} \right] dx$$

### Step 7: Compute the definite single-variable integral
Apply standard calculus integration rules ($\int x^n \, dx = \frac{x^{n+1}}{n+1}$) component by component:

$$\int_C \bar{F} \cdot d\bar{r} = \left[ 3\left(\frac{x^3}{3}\right) - \frac{1}{8}\left(\frac{x^4}{4}\right) + \frac{51}{64}\left(\frac{x^6}{66}\right) \right]_{0}^{2}$$

Simplify the constant fraction coefficients before substituting values:

$$\int_C \bar{F} \cdot d\bar{r} = \left[ x^3 - \frac{x^4}{32} + \frac{51x^6}{384} \right]_{0}^{2}$$

Reduce the fraction $\frac{51}{384}$ by dividing the numerator and denominator by 3:

$$\frac{51 \div 3}{384 \div 3} = \frac{17}{128}$$

$$\int_C \bar{F} \cdot d\bar{r} = \left[ x^3 - \frac{x^4}{32} + \frac{17x^6}{128} \right]_{0}^{2}$$

### Step 8: Evaluate the limits at $x=2$ and $x=0$
Substitute the upper limit ($2$) and subtract the lower limit ($0$):

$$\int_C \bar{F} \cdot d\bar{r} = \left( (2)^3 - \frac{(2)^4}{32} + \frac{17(2)^6}{128} \right) - 0$$

Calculate the powers of 2:

$$(2)^3 = 8, \quad (2)^4 = 16, \quad (2)^6 = 64$$

Substitute these values back into the numeric expression:

$$\int_C \bar{F} \cdot d\bar{r} = 8 - \frac{16}{32} + \frac{17(64)}{128}$$

Simplify each fraction term:

$$\frac{16}{32} = \frac{1}{2}$$

$$\frac{64}{128} = \frac{1}{2} \implies \frac{17(64)}{128} = \frac{17}{2}$$

Combine the remaining fractions over their shared denominator:

$$\int_C \bar{F} \cdot d\bar{r} = 8 - \frac{1}{2} + \frac{17}{2}$$

$$\int_C \bar{F} \cdot d\bar{r} = 8 + \frac{16}{2}$$

$$\int_C \bar{F} \cdot d\bar{r} = 8 + 8 = 16$$
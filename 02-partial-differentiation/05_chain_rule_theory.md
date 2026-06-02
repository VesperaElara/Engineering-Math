# Engineering Mathematics: Total Derivatives & The Chain Rule

## Concept Overview: Functions of Independent Variables

Up until now, you have been differentiating functions where the variables are completely independent of each other.

However, in many engineering scenarios, the variables themselves depend on other underlying variables. This is where the **Chain Rule for functions of multiple variables** comes into play. 

---

## The Tree Diagram Breakdown

When variables are nested inside other variables, it can be easy to lose track of what to hold constant and what to differentiate. The **Tree Diagram** (shown on the right side of your teacher's board) is a perfect visual roadmap to prevent mistakes.


### How to Build and Read the Tree Diagram
1. **The Top Level (Dependent Variable):** Place your main function variable ($z$) at the very top.
2. **The Intermediate Level:** Look at what variables directly make up $z$. Since $z = f(x, y)$, draw branches down from $z$ to both $x$ and $y$.
3. **The Bottom Level (Independent Variables):** Look at what variables control $x$ and $y$. Since both $x = \phi(u, v)$ and $y = \psi(u, v)$, draw branches from both $x$ and $y$ down to $u$ and $v$.

```text
              z               <-- Top Level: Main Dependent Function
             / \
            /   \             
           /     \            
          x       y           <-- Intermediate Level: Function Arguments
         / \     / \          
        /   \   /   \         
       u     v u     v        <-- Bottom Level: Ultimate Independent Variables
```

### The Core Rule: "Trace All Paths"
To find a total partial derivative like $\frac{\partial z}{\partial u}$, you must **trace every single path** that leads from the top variable $z$ down to the bottom variable $u$:
* **Path 1 (Through $x$):** Travel from $z \to x$, then from $x \to u$. Multiply the derivatives along this path: $\frac{\partial z}{\partial x} \cdot \frac{\partial x}{\partial u}$.
* **Path 2 (Through $y$):** Travel from $z \to y$, then from $y \to u$. Multiply the derivatives along this path: $\frac{\partial z}{\partial y} \cdot \frac{\partial y}{\partial u}$.

Finally, **add the results of all individual paths together**.

---

## Formula Derivation via the Tree Roadmap

By following the roadmap rules above, we can directly construct the two main equations on the board:

### 1. Differentiating with respect to $u$
$$\frac{\partial z}{\partial u} = \left( \frac{\partial z}{\partial x} \cdot \frac{\partial x}{\partial u} \right) + \left( \frac{\partial z}{\partial y} \cdot \frac{\partial y}{\partial u} \right)$$

### 2. Differentiating with respect to $v$
$$\frac{\partial z}{\partial v} = \left( \frac{\partial z}{\partial x} \cdot \frac{\partial x}{\partial v} \right) + \left( \frac{\partial z}{\partial y} \cdot \frac{\partial y}{\partial v} \right)$$

> **Why are all the symbols partials ($\partial$)?** > Notice that every intermediate and bottom variable splits into multiple choices. Because $z$ depends on more than one variable ($x, y$), its derivatives are partial. Because $x$ and $y$ both depend on more than one variable ($u, v$), their derivatives are also partials.

----
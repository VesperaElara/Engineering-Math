# Vector Integration: Stokes' Theorem

## 1. Stokes' Theorem

### Name of Concept
Stokes' Theorem (Converting a 3D Line Integral to a Surface Integral).

### Core Mathematical Formulas

$$\oint_C \bar{F} \cdot d\bar{r} = \iint_S (\nabla \times \bar{F}) \cdot \hat{n} \, dS$$

The unit outward normal vector $\hat{n}$ (or $\bar{N}$) for a given surface boundary $\phi(x,y,z) = 0$ is found using:

$$\hat{n} = \frac{\nabla \phi}{|\nabla \phi|}$$

Standard standard coordinate plane standard unit normal vector assignments:

$$\hat{n} = \begin{cases} \text{xy-plane} & \bar{k} \\ \text{yz-plane} & \bar{i} \\ \text{xz-plane} & \bar{j} \end{cases}$$

### Beginner-Friendly Explanation of Operations



1. **What is Stokes' Theorem?** Think of Stokes' Theorem as a 3D extension of Green's Theorem. Instead of restricting yourself to a flat 2D region, imagine a flexible curved open mesh or surface $S$ (like an open butterfly net or a deflated balloon) whose rim forms a solid closed loop boundary curve $C$. Stokes' Theorem states that walking along the outer rim counting the work done by a force field ($\oint_C \bar{F} \cdot d\bar{r}$) yields the exact same numeric total as sum-collecting the tiny rotational churning tendencies ($\nabla \times \bar{F}$) piercing through every open microscopic pore of the net surface area ($\iint_S$).
2. **The Role of the Curl ($\nabla \times \bar{F}$):** Instead of using the raw force components directly inside the double surface integral, you first evaluate the curl matrix determinant to measure the local swirling components of the vector field.
3. **The Outward Normal Vector ($\hat{n}$):** To balance the component projection over an active surface area patch $dS$, we multiply by a unit directional vector $\hat{n}$ that points completely perpendicular (normal) to the surface at that exact point. If your surface happens to be completely flat and sitting square on one of our standard coordinate planes, picking $\hat{n}$ is simple:
   * If the surface sits entirely on the floor (**xy-plane**), the perpendicular direction points straight up along the z-axis, making $\hat{n} = \bar{k}$.
   * If the surface stands flat against the side wall (**yz-plane**), the perpendicular direction points out along the x-axis, making $\hat{n} = \bar{i}$.
   * If the surface stands flat against the back wall (**xz-plane**), the perpendicular direction points out along the y-axis, making $\hat{n} = \bar{j}$.
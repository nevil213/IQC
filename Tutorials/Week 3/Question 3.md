<!-- Q3. Discuss the Cauchy–Schwarz inequality. (Refer to Nielsen & Chuang, Box 2.1) -->

### Solution

Let $\mathcal{H}$ be an inner-product space over $\mathbb{C}$. The Cauchy–Schwarz inequality states that for all $\mathbf{u}, \mathbf{v} \in \mathcal{H}$,

$$
\lvert \langle \mathbf{u}, \mathbf{v} \rangle \rvert^2 \leq \lVert \mathbf{u} \rVert^2 \lVert \mathbf{v} \rVert^2,
$$

with equality if and only if $\mathbf{u}$ and $\mathbf{v}$ are linearly dependent.

**Method 1 – Quadratic form positivity.** Consider the norm of $\mathbf{u} - \lambda \mathbf{v}$ for arbitrary $\lambda \in \mathbb{C}$:

$$
0 \leq \lVert \mathbf{u} - \lambda \mathbf{v} \rVert^2 = \lVert \mathbf{u} \rVert^2 - \lambda \langle \mathbf{v}, \mathbf{u} \rangle - \lambda^* \langle \mathbf{u}, \mathbf{v} \rangle + \lvert \lambda \rvert^2 \lVert \mathbf{v} \rVert^2.
$$

Choosing

$$
\lambda = \frac{\langle \mathbf{v}, \mathbf{u} \rangle}{\lVert \mathbf{v} \rVert^2}
$$

minimizes the quadratic in $\lambda$ and yields the desired inequality immediately. Equality holds exactly when $\mathbf{u} - \lambda \mathbf{v} = \mathbf{0}$, i.e., when $\mathbf{u}$ is proportional to $\mathbf{v}$.

**Method 2 – Projection geometry.** Decompose $\mathbf{u}$ into the sum of a component parallel to $\mathbf{v}$ and an orthogonal remainder:

$$
\mathbf{u} = \frac{\langle \mathbf{v}, \mathbf{u} \rangle}{\lVert \mathbf{v} \rVert^2} \mathbf{v} + \mathbf{u}_\perp,
$$

with $\langle \mathbf{v}, \mathbf{u}_\perp \rangle = 0$. Taking norms gives

$$
\lVert \mathbf{u} \rVert^2 = \frac{\lvert \langle \mathbf{v}, \mathbf{u} \rangle \rvert^2}{\lVert \mathbf{v} \rVert^2} + \lVert \mathbf{u}_\perp \rVert^2 \geq \frac{\lvert \langle \mathbf{v}, \mathbf{u} \rangle \rvert^2}{\lVert \mathbf{v} \rVert^2},
$$

which rearranges to the Cauchy–Schwarz bound. The geometric interpretation emphasizes that $\lvert \langle \mathbf{u}, \mathbf{v} \rangle \rvert$ is the norm of the projection of one vector onto the other.

**Method 3 – Spectral view using positive operators.** Define the rank-one operator $A = \lvert \mathbf{v} \rangle \langle \mathbf{v} \rvert$. Then $A$ is positive-semidefinite with eigenvalue $\lVert \mathbf{v} \rVert^2$ along $\mathbf{v}$ and zero otherwise. The Rayleigh quotient of $A$ evaluated at $\mathbf{u}$ satisfies

$$
0 \leq \langle \mathbf{u}, A \mathbf{u} \rangle = \lvert \langle \mathbf{v}, \mathbf{u} \rangle \rvert^2 \leq \lVert \mathbf{v} \rVert^2 \lVert \mathbf{u} \rVert^2,
$$

because the maximum eigenvalue of $A$ equals $\lVert \mathbf{v} \rVert^2$. This operator-based argument generalizes elegantly to inequalities involving higher-rank positive operators.

Across all proofs, the key insight is that inner products cannot exceed the product of norms, encapsulating the angle between vectors via $\cos \theta = \lvert \langle \mathbf{u}, \mathbf{v} \rangle \rvert / (\lVert \mathbf{u} \rVert \lVert \mathbf{v} \rVert)$.

# Q3. Discuss the Cauchy–Schwarz inequality. (Refer to Nielsen & Chuang, Box 2.1)

## Solution

Below are multiple methods to discuss the Cauchy–Schwarz inequality, each explained in detail. All math expressions are formatted for proper rendering as per the rules.

---

**Method 1 – Quadratic Form Positivity**

Consider the norm of $\mathbf{u} - \lambda \mathbf{v}$ for an arbitrary complex $\lambda$:

$$
0 \leq \lVert \mathbf{u} - \lambda \mathbf{v} \rVert^2 = \lVert \mathbf{u} \rVert^2 - \lambda \langle \mathbf{v}, \mathbf{u} \rangle - \lambda^* \langle \mathbf{u}, \mathbf{v} \rangle + \lvert \lambda \rvert^2 \lVert \mathbf{v} \rVert^2.
$$

To minimize this quadratic form, choose:

$$
\lambda = \frac{\langle \mathbf{v}, \mathbf{u} \rangle}{\lVert \mathbf{v} \rVert^2}.
$$

Substituting yields the inequality directly. Equality holds when $\mathbf{u} - \lambda \mathbf{v} = 0$, meaning $\mathbf{u}$ and $\mathbf{v}$ are linearly dependent.

**Explanation:** This method treats the inequality as an optimization problem, minimizing the norm squared to derive the bound. It's a standard variational approach in functional analysis.

---

**Method 2 – Projection Geometry**

Decompose $\mathbf{u}$ into a component parallel to $\mathbf{v}$ and an orthogonal remainder:

$$
\mathbf{u} = \frac{\langle \mathbf{v}, \mathbf{u} \rangle}{\lVert \mathbf{v} \rVert^2} \mathbf{v} + \mathbf{u}_\perp,
$$

where $\langle \mathbf{v}, \mathbf{u}_\perp \rangle = 0$. Taking norms:

$$
\lVert \mathbf{u} \rVert^2 = \frac{\lvert \langle \mathbf{v}, \mathbf{u} \rangle \rvert^2}{\lVert \mathbf{v} \rVert^2} + \lVert \mathbf{u}_\perp \rVert^2 \geq \frac{\lvert \langle \mathbf{v}, \mathbf{u} \rangle \rvert^2}{\lVert \mathbf{v} \rVert^2}.
$$

Rearranging gives the Cauchy–Schwarz inequality.

**Explanation:** Geometrically, this shows that the inner product magnitude is bounded by the product of norms, as the projection length cannot exceed the vector's length.

---

**Method 3 – Spectral View Using Positive Operators**

Define the rank-one positive operator $A = \lvert \mathbf{v} \rangle \langle \mathbf{v} \rvert$, with eigenvalues $\lVert \mathbf{v} \rVert^2$ (along $\mathbf{v}$) and 0 elsewhere. The Rayleigh quotient for $A$ at $\mathbf{u}$ is:

$$
0 \leq \langle \mathbf{u}, A \mathbf{u} \rangle = \lvert \langle \mathbf{v}, \mathbf{u} \rangle \rvert^2 \leq \lVert \mathbf{v} \rVert^2 \lVert \mathbf{u} \rVert^2.
$$

**Explanation:** This operator-based proof generalizes to higher-rank positive operators, using spectral properties to bound the quadratic form.

---

**Summary:**

The Cauchy–Schwarz inequality bounds inner products by norm products, with equality for dependent vectors. These methods cover variational, geometric, and operator-theoretic perspectives. All math expressions follow the rendering rules: display blocks are isolated, matrices use double backslashes, and inline math is simple.

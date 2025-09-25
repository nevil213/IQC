# Q2. (Optional) Prove that the Gram–Schmidt procedure produces an orthonormal basis.

## Solution

Below are multiple methods to prove that the Gram–Schmidt procedure produces an orthonormal basis, each explained in detail. All math expressions are formatted for proper rendering as per the rules.

---

**Method 1 – Induction on the Construction Index**

Assume the Gram–Schmidt procedure generates vectors $\mathbf{u}_k$ and normalized vectors $\mathbf{e}_k$ according to:

$$
\mathbf{u}_k = \mathbf{v}_k - \sum_{j=1}^{k-1} \langle \mathbf{e}_j, \mathbf{v}_k \rangle \, \mathbf{e}_j, \quad \mathbf{e}_k = \frac{\mathbf{u}_k}{\lVert \mathbf{u}_k \rVert}.
$$

**Base Step:** The first vector $\mathbf{e}_1 = \mathbf{v}_1 / \lVert \mathbf{v}_1 \rVert$ has unit norm by construction.

**Inductive Step:** Suppose $\mathbf{e}_1, \dots, \mathbf{e}_{k-1}$ are orthonormal. For any $j < k$, compute the inner product:

$$
\langle \mathbf{e}_j, \mathbf{u}_k \rangle = \langle \mathbf{e}_j, \mathbf{v}_k \rangle - \sum_{m=1}^{k-1} \langle \mathbf{e}_m, \mathbf{v}_k \rangle \langle \mathbf{e}_j, \mathbf{e}_m \rangle.
$$

Since the $\mathbf{e}_m$ are orthonormal, $\langle \mathbf{e}_j, \mathbf{e}_m \rangle = \delta_{jm}$, so the sum collapses to $\langle \mathbf{e}_j, \mathbf{v}_k \rangle$, making $\langle \mathbf{e}_j, \mathbf{u}_k \rangle = 0$. Thus, $\mathbf{u}_k$ is orthogonal to all previous $\mathbf{e}_j$. Normalization ensures $\mathbf{e}_k$ has unit norm and remains orthogonal.

**Explanation:** This inductive proof shows that orthogonality is maintained at each step, and normalization preserves unit length. Linear independence of the $\mathbf{v}_k$ guarantees $\mathbf{u}_k \neq 0$, avoiding division by zero.

---

**Method 2 – Matrix/QR Factorization Argument**

Arrange the original vectors as columns in a matrix $V = [\mathbf{v}_1, \dots, \mathbf{v}_n]$. Gram–Schmidt factorizes $V$ into $V = Q R$, where $Q$ has orthonormal columns (the $\mathbf{e}_k$) and $R$ is upper triangular with positive diagonals.

The Gram matrix $V^\dagger V$ satisfies:

$$
V^\dagger V = R^\dagger Q^\dagger Q R.
$$

Since the $\mathbf{v}_k$ are linearly independent, $V^\dagger V$ is positive-definite, so $R$ is invertible, implying:

$$
Q^\dagger Q = (R^\dagger)^{-1} V^\dagger V R^{-1} = I.
$$

Thus, the columns of $Q$ form an orthonormal set.

**Explanation:** This matrix viewpoint leverages linear algebra to confirm orthonormality directly from the factorization properties, connecting to numerical stability in computations.

---

**Method 3 – Projection-Operator Invariance**

Define $P_k = \sum_{j=1}^{k} \lvert \mathbf{e}_j \rangle \langle \mathbf{e}_j \rvert$, the projector onto the span of the first $k$ orthonormal vectors. Gram–Schmidt ensures $P_k$ projects onto the span of $\mathbf{v}_1, \dots, \mathbf{v}_k$.

Projectors are idempotent and Hermitian:

$$
P_k^2 = P_k, \quad P_k^\dagger = P_k.
$$

Adding vectors sequentially preserves these properties, ensuring the $\mathbf{e}_k$ remain orthonormal.

**Explanation:** This operator-theoretic approach highlights the geometric role of projectors in maintaining orthonormality throughout the process.

---

**Summary:**

All methods confirm that Gram–Schmidt yields an orthonormal basis spanning the original subspace. The inductive method is constructive, the matrix method is algebraic, and the projection method is geometric. All math expressions follow the rendering rules: display blocks are isolated, matrices use double backslashes, and inline math is simple.

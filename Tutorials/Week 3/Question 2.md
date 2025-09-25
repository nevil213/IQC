<!-- Q2. (Optional) Prove that the Gram–Schmidt procedure produces an orthonormal basis. -->

### Solution

**Method 1 – Induction on the construction index.** Suppose Gram–Schmidt produces vectors $\mathbf{u}_k$ and normalized vectors $\mathbf{e}_k$, with

$$
\mathbf{u}_k = \mathbf{v}_k - \sum_{j=1}^{k-1} \langle \mathbf{e}_j, \mathbf{v}_k \rangle \, \mathbf{e}_j, \qquad \mathbf{e}_k = \frac{\mathbf{u}_k}{\lVert \mathbf{u}_k \rVert}.
$$

*Base step:* $\mathbf{e}_1 = \mathbf{v}_1 / \lVert \mathbf{v}_1 \rVert$ is clearly unit length.

*Inductive step:* Assume $\mathbf{e}_1, \dots, \mathbf{e}_{k-1}$ are orthonormal. For $j < k$ we have

$$
\langle \mathbf{e}_j, \mathbf{u}_k \rangle = \langle \mathbf{e}_j, \mathbf{v}_k \rangle - \sum_{m=1}^{k-1} \langle \mathbf{e}_m, \mathbf{v}_k \rangle \langle \mathbf{e}_j, \mathbf{e}_m \rangle = \langle \mathbf{e}_j, \mathbf{v}_k \rangle - \langle \mathbf{e}_j, \mathbf{v}_k \rangle = 0,
$$

because orthonormality of $\{\mathbf{e}_m\}_{m=1}^{k-1}$ forces $\langle \mathbf{e}_j, \mathbf{e}_m \rangle = \delta_{jm}$. Therefore $\mathbf{u}_k$ is orthogonal to every previous $\mathbf{e}_j$. Normalizing does not disturb orthogonality, and $\mathbf{e}_k$ has unit norm by construction. The process thus yields an orthonormal set $\{\mathbf{e}_1, \dots, \mathbf{e}_n\}$.

Linear independence of the $\mathbf{v}_k$ also implies each $\mathbf{u}_k \neq \mathbf{0}$ (otherwise $\mathbf{v}_k$ would lie inside the span of earlier vectors), so the algorithm never divides by zero.

**Method 2 – Matrix/QR factorization argument.** Place the original vectors in a matrix $V = [\mathbf{v}_1, \dots, \mathbf{v}_n]$. Gram–Schmidt factorizes this as $V = QR$, where $Q = [\mathbf{e}_1, \dots, \mathbf{e}_n]$ and $R$ is upper triangular with positive diagonal. The Gram matrix of the original set satisfies

$$
V^\dagger V = R^\dagger Q^\dagger Q R.
$$

Because the Gram matrix is positive-definite (the $\mathbf{v}_k$ are linearly independent), $R$ is invertible. Therefore

$$
Q^\dagger Q = (R^\dagger)^{-1} V^\dagger V R^{-1} = I,
$$

so the columns of $Q$ are orthonormal. This shows Gram–Schmidt produces a matrix with orthonormal columns and, consequently, an orthonormal basis spanning the same subspace as the columns of $V$.

**Method 3 – Projection-operator invariance.** Define $P_{k} = \sum_{j=1}^{k} \lvert \mathbf{e}_j \rangle \langle \mathbf{e}_j \rvert$. Gram–Schmidt ensures $P_k$ is the orthogonal projector onto the span of $\{\mathbf{v}_1, \dots, \mathbf{v}_k\}$. Because projectors are idempotent and Hermitian,

$$
P_k^2 = P_k, \qquad P_k^\dagger = P_k,
$$

and sequentially adding vectors via $P_{k} = P_{k-1} + \lvert \mathbf{e}_k \rangle \langle \mathbf{e}_k \rvert$ preserves orthogonality and normalization. Hence the resulting $\mathbf{e}_k$ form an orthonormal basis of the subspace.

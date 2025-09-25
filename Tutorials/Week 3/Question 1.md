<!-- Q1. What is the Gram–Schmidt procedure? Write down the procedure. (Refer to
Nielsen & Chuang, Section 2.1.4) -->

### Solution

**Method 1 – Iterative orthogonalization (textbook algorithm).** Given a linearly independent set of vectors $\{\mathbf{v}_1, \dots, \mathbf{v}_n\}$ in an inner-product space:

1. Initialize $\mathbf{u}_1 = \mathbf{v}_1$ and normalize to $\mathbf{e}_1 = \mathbf{u}_1 / \lVert \mathbf{u}_1 \rVert$.
2. For each $k = 2, \dots, n$, subtract from $\mathbf{v}_k$ its projections onto the previously constructed orthonormal vectors:

	$$
	\mathbf{u}_k = \mathbf{v}_k - \sum_{j=1}^{k-1} \langle \mathbf{e}_j, \mathbf{v}_k \rangle \, \mathbf{e}_j
	$$

3. Normalize to obtain $\mathbf{e}_k = \mathbf{u}_k / \lVert \mathbf{u}_k \rVert$. The ordered set $\{\mathbf{e}_1, \dots, \mathbf{e}_n\}$ is an orthonormal basis spanning the same subspace as the original vectors.

This version is often called the *classical Gram–Schmidt* procedure.

**Method 2 – Projection-operator formulation.** Let $P_{k-1}$ denote the projector onto the span of $\{\mathbf{e}_1, \dots, \mathbf{e}_{k-1}\}$. Then

$$
P_{k-1} = \sum_{j=1}^{k-1} \lvert \mathbf{e}_j \rangle \langle \mathbf{e}_j \rvert,
$$

and the $k$-th orthogonalized (but not yet normalized) vector is obtained by

$$
\mathbf{u}_k = (I - P_{k-1}) \mathbf{v}_k.
$$

Normalizing $\mathbf{u}_k$ again yields $\mathbf{e}_k = \mathbf{u}_k / \lVert \mathbf{u}_k \rVert$. This formulation emphasizes that Gram–Schmidt repeatedly removes components lying in already-constructed subspaces by applying complementary projectors.

**Method 3 – Matrix/QR viewpoint.** Assemble the original vectors as columns of a matrix $V = [\mathbf{v}_1, \dots, \mathbf{v}_n]$. The Gram–Schmidt procedure factorizes $V$ as

$$
V = QR,
$$

where $Q$ has orthonormal columns (those are $\mathbf{e}_k$) and $R$ is upper triangular with positive diagonal entries. The entries of $R$ record the projection coefficients computed in Method 1. Computationally, this QR factorization perspective connects Gram–Schmidt to numerical linear algebra routines and highlights its stability-improved variants (such as modified Gram–Schmidt or Householder QR).

Across all three viewpoints the essence is identical: starting with a linearly independent set, we iteratively create orthogonal vectors by removing previously accounted-for components and then normalize to reach an orthonormal basis.
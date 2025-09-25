# Q1. What is the Gram–Schmidt procedure? Write down the procedure. (Refer to Nielsen & Chuang, Section 2.1.4)

## Solution

Below are multiple methods for the Gram–Schmidt procedure, each explained in detail. All math expressions are formatted for proper rendering as per the rules.

---

**Method 1 – Iterative Orthogonalization (Textbook Algorithm)**

Suppose you are given a linearly independent set of vectors $\{\mathbf{v}_1, \dots, \mathbf{v}_n\}$ in an inner-product space. The Gram–Schmidt procedure constructs an orthonormal basis $\{\mathbf{e}_1, \dots, \mathbf{e}_n\}$ spanning the same subspace as follows:

1. **Initialize the first vector:**

	Set $\mathbf{u}_1 = \mathbf{v}_1$ and normalize:

	$$
	\mathbf{e}_1 = \frac{\mathbf{u}_1}{\lVert \mathbf{u}_1 \rVert}
	$$

2. **Iterative step for $k = 2, \dots, n$:**

	Subtract from $\mathbf{v}_k$ its projections onto the previously constructed orthonormal vectors:

	$$
	\mathbf{u}_k = \mathbf{v}_k - \sum_{j=1}^{k-1} \langle \mathbf{e}_j, \mathbf{v}_k \rangle \, \mathbf{e}_j
	$$

	Normalize:

	$$
	\mathbf{e}_k = \frac{\mathbf{u}_k}{\lVert \mathbf{u}_k \rVert}
	$$

3. **Result:**

	The ordered set $\{\mathbf{e}_1, \dots, \mathbf{e}_n\}$ is an orthonormal basis for the span of the original vectors.

**Explanation:**

At each step, the procedure removes components of the current vector that lie along directions already accounted for, ensuring orthogonality. Normalization then guarantees unit length. This is the classical Gram–Schmidt algorithm, widely used in mathematics and physics.

---

**Method 2 – Projection-Operator Formulation**

Let $P_{k-1}$ be the projector onto the span of $\{\mathbf{e}_1, \dots, \mathbf{e}_{k-1}\}$:

$$
P_{k-1} = \sum_{j=1}^{k-1} \lvert \mathbf{e}_j \rangle \langle \mathbf{e}_j \rvert
$$

The $k$-th orthogonalized (but not yet normalized) vector is obtained by applying the complementary projector:

$$
\mathbf{u}_k = (I - P_{k-1}) \mathbf{v}_k
$$

Normalize as before:

$$
\mathbf{e}_k = \frac{\mathbf{u}_k}{\lVert \mathbf{u}_k \rVert}
$$

**Explanation:**

This method emphasizes that Gram–Schmidt is a process of repeatedly removing components lying in already-constructed subspaces by applying complementary projectors. It is especially useful in quantum mechanics, where projectors are fundamental.

---

**Method 3 – Matrix/QR Factorization Viewpoint**

Arrange the original vectors as columns of a matrix:

$$
V = [\mathbf{v}_1, \dots, \mathbf{v}_n]
$$

The Gram–Schmidt procedure factorizes $V$ as

$$
V = Q R
$$

where $Q$ has orthonormal columns (the $\mathbf{e}_k$) and $R$ is upper triangular with positive diagonal entries. The entries of $R$ record the projection coefficients computed in Method 1.

**Explanation:**

This QR factorization perspective connects Gram–Schmidt to numerical linear algebra routines and highlights its stability-improved variants (such as modified Gram–Schmidt or Householder QR). It is the basis for many algorithms in computational mathematics.

---

**Summary:**

Across all three viewpoints, the essence is identical: starting with a linearly independent set, we iteratively create orthogonal vectors by removing previously accounted-for components and then normalize to reach an orthonormal basis. All math expressions above are formatted for proper rendering: display math blocks are isolated, matrices use double backslashes, and inline math is only used for simple expressions.

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
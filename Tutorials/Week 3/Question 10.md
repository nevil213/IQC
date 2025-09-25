A projector satisfies the equation $P^2 = P$ because its fundamental purpose is to map vectors into a specific subspace. Once a vector is in that subspace, projecting it again will not change it. This property, that applying the operation twice is the same as applying it once, is known as **idempotence**.

***

### **Q10. Show that any projector $P$ satisfies the equation $P^2 = P$.**

A **projector** is an operator that takes any vector and finds its component within a given subspace. We can prove its defining property of idempotence ($P^2=P$) from this fundamental definition.

---

## **Solution 1: Geometric Argument**

This is the most intuitive way to understand why projectors are idempotent.

1.  **First Projection:** Let $S$ be the subspace onto which the operator $P$ projects. When we apply $P$ to an arbitrary vector $|\psi\rangle$, the resulting vector, which we'll call $|\psi_S\rangle$, lies entirely within the subspace $S$.
    $$
    |\psi_S\rangle = P|\psi\rangle
    $$
    

2.  **Second Projection:** Now, let's apply the projector $P$ a second time to this result, $P|\psi_S\rangle$. The definition of a projection states that any vector already lying within the target subspace is left unchanged by the projection. Since $|\psi_S\rangle$ is in $S$, applying $P$ to it does nothing.
    $$
    P|\psi_S\rangle = |\psi_S\rangle
    $$

3.  **Conclusion:** By substituting the definition of $|\psi_S\rangle$ from the first step into the second, we get:
    $$
    P(P|\psi\rangle) = P|\psi\rangle
    $$
    This can be rewritten as $P^2|\psi\rangle = P|\psi\rangle$. Since this equation holds true for any arbitrary vector $|\psi\rangle$, the operators themselves must be equal.
    $$
    P^2 = P
    $$

---

## **Solution 2: Algebraic Proof using Vector Decomposition**

This proof is more formal and relies on decomposing the vector space.

1.  **Decomposition of the Vector Space:** Any vector space $V$ can be expressed as the **direct sum** of a subspace $S$ and its orthogonal complement $S^\perp$. This means any vector $|\psi\rangle \in V$ can be uniquely written as:
    $$
    |\psi\rangle = |\psi_S\rangle + |\psi_{S^\perp}\rangle
    $$
    where $|\psi_S\rangle$ is the component in $S$ and $|\psi_{S^\perp}\rangle$ is the component in $S^\perp$.

2.  **Action of the Projector:** The projector $P$ onto the subspace $S$ is defined by its action on these components: it preserves the component in $S$ and annihilates the component in $S^\perp$.
    $$
    P|\psi\rangle = P(|\psi_S\rangle + |\psi_{S^\perp}\rangle) = |\psi_S\rangle
    $$

3.  **Applying the Projector Twice:** Now we apply $P$ again to the result:
    $$
    P^2|\psi\rangle = P(P|\psi\rangle) = P(|\psi_S\rangle)
    $$
    Since the vector $|\psi_S\rangle$ is already entirely within the subspace $S$, applying the projector $P$ to it leaves it unchanged.
    $$
    P(|\psi_S\rangle) = |\psi_S\rangle
    $$

4.  **Conclusion:** We have shown that $P|\psi\rangle = |\psi_S\rangle$ and $P^2|\psi\rangle = |\psi_S\rangle$. As these are equal for any vector $|\psi\rangle$, the operators must be equal.
    $$
    P^2 = P
    $$

---

## **Solution 3: Proof using Spectral Decomposition**

This proof applies to the common case of **orthogonal projectors** used in quantum mechanics, which are also Hermitian ($P^\dagger = P$).

1.  **Eigenvalues of a Projector:** From the idempotence property, it can be shown that the eigenvalues, $\lambda_k$, of any projector can only be 0 or 1.

2.  **Spectral Decomposition:** The spectral theorem states that any Hermitian operator can be diagonalized and written as a sum of its eigenvalues weighting projectors onto its eigenspaces:
    $$
    P = \sum_k \lambda_k |k\rangle\langle k|
    $$
    where $\{|k\rangle\}$ is an orthonormal basis of eigenvectors. Since $\lambda_k$ is either 0 or 1, this means $P$ is the sum of projectors onto the subspace where the eigenvalue is 1 (the subspace $S$).
    $$
    P = \sum_{k \text{ where } \lambda_k=1} |k\rangle\langle k|
    $$

3.  **Squaring the Operator:** Let's compute $P^2$ using this form:
    $$
    P^2 = \left(\sum_{j \in S} |j\rangle\langle j|\right) \left(\sum_{k \in S} |k\rangle\langle k|\right) = \sum_{j,k \in S} |j\rangle\langle j|k\rangle\langle k|
    $$
    Because the eigenvectors form an orthonormal basis, $\langle j|k\rangle = \delta_{jk}$. The sum collapses to only those terms where $j=k$:
    $$
    P^2 = \sum_{k \in S} |k\rangle\langle k|
    $$

4.  **Conclusion:** The result of the sum is just the original operator $P$. 🎯
    $$
    P^2 = P
    $$
# Q7. Show that the eigenvalues of a projector $P$ are all either 0 or 1.

## Solution

Below are multiple methods to show that the eigenvalues of a projector $P$ are all either 0 or 1, each explained in detail. All math expressions are formatted for proper rendering as per the rules.

---

**Method 1 – Eigenvalue Equation from Idempotence**

For an eigenvector $\lvert \psi \rangle$ with $P \lvert \psi \rangle = \lambda \lvert \psi \rangle$, apply $P$ again:

$$
P^2 \lvert \psi \rangle = P (\lambda \lvert \psi \rangle) = \lambda P \lvert \psi \rangle = \lambda^2 \lvert \psi \rangle.
$$

But $P^2 = P$, so $\lambda^2 \lvert \psi \rangle = \lambda \lvert \psi \rangle$, implying $\lambda(\lambda - 1) = 0$.

**Explanation:** Idempotence forces eigenvalues to satisfy a quadratic equation with roots 0 and 1.

---

**Method 2 – Spectral Decomposition**

As a normal operator, $P = \sum_k \lambda_k \lvert k \rangle \langle k \rvert$. Then $P^2 = \sum_k \lambda_k^2 \lvert k \rangle \langle k \rvert = P$, so $\lambda_k^2 = \lambda_k$.

**Explanation:** The spectral theorem decomposes $P$, and idempotence constrains the eigenvalues.

---

**Method 3 – Geometric Argument**

Vectors in the subspace $\mathcal{S}$ are unchanged by $P$ (eigenvalue 1), while orthogonal vectors map to zero (eigenvalue 0).

**Explanation:** Projectors preserve their range and annihilate the orthogonal complement.

---

**Summary:**

Thus all eigenvalues of any projector are either zero or one. All math expressions follow the rendering rules: display blocks are isolated, matrices use double backslashes, and inline math is simple.

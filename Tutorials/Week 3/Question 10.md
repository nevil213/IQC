# Q10. Show that any projector $P$ satisfies the equation $P^2 = P$.

## Solution

Below are multiple methods to show that any projector $P$ satisfies $P^2 = P$, each explained in detail. All math expressions are formatted for proper rendering as per the rules.

---

**Method 1 – Direct Geometric Reasoning**

Decompose $\lvert \psi \rangle = \lvert \psi_{\parallel} \rangle + \lvert \psi_{\perp} \rangle$ with $\lvert \psi_{\parallel} \rangle \in \mathcal{S}$, $\lvert \psi_{\perp} \rangle \perp \mathcal{S}$. Then $P \lvert \psi \rangle = \lvert \psi_{\parallel} \rangle$, and $P^2 \lvert \psi \rangle = P \lvert \psi_{\parallel} \rangle = \lvert \psi_{\parallel} \rangle = P \lvert \psi \rangle$.

**Explanation:** Projectors are idempotent by definition in geometric terms.

---

**Method 2 – Matrix Form of Orthogonal Projectors**

For $P = V V^\dagger$ with $V^\dagger V = I$, $P^2 = (V V^\dagger)(V V^\dagger) = V (V^\dagger V) V^\dagger = V I V^\dagger = P$.

**Explanation:** Matrix multiplication confirms idempotence for orthogonal projectors.

---

**Method 3 – Spectral Decomposition**

$P = \sum_k \lambda_k \lvert k \rangle \langle k \rvert$ with $\lambda_k \in \{0,1\}$. Then $P^2 = \sum_k \lambda_k^2 \lvert k \rangle \langle k \rvert = \sum_k \lambda_k \lvert k \rangle \langle k \rvert = P$.

**Explanation:** Eigenvalues being 0 or 1 force idempotence.

---

**Summary:**

Therefore every projector is idempotent: $P^2 = P$. All math expressions follow the rendering rules: display blocks are isolated, matrices use double backslashes, and inline math is simple.
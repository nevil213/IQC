<!-- Q10. Show that any projector P satisfies the equation P
2 = P. -->

### Solution

Let $P$ be a projector onto a subspace $\mathcal{S}$ of a Hilbert space.

**Method 1 – Direct geometric reasoning.** For any vector $\lvert \psi \rangle$ decompose $\lvert \psi \rangle = \lvert \psi_{\parallel} \rangle + \lvert \psi_{\perp} \rangle$ with $\lvert \psi_{\parallel} \rangle \in \mathcal{S}$ and $\lvert \psi_{\perp} \rangle \perp \mathcal{S}$. Applying $P$ once yields $P \lvert \psi \rangle = \lvert \psi_{\parallel} \rangle$, and applying $P$ again leaves the vector unchanged: $P^2 \lvert \psi \rangle = P \lvert \psi_{\parallel} \rangle = \lvert \psi_{\parallel} \rangle = P \lvert \psi \rangle$. Since this holds for all vectors, $P^2 = P$.

**Method 2 – Matrix form of orthogonal projectors.** If $P$ is an orthogonal projector onto the columns of a matrix $V$ with orthonormal columns ($V^\dagger V = I$), then $P = V V^\dagger$. Multiplying gives

$$
P^2 = (V V^\dagger)(V V^\dagger) = V (V^\dagger V) V^\dagger = V I V^\dagger = P.
$$

**Method 3 – Spectral decomposition.** Projectors are normal operators, so we may write

$$
P = \sum_k \lambda_k \lvert k \rangle \langle k \rvert
$$

with eigenvalues $\lambda_k \in \{0, 1\}$ (see Question 7). Then

$$
P^2 = \sum_k \lambda_k^2 \lvert k \rangle \langle k \rvert = \sum_k \lambda_k \lvert k \rangle \langle k \rvert = P.
$$

Therefore every projector is idempotent: $P^2 = P$.
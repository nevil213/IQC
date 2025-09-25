<!-- Q7. Show that the eigenvalues of a projector P are all either 0 or 1. -->

### Solution

Let $P$ be a projector, i.e., $P^2 = P$ and $P^\dagger = P$ (orthogonal projector) or more generally $P^2 = P$ (idempotent operator).

**Method 1 – Eigenvalue equation from idempotence.** Suppose $P \lvert \psi \rangle = \lambda \lvert \psi \rangle$ for some eigenpair $(\lambda, \lvert \psi \rangle)$. Then

$$
P^2 \lvert \psi \rangle = P (\lambda \lvert \psi \rangle) = \lambda P \lvert \psi \rangle = \lambda^2 \lvert \psi \rangle.
$$

But $P^2 = P$ implies

$$
P^2 \lvert \psi \rangle = P \lvert \psi \rangle = \lambda \lvert \psi \rangle.
$$

Equating the two expressions gives $\lambda^2 = \lambda$, so $\lambda(\lambda - 1) = 0$ and therefore $\lambda \in \{0, 1\}$.

**Method 2 – Spectral decomposition.** Because $P$ is normal ($P^\dagger P = P P^\dagger$) whenever it is an orthogonal projector, the spectral theorem applies:

$$
P = \sum_k \lambda_k \lvert k \rangle \langle k \rvert.
$$

Applying $P^2 = P$ gives

$$
\sum_k \lambda_k^2 \lvert k \rangle \langle k \rvert = \sum_k \lambda_k \lvert k \rangle \langle k \rvert,
$$

leading to the same constraint $\lambda_k^2 = \lambda_k$ for every eigenvalue. Hence all $\lambda_k$ equal $0$ or $1$.

**Method 3 – Geometric argument.** If $P$ projects onto a subspace $\mathcal{S}$, then vectors in $\mathcal{S}$ are left unchanged (eigenvalue $1$), while vectors orthogonal to $\mathcal{S}$ are mapped to the zero vector (eigenvalue $0$). Decomposing any vector as $\lvert \psi \rangle = \lvert \psi_{\parallel} \rangle + \lvert \psi_{\perp} \rangle$ with $\lvert \psi_{\parallel} \rangle \in \mathcal{S}$ and $\lvert \psi_{\perp} \rangle \perp \mathcal{S}$ shows directly that $P$ has no other eigenvalues.

Thus all eigenvalues of any projector are either zero or one.

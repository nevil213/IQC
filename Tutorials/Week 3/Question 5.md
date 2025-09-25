<!-- Q5. Use the spectral decomposition to show that K ≡ −ilog(U) is Hermitian for any
unitary U, and thus U = exp(iK) for some Hermitian K. -->

### Solution

Let $U$ be a unitary operator, so $U^\dagger U = U U^\dagger = I$.

**Method 1 – Spectral decomposition.** Every unitary operator admits an orthonormal eigenbasis $\{\lvert u_k \rangle\}$ with eigenvalues of unit modulus:

$$
U = \sum_k e^{i \theta_k} \lvert u_k \rangle \langle u_k \rvert, \qquad \theta_k \in (-\pi, \pi].
$$

Define

$$
K = -i \log(U) := \sum_k \theta_k \lvert u_k \rangle \langle u_k \rvert.
$$

The coefficients $\theta_k$ are real, giving $K^\dagger = K$ directly. Exponentiating reproduces $U$:

$$
\exp(iK) = \sum_k e^{i \theta_k} \lvert u_k \rangle \langle u_k \rvert = U.
$$

The only subtlety is choosing a consistent branch for the logarithm; selecting angles $\theta_k$ in any interval of width $2\pi$ works, and different choices merely shift $K$ by integer multiples of $2\pi$ on the corresponding eigenspaces.

**Method 2 – Functional calculus and adjoint properties.** For a unitary $U$, the logarithm may be defined via the holomorphic functional calculus using a contour that winds around the spectrum of $U$ once. One obtains

$$
\big( \log U \big)^\dagger = \log(U^\dagger) = \log(U^{-1}) = - \log U,
$$

provided the branch cut is chosen symmetrically about the real axis. Consequently,

$$
K^\dagger = (-i \log U)^\dagger = i (\log U)^\dagger = i (- \log U) = -i \log U = K.
$$

This approach emphasizes that the anti-Hermitian generator $\log U$ exponentiates to a unitary and that multiplying by $-i$ produces a Hermitian generator.

**Method 3 – Polar decomposition of normal operators.** Any normal operator $N$ admits $N = V P$ with $V$ unitary and $P$ positive. Specializing to $U$ (already unitary) gives $U = V$ and $P = I$. The continuous one-parameter family $U(s) = U^s$ is unitary for real $s$. Differentiating at $s = 0$ yields the Hermitian generator

$$
K = -i \left. \frac{\mathrm{d}U^s}{\mathrm{d}s} \right\rvert_{s = 0},
$$

which coincides with $-i \log U$. As generators of unitary one-parameter groups are always Hermitian, $K$ must be Hermitian.

Therefore every unitary $U$ can be written as $U = e^{iK}$ for some Hermitian $K$, unique up to additions of $2\pi$ times projectors onto eigenspaces, reflecting the multivalued nature of the logarithm on the unit circle.

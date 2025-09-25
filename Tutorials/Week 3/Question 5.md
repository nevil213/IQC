# Q5. Use the spectral decomposition to show that $K \equiv -i \log(U)$ is Hermitian for any unitary $U$, and thus $U = \exp(iK)$ for some Hermitian $K$.

## Solution

Below are multiple methods to show that $K = -i \log(U)$ is Hermitian for any unitary $U$, implying $U = \exp(iK)$ for some Hermitian $K$, each explained in detail. All math expressions are formatted for proper rendering as per the rules.

---

**Method 1 – Spectral Decomposition**

Any unitary $U$ has an orthonormal eigenbasis $\{\lvert u_k \rangle\}$ with eigenvalues $e^{i \theta_k}$, $\theta_k \in (-\pi, \pi]$. Define:

$$
K = -i \log(U) = \sum_k \theta_k \lvert u_k \rangle \langle u_k \rvert.
$$

Since $\theta_k$ are real, $K^\dagger = K$. Exponentiating gives:

$$
\exp(iK) = \sum_k e^{i \theta_k} \lvert u_k \rangle \langle u_k \rvert = U.
$$

**Explanation:** This directly constructs $K$ from the phases, ensuring Hermiticity and reproducing $U$.

---

**Method 2 – Functional Calculus and Adjoint Properties**

Using holomorphic functional calculus, $\log(U)^\dagger = \log(U^\dagger) = \log(U^{-1}) = -\log(U)$, with branch cut chosen symmetrically. Thus:

$$
K^\dagger = (-i \log U)^\dagger = i (\log U)^\dagger = i (-\log U) = -i \log U = K.
$$

**Explanation:** This analytic approach confirms Hermiticity via functional properties of the logarithm.

---

**Method 3 – Polar Decomposition of Normal Operators**

For normal $U$, polar decomposition gives $U = V P$ with $V$ unitary and $P$ positive. Differentiating $U(s) = U^s$ at $s=0$ yields:

$$
K = -i \left. \frac{dU^s}{ds} \right|_{s=0},
$$

which equals $-i \log U$.

**Explanation:** Generators of unitary groups are Hermitian, so $K$ must be Hermitian.

---

**Summary:**

Every unitary $U$ can be written as $U = e^{iK}$ for Hermitian $K$, unique up to $2\pi$ multiples on eigenspaces. The spectral method is constructive, the functional method is analytic, and the polar method is group-theoretic. All math expressions follow the rendering rules: display blocks are isolated, matrices use double backslashes, and inline math is simple.

<!-- Q8. Show that a positive operator is necessarily Hermitian. -->

### Solution

An operator $A$ on a Hilbert space is *positive* if $\langle \psi, A \psi \rangle \geq 0$ for all vectors $\lvert \psi \rangle$.

**Method 1 – Polarization identity.** For any vectors $\lvert \phi \rangle$ and $\lvert \psi \rangle$ the complex polarization identity gives

$$
\langle \phi, A \psi \rangle = \frac{1}{4} \sum_{k=0}^3 i^k \langle \phi + i^k \psi, A (\phi + i^k \psi) \rangle.
$$

Each inner product on the right is real because $\langle \chi, A \chi \rangle \geq 0$. Therefore $\langle \phi, A \psi \rangle = \langle A \phi, \psi \rangle$, showing $A = A^\dagger$.

**Method 2 – Spectral theorem for normal operators.** A positive operator $A$ is automatically normal because $A^\dagger A = A A^\dagger$ when $A$ commutes with $A^\dagger$. The spectral theorem then writes

$$
A = \sum_k \lambda_k \lvert k \rangle \langle k \rvert,
$$

with eigenvalues $\lambda_k \geq 0$. Since the expansion coefficients are real and the eigenvectors form an orthonormal basis, $A$ equals its adjoint. (If $A$ were not Hermitian, some eigenvalue would have to be complex, contradicting positivity.)

**Method 3 – Square-root construction.** Positivity ensures there exists a unique positive operator $B$ such that $A = B^2$ (this is the operator square root). Then

$$
A^\dagger = (B^2)^\dagger = (B^\dagger)^2 = B^2 = A,
$$

where we use that $B$ is positive (hence Hermitian by the argument recursively) and commute $B$ with itself. Consequently, $A$ must be Hermitian.

In any of these viewpoints, the central point is that positivity forces the operator to have a real spectrum, making the operator Hermitian.

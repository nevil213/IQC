<!-- Q4. Prove that U(t1, t2) defined as
U(t1, t2) = exp 
−
iH(t2 − t1)
ℏ

is unitary. Here, H is the Hamiltonian as described in Postulate 2′
. -->

### Solution

Let

$$
U(t_1, t_2) = \exp\!\left( -\frac{i}{\hbar} H (t_2 - t_1) \right),
$$

where $H$ is a Hermitian (self-adjoint) Hamiltonian operator.

**Method 1 – Spectral decomposition of the Hamiltonian.** Because $H$ is Hermitian, it admits the spectral decomposition

$$
H = \sum_k E_k \lvert E_k \rangle \langle E_k \rvert,
$$

with real eigenvalues $E_k$ and orthonormal eigenvectors $\{\lvert E_k \rangle\}$. Then

$$
U(t_1, t_2) = \sum_k \exp\!\left( -\frac{i}{\hbar} E_k (t_2 - t_1) \right) \lvert E_k \rangle \langle E_k \rvert.
$$

Taking the adjoint gives

$$
U(t_1, t_2)^\dagger = \sum_k \exp\!\left( \frac{i}{\hbar} E_k (t_2 - t_1) \right) \lvert E_k \rangle \langle E_k \rvert,
$$

and multiplying shows

$$
U(t_1, t_2)^\dagger U(t_1, t_2) = \sum_k \lvert E_k \rangle \langle E_k \rvert = I.
$$

Hence $U(t_1, t_2)$ is unitary. The same computation yields $U(t_1, t_2) U(t_1, t_2)^\dagger = I$.

**Method 2 – Anti-Hermitian exponentials.** Define

$$
A = -\frac{i}{\hbar} H (t_2 - t_1).
$$

Because $H^\dagger = H$ and $t_2 - t_1$ is real, we have $A^\dagger = -A$. Exponentials of anti-Hermitian operators are unitary:

$$
\big( e^A \big)^\dagger e^A = e^{A^\dagger} e^A = e^{-A} e^A = e^{0} = I.
$$

This argument relies only on the algebraic identity $e^{B} e^{C} = e^{B+C}$ when $B$ and $C$ commute, which holds here because $A$ commutes with itself and with $-A$.

**Method 3 – Differential equation for the propagator.** Treat $U(t) = U(t_0, t)$ and note that it satisfies the Schrödinger equation

$$
i \hbar \, \frac{\mathrm{d}U(t)}{\mathrm{d}t} = H U(t), \qquad U(t_0) = I.
$$

Differentiate $U(t)^\dagger U(t)$:

$$
\frac{\mathrm{d}}{\mathrm{d}t}\big( U(t)^\dagger U(t) \big) = \left( \frac{\mathrm{d}U(t)^\dagger}{\mathrm{d}t} \right) U(t) + U(t)^\dagger \frac{\mathrm{d}U(t)}{\mathrm{d}t} = \frac{i}{\hbar} U(t)^\dagger H U(t) - \frac{i}{\hbar} U(t)^\dagger H U(t) = 0.
$$

Since $U(t_0)^\dagger U(t_0) = I$, the solution remains the identity for all $t$, implying unitarity. This method highlights that even when $H$ varies with time (provided it remains Hermitian), the time-evolution operator stays unitary.
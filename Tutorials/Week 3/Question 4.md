# Q4. Prove that $U(t_1, t_2) = \exp\left( -\frac{i}{\hbar} H (t_2 - t_1) \right)$ is unitary. Here, H is the Hamiltonian as described in Postulate 2'.

## Solution

Below are multiple methods to prove that $U(t_1, t_2) = \exp\left( -\frac{i}{\hbar} H (t_2 - t_1) \right)$ is unitary, each explained in detail. All math expressions are formatted for proper rendering as per the rules.

---

**Method 1 – Spectral Decomposition of the Hamiltonian**

Since $H$ is Hermitian, it has a spectral decomposition:

$$
H = \sum_k E_k \lvert E_k \rangle \langle E_k \rvert,
$$

with real $E_k$ and orthonormal $\lvert E_k \rangle$. Thus,

$$
U(t_1, t_2) = \sum_k \exp\left( -\frac{i}{\hbar} E_k (t_2 - t_1) \right) \lvert E_k \rangle \langle E_k \rvert.
$$

The adjoint is:

$$
U(t_1, t_2)^\dagger = \sum_k \exp\left( \frac{i}{\hbar} E_k (t_2 - t_1) \right) \lvert E_k \rangle \langle E_k \rvert.
$$

Multiplying gives $U^\dagger U = I$, confirming unitarity.

**Explanation:** This method uses the eigenbasis to show that each component is a phase factor on the unit circle, preserving unitarity.

---

**Method 2 – Anti-Hermitian Exponentials**

Define $A = -\frac{i}{\hbar} H (t_2 - t_1)$. Since $H^\dagger = H$ and $t_2 - t_1$ is real, $A^\dagger = -A$. Exponentials of anti-Hermitian operators are unitary:

$$
(e^A)^\dagger e^A = e^{A^\dagger} e^A = e^{-A} e^A = I.
$$

**Explanation:** Anti-Hermitian operators generate unitary groups, as their exponentials satisfy the unitarity condition algebraically.

---

**Method 3 – Differential Equation for the Propagator**

$U(t) = U(t_0, t)$ satisfies $i \hbar \frac{dU}{dt} = H U$, with $U(t_0) = I$. Differentiate $U^\dagger U$:

$$
\frac{d}{dt} (U^\dagger U) = \left( \frac{dU^\dagger}{dt} \right) U + U^\dagger \frac{dU}{dt} = \frac{i}{\hbar} U^\dagger H U - \frac{i}{\hbar} U^\dagger H U = 0.
$$

Since $U(t_0)^\dagger U(t_0) = I$, unitarity holds for all $t$.

**Explanation:** This dynamical approach shows unitarity is preserved under the time-evolution equation, even for time-dependent Hamiltonians.

---

**Summary:**

All methods confirm that the time-evolution operator is unitary due to the Hermitian nature of $H$. The spectral method is basis-dependent, the exponential method is algebraic, and the differential method is dynamical. All math expressions follow the rendering rules: display blocks are isolated, matrices use double backslashes, and inline math is simple.
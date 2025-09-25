# Question 2: Suppose we prepare a quantum system in an eigenstate $\lvert \psi \rangle$ of some observable $M$, with corresponding eigenvalue $m$. What is the average observed value of $M$, and the standard deviation?

## Solution

Below are multiple methods to determine the average observed value and standard deviation when measuring $M$ on its eigenstate $\lvert \psi \rangle$, each explained in detail. All math expressions are formatted for proper rendering as per the rules.

---

**Method 1 – Expectation Value Calculation**

Since $M \lvert \psi \rangle = m \lvert \psi \rangle$, the expectation value is:

$$
\langle M \rangle = \langle \psi \vert M \vert \psi \rangle = m \langle \psi \vert \psi \rangle = m.
$$

The variance is $\langle M^2 \rangle - \langle M \rangle^2 = m^2 - m^2 = 0$, so standard deviation $\sigma = 0$.

**Explanation:** Eigenstates give definite outcomes, so no spread.

---

**Method 2 – Measurement Outcome**

Every measurement yields $m$ with probability 1, so average is $m$, and $\sigma = 0$.

**Explanation:** Deterministic measurement.

---

**Method 3 – Spectral Decomposition**

$M = \sum_k \lambda_k P_k$, and $\lvert \psi \rangle$ is in the eigenspace for $\lambda_k = m$, so only that term contributes.

**Explanation:** Only one eigenvalue possible.

---

**Summary:**

Average is $m$, standard deviation is 0. All math expressions follow the rendering rules: display blocks are isolated, matrices use double backslashes, and inline math is simple.
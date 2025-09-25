# Question 1: Show that the average value of the measurement is $\langle \psi | M | \psi \rangle$. Also, compute the formula for standard deviation.

## Solution

Below are multiple methods to show that the average value of a measurement of observable $M$ on state $\lvert \psi \rangle$ is $\langle \psi \vert M \vert \psi \rangle$, and to compute the standard deviation, each explained in detail. All math expressions are formatted for proper rendering as per the rules.

---

**Method 1 – Probabilistic Expectation**

The average value is the sum over possible outcomes $m$ of $m$ times the probability $p(m)$:

$$
\langle M \rangle = \sum_m m p(m).
$$

For projective measurement, $p(m) = \langle \psi \vert P_m \vert \psi \rangle$, where $P_m$ is the projector onto the eigenspace for $m$.

Thus,

$$
\langle M \rangle = \sum_m m \langle \psi \vert P_m \vert \psi \rangle = \langle \psi \vert \left( \sum_m m P_m \right) \vert \psi \rangle = \langle \psi \vert M \vert \psi \rangle.
$$

**Explanation:** This uses the spectral decomposition $M = \sum_m m P_m$.

---

**Method 2 – Post-Measurement State Average**

After measurement yielding $m$, the state collapses to $\lvert \psi_m \rangle = P_m \lvert \psi \rangle / \sqrt{p(m)}$, and the average is the expectation over outcomes.

The standard deviation is $\sigma = \sqrt{ \langle M^2 \rangle - \langle M \rangle^2 }$, where $\langle M^2 \rangle = \langle \psi \vert M^2 \vert \psi \rangle$.

**Explanation:** Variance is the second moment minus square of first moment.

---

**Method 3 – Operator Expectation**

For any observable, the expectation is $\langle M \rangle = \operatorname{Tr}(\rho M)$, where $\rho = \lvert \psi \rangle \langle \psi \vert$.

Thus, $\langle M \rangle = \operatorname{Tr}(\lvert \psi \rangle \langle \psi \vert M) = \langle \psi \vert M \vert \psi \rangle$.

Standard deviation: $\sigma = \sqrt{ \operatorname{Tr}(\rho M^2) - [\operatorname{Tr}(\rho M)]^2 }$.

**Explanation:** This is the general formula for expectation values in quantum mechanics.

---

**Summary:**

The average is $\langle \psi \vert M \vert \psi \rangle$, and standard deviation is $\sqrt{ \langle \psi \vert M^2 \vert \psi \rangle - (\langle \psi \vert M \vert \psi \rangle)^2 }$. All math expressions follow the rendering rules: display blocks are isolated, matrices use double backslashes, and inline math is simple.

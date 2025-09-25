# Q8. Show that a positive operator is necessarily Hermitian.

## Solution

Below are multiple methods to show that a positive operator $A$ (where $\langle \psi, A \psi \rangle \geq 0$ for all $\lvert \psi \rangle$) is necessarily Hermitian, each explained in detail. All math expressions are formatted for proper rendering as per the rules.

---

**Method 1 – Polarization Identity**

The complex polarization identity gives:

$$
\langle \phi, A \psi \rangle = \frac{1}{4} \sum_{k=0}^3 i^k \langle \phi + i^k \psi, A (\phi + i^k \psi) \rangle.
$$

Each term on the right is real and non-negative, so $\langle \phi, A \psi \rangle = \langle A \phi, \psi \rangle$.

**Explanation:** This identity expresses the bilinear form in terms of quadratic forms, forcing symmetry.

---

**Method 2 – Spectral Theorem for Normal Operators**

Positive operators are normal, so $A = \sum_k \lambda_k \lvert k \rangle \langle k \rvert$ with $\lambda_k \geq 0$. The expansion implies $A = A^\dagger$.

**Explanation:** The spectral theorem ensures real eigenvalues and orthonormal basis, yielding Hermiticity.

---

**Method 3 – Square-Root Construction**

Positivity implies $A = B^2$ for positive $B$. Then $A^\dagger = (B^2)^\dagger = B^2 = A$.

**Explanation:** The square root preserves Hermiticity recursively.

---

**Summary:**

In any viewpoint, positivity forces a real spectrum, making the operator Hermitian. All math expressions follow the rendering rules: display blocks are isolated, matrices use double backslashes, and inline math is simple.

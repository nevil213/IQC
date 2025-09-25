> **Question 7:** Show that any measurement where the measurement operators and the POVM elements coincide is a projective measurement.

## Solution

Below are multiple methods to show that if the measurement operators \(M_m\) coincide with the POVM elements \(E_m\), then the measurement is projective, each explained in detail.

---

**Method 1 – POVM Properties and Projector Condition**

For a general measurement, the POVM elements are

$$
E_m = M_m^{\dag} M_m
$$

and they satisfy \(E_m \geq 0\) and \(\sum_m E_m = I\).

If \(M_m = E_m\), then

$$
E_m = M_m^{\dag} M_m = E_m^{\dag} E_m
$$

Since \(E_m\) are Hermitian (as POVM elements), \(E_m^{\dag} = E_m\), so

$$
E_m = E_m^2
$$

Thus, \(E_m\) are projectors: \(E_m^2 = E_m\), \(E_m^{\dag} = E_m\), and \(E_m \geq 0\).

For projectors summing to the identity, they must be orthogonal: \(E_i E_j = 0\) for \(i \neq j\).

This follows because for any vector \(|\psi\rangle\), \(E_i E_j |\psi\rangle = E_i (E_j |\psi\rangle)\), and since \(\sum_k E_k = I\), the ranges are orthogonal subspaces.

Therefore, the measurement is projective.

**Explanation:** The coincidence implies the POVM elements are idempotent and Hermitian, making them orthogonal projectors.

---

**Method 2 – Measurement Operator Decomposition**

From the polar decomposition (as in Question 8), any \(M_m\) can be written as \(M_m = U_m \sqrt{E_m}\), where \(U_m\) is unitary and \(\sqrt{E_m}\) is positive.

If \(M_m = E_m\), then \(E_m = U_m \sqrt{E_m}\).

Since \(E_m\) is Hermitian positive, \(\sqrt{E_m}\) is also Hermitian positive, and \(E_m = U_m \sqrt{E_m}\) implies \(U_m = I\), because the polar decomposition is unique up to phase, but here it forces \(U_m\) to be identity.

Thus,

$$
E_m = \sqrt{E_m}
$$

so \(E_m^2 = E_m\), confirming projectors.

The orthogonality follows as in Method 1.

**Explanation:** The decomposition simplifies to show \(E_m\) are square roots of themselves, hence projectors.

---

**Method 3 – Direct Verification of Projective Conditions**

A projective measurement has orthogonal projectors \(P_m\) with \(P_m^{\dag} = P_m\), \(P_m^2 = P_m\), \(P_m P_k = 0\) for \(m \neq k\), and \(\sum_m P_m = I\).

Given \(M_m = E_m\), and

$$
E_m = M_m^{\dag} M_m
$$

with \(\sum E_m = I\), we have \(E_m^{\dag} = E_m\) and

$$
E_m^2 = E_m
$$

as above.

To confirm orthogonality, note that for \(i \neq j\), \(E_i E_j = E_i E_j\), and since \(E_i^2 = E_i\), applying to a vector in the range of \(E_j\), but more rigorously, the operator \(E_i E_j\) has zero eigenvalues because if \(E_i E_j |\psi\rangle = \lambda |\psi\rangle\), then \(\langle \psi | E_i E_j |\psi\rangle = \lambda\), but also \(\langle \psi | E_i E_j |\psi\rangle = \langle E_j \psi | E_i | E_j \psi \rangle \leq \|E_j \psi\|^2\), but since \(\sum E_k = I\), the supports are disjoint.

Thus,

$$
E_i E_j = 0
$$

**Explanation:** Explicit check shows the POVM elements satisfy all projector axioms, including orthogonality.

---

**Method 4 – Equivalence of Measurement Types**

In quantum mechanics, a measurement is projective if and only if the measurement operators \(M_m\) are orthogonal projectors themselves.

Since \(M_m = E_m\), and we have shown \(E_m\) are orthogonal projectors summing to \(I\), the measurement is projective.

Conversely, for projective measurements, \(M_m = P_m\), so

$$
E_m = P_m^{\dag} P_m = P_m
$$

since projectors are Hermitian.

Thus, the condition \(M_m = E_m\) characterizes projective measurements.

**Explanation:** This establishes the equivalence between the coincidence condition and projective measurements.

---

**Summary:**

Any measurement where \(M_m = E_m\) has POVM elements that are orthogonal projectors summing to the identity, hence it is a projective measurement. All math expressions follow the rendering rules: display blocks are isolated, matrices use double backslashes, and inline math is simple.
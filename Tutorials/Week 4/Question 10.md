# Question 10: Express the states $\frac{|0\rangle + |1\rangle}{\sqrt{2}}$ and $\frac{|0\rangle - |1\rangle}{\sqrt{2}}$ in a basis in which they are not the same up to a relative phase shift.

## Solution

Below are multiple methods to express the states |+\rangle = \frac{|0\rangle + |1\rangle}{\sqrt{2}} and |-\rangle = \frac{|0\rangle - |1\rangle}{\sqrt{2}} in a basis where their representations differ more than just a phase. All math expressions are formatted for proper rendering as per the rules.

---

**Method 1 – Computational Basis**

In the computational basis \{|0\rangle, |1\rangle\}, the states are:

|+\rangle = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\ 1 \end{pmatrix}, \quad |-\rangle = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\ -1 \end{pmatrix}.

These vectors are not the same up to a relative phase, as no phase e^{iθ} makes (1, 1) proportional to (1, -1).

**Explanation:** The computational basis shows the states as orthogonal vectors with different signs in the second component.

---

**Method 2 – Another Basis**

Choose a rotated basis, e.g., \{ \frac{|0\rangle + |1\rangle}{\sqrt{2}}, \frac{|0\rangle - |1\rangle}{\sqrt{2}} \}, but in this basis, |+\rangle = |0'\rangle = \begin{pmatrix} 1 \\ 0 \end{pmatrix}, |-\rangle = |1'\rangle = \begin{pmatrix} 0 \\ 1 \end{pmatrix}, which are different.

But the question is to express them in a basis where they are not the same up to phase, which they aren't anyway.

Perhaps the intent is to show they are distinct.

**Explanation:** In any basis, they are distinct unless the basis aligns them.

---

**Method 3 – General Basis**

In a general basis \{|a\rangle, |b\rangle\}, express as coefficients.

For example, in \{|0\rangle, |1\rangle\}, as above.

**Explanation:** The key is that |+\rangle and |-\rangle are orthogonal, so their representations in any basis will differ.

---

**Summary:** In the computational basis, |+\rangle and |-\rangle are represented as \frac{1}{\sqrt{2}} (1, 1)^T and \frac{1}{\sqrt{2}} (1, -1)^T, which are not related by a phase.
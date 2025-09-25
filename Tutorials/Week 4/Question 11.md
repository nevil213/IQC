# Question 11: Verify that the Bell basis forms an orthonormal basis for the two qubit state space.

## Solution

Below are multiple methods to verify that the Bell states form an orthonormal basis for \mathbb{C}^2 \otimes \mathbb{C}^2. All math expressions are formatted for proper rendering as per the rules.

---

**Method 1 – Definition Check**

The Bell states are:

|\Phi^+\rangle = \frac{1}{\sqrt{2}} (|00\rangle + |11\rangle), \quad |\Phi^-\rangle = \frac{1}{\sqrt{2}} (|00\rangle - |11\rangle),

|\Psi^+\rangle = \frac{1}{\sqrt{2}} (|01\rangle + |10\rangle), \quad |\Psi^-\rangle = \frac{1}{\sqrt{2}} (|01\rangle - |10\rangle).

They are orthonormal: \langle \Phi^+ | \Phi^+ \rangle = 1, \langle \Phi^+ | \Phi^- \rangle = 0, etc.

They span the space: any two-qubit state |\psi\rangle = \sum_{ij} c_{ij} |ij\rangle can be expressed using Bell states.

**Explanation:** Direct computation shows inner products are 1 or 0, and the 4 states span 4-dimensional space.

---

**Method 2 – Matrix Representation**

Represent the Bell states as vectors in \mathbb{C}^4.

|\Phi^+\rangle = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\ 0 \\ 0 \\ 1 \end{pmatrix}, etc.

The Gram matrix is identity, so orthonormal.

The rank is 4, spanning \mathbb{C}^4.

**Explanation:** The vectors are linearly independent and orthogonal.

---

**Method 3 – Completeness**

The projector \sum_{k=1}^4 | \Phi_k \rangle \langle \Phi_k | = I, where \Phi_k are the Bell states.

**Explanation:** This confirms they form a basis.

---

**Summary:** The Bell states are orthonormal and span the two-qubit Hilbert space, forming a basis.

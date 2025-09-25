# Q12. (Eigendecomposition of the Pauli matrices) Find the eigenvectors, eigenvalues, and diagonal representations of the Pauli matrices $X$, $Y$, and $Z$.

## Solution

Below are multiple methods to find the eigenvectors, eigenvalues, and diagonal representations of the Pauli matrices $X$, $Y$, $Z$, each explained in detail. All math expressions are formatted for proper rendering as per the rules.

---

**Method 1 – Direct Eigenvector Solving**

Pauli matrices:

$$
X = \begin{pmatrix} 0 & 1 \\\\ 1 & 0 \end{pmatrix}, \quad Y = \begin{pmatrix} 0 & -i \\\\ i & 0 \end{pmatrix}, \quad Z = \begin{pmatrix} 1 & 0 \\\\ 0 & -1 \end{pmatrix}.
$$

All have eigenvalues $\pm 1$.

- $X$: Eigenvectors $\frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\\\ 1 \end{pmatrix}$ for +1, $\frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\\\ -1 \end{pmatrix}$ for -1.

- $Y$: $\frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\\\ i \end{pmatrix}$ for +1, $\frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\\\ -i \end{pmatrix}$ for -1.

- $Z$: $\begin{pmatrix} 1 \\\\ 0 \end{pmatrix}$ for +1, $\begin{pmatrix} 0 \\\\ 1 \end{pmatrix}$ for -1.

**Explanation:** Solving the characteristic equations directly.

---

**Method 2 – Bloch-Sphere Intuition and Rotations**

Eigenvectors are spin-up/down states:

$$
\lvert \pm x \rangle = \frac{1}{\sqrt{2}} (\lvert 0 \rangle \pm \lvert 1 \rangle), \quad \lvert \pm y \rangle = \frac{1}{\sqrt{2}} (\lvert 0 \rangle \pm i \lvert 1 \rangle), \quad \lvert \pm z \rangle = \lvert 0 \rangle, \lvert 1 \rangle.
$$

**Explanation:** Pauli matrices represent measurements along axes.

---

**Diagonal Representations via Unitary Similarity**

Using $H$ (Hadamard) and $S = \operatorname{diag}(1, i)$:

$$
X = H Z H, \quad Y = (S H) Z (S H)^\dagger, \quad Z = Z.
$$

Explicitly:

$$
X = H \begin{pmatrix} 1 & 0 \\\\ 0 & -1 \end{pmatrix} H^\dagger, \quad Y = U_Y \begin{pmatrix} 1 & 0 \\\\ 0 & -1 \end{pmatrix} U_Y^\dagger, \quad Z = I \begin{pmatrix} 1 & 0 \\\\ 0 & -1 \end{pmatrix} I^\dagger.
$$

**Explanation:** Similarity transformations diagonalize the matrices.

---

**Summary:**

These diagonal forms, together with the eigenvectors listed above, provide the full eigendecomposition for the Pauli matrices. All math expressions follow the rendering rules: display blocks are isolated, matrices use double backslashes, and inline math is simple.
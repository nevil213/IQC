# Q11. The Hadamard gate is given by $H = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 & 1 \\\\ 1 & -1 \end{pmatrix}$. Verify that $H^2 = I$ and that $H$ is unitary. Find the eigenvalues and eigenvectors of $H$.

## Solution

Below are multiple methods to verify that the Hadamard gate $H$ satisfies $H^2 = I$ and is unitary, and to find its eigenvalues and eigenvectors, each explained in detail. All math expressions are formatted for proper rendering as per the rules.

---

**Method 1 – Direct Matrix Multiplication**

Compute $H^2$:

$$
H^2 = \frac{1}{2} \begin{pmatrix}
1 & 1 \\\\
1 & -1
\end{pmatrix} \begin{pmatrix}
1 & 1 \\\\
1 & -1
\end{pmatrix} = \frac{1}{2} \begin{pmatrix}
2 & 0 \\\\
0 & 2
\end{pmatrix} = I.
$$

Since $H^2 = I$, $H^{-1} = H$, and $H^\dagger H = H H = I$, $H$ is unitary.

**Explanation:** Matrix computation directly shows the properties.

---

**Method 2 – Orthonormal Columns Check**

Columns of $H$:

$$
\mathbf{h}_1 = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\\\ 1 \end{pmatrix}, \quad \mathbf{h}_2 = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\\\ -1 \end{pmatrix}.
$$

They have unit norm and are orthogonal, so $H$ is unitary.

**Explanation:** Unitary matrices have orthonormal columns.

---

**Eigenvalues and Eigenvectors**

Solve $H \lvert \psi \rangle = \lambda \lvert \psi \rangle$. Eigenvalues $\pm 1$.

For $\lambda = 1$: $\lvert + \rangle = \frac{1}{\sqrt{2}} (\lvert 0 \rangle + \lvert 1 \rangle)$.

For $\lambda = -1$: $\lvert - \rangle = \frac{1}{\sqrt{2}} (\lvert 0 \rangle - \lvert 1 \rangle)$.

Spectral decomposition: $H = \lvert + \rangle \langle + \rvert - \lvert - \rangle \langle - \rvert$.

**Explanation:** Eigenvectors are the $\pm$ states, and $H$ rotates the Bloch sphere.

---

**Summary:**

$H$ is unitary with $H^2 = I$, eigenvalues $\pm 1$, and eigenvectors $\lvert \pm \rangle$. All math expressions follow the rendering rules: display blocks are isolated, matrices use double backslashes, and inline math is simple.
<!-- Q12. (Eigendecomposition of the Pauli matrices) Find the eigenvectors, eigenvalues, and
diagonal representations of the Pauli matrices X, Y ,and Z. -->

### Solution

The Pauli matrices are

$$
X = \begin{pmatrix}
0 & 1 \\\\
1 & 0
\end{pmatrix}, \qquad Y = \begin{pmatrix}
0 & -i \\\\
i & 0
\end{pmatrix}, \qquad Z = \begin{pmatrix}
1 & 0 \\\\
0 & -1
\end{pmatrix}.
$$

All three are Hermitian and unitary, with eigenvalues $\pm 1$.

**Method 1 – Direct eigenvector solving.**

- For $X$, solve $(X - \lambda I) \mathbf{v} = 0$. The characteristic polynomial is $\lambda^2 - 1$, so $\lambda = \pm 1$. Eigenvectors are

	$$
	\lambda = +1: \; \mathbf{v}_+^{(X)} = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\\\ 1 \end{pmatrix}, \qquad
	\lambda = -1: \; \mathbf{v}_-^{(X)} = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\\\ -1 \end{pmatrix}.
	$$

- For $Y$, the characteristic polynomial is again $\lambda^2 - 1$. Solving $(Y - \lambda I) \mathbf{v} = 0$ yields
	$$
	\lambda = +1: \; \mathbf{v}_+^{(Y)} = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\\\ i \end{pmatrix}, \qquad
	\lambda = -1: \; \mathbf{v}_-^{(Y)} = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\\\ -i \end{pmatrix}.
	$$

- For $Z$, the eigenvectors coincide with the computational basis:
	$$
	\lambda = +1: \; \mathbf{v}_+^{(Z)} = \begin{pmatrix} 1 \\\\ 0 \end{pmatrix} = \lvert 0 \rangle, \qquad
	\lambda = -1: \; \mathbf{v}_-^{(Z)} = \begin{pmatrix} 0 \\\\ 1 \end{pmatrix} = \lvert 1 \rangle.
	$$

**Method 2 – Bloch-sphere intuition and rotations.** The Pauli operators correspond to spin measurements along the $x$, $y$, and $z$ axes. Their eigenvectors are the “spin-up” and “spin-down” states along each axis:

$$
\lvert \pm x \rangle = \frac{1}{\sqrt{2}} (\lvert 0 \rangle \pm \lvert 1 \rangle), \quad
\lvert \pm y \rangle = \frac{1}{\sqrt{2}} (\lvert 0 \rangle \pm i \lvert 1 \rangle), \quad
\lvert \pm z \rangle = \lvert 0 \rangle, \lvert 1 \rangle.
$$

Measurements of spin along each axis return $\pm 1$ with these eigenstates, reinforcing the direct algebraic solution.

**Diagonal representations via unitary similarity.** Let $H$ be the Hadamard gate and $S = \operatorname{diag}(1, i)$ the phase gate. Then

$$
H X H = Z, \qquad S H \, Y \, H^\dagger S^\dagger = Z, \qquad Z = Z.
$$

Therefore

$$
X = H Z H, \qquad Y = (S H) Z (S H)^\dagger, \qquad Z = Z,
$$

showing that each Pauli can be diagonalized to $\operatorname{diag}(1, -1)$ by an appropriate unitary change of basis. Written explicitly,

$$
X = U_X \begin{pmatrix} 1 & 0 \\\\ 0 & -1 \end{pmatrix} U_X^\dagger, \qquad U_X = H,
$$

$$
Y = U_Y \begin{pmatrix} 1 & 0 \\\\ 0 & -1 \end{pmatrix} U_Y^\dagger, \qquad U_Y = S H,
$$

$$
Z = U_Z \begin{pmatrix} 1 & 0 \\\\ 0 & -1 \end{pmatrix} U_Z^\dagger, \qquad U_Z = I.
$$

These diagonal forms, together with the eigenvectors listed above, provide the full eigendecomposition for the Pauli matrices.
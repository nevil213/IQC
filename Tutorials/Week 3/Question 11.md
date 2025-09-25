<!-- Q11. The Hadamard gate is given by:
H =
1
√
2

1 1
1 −1

.
Verify that H2 = I and that H is unitary. Find the eigenvalues and eigenvectors of
H. -->

### Solution

The Hadamard gate is

$$
H = \frac{1}{\sqrt{2}} \begin{pmatrix}
1 & 1 \\\\
1 & -1
\end{pmatrix}.
$$

**Method 1 – Direct matrix multiplication.** Compute

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

Since $H^2 = I$, $H^{-1} = H$. Moreover,

$$
H^\dagger H = H H = I,
$$

so $H$ is unitary.

**Method 2 – Orthonormal columns check.** The columns of $H$ are

$$
\mathbf{h}_1 = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\\\ 1 \end{pmatrix}, \qquad \mathbf{h}_2 = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\\\ -1 \end{pmatrix}.
$$

They satisfy $\lVert \mathbf{h}_1 \rVert = \lVert \mathbf{h}_2 \rVert = 1$ and $\langle \mathbf{h}_1, \mathbf{h}_2 \rangle = 0$. A matrix with orthonormal columns is unitary, so $H$ is unitary without needing to square it explicitly.

**Eigenvalues and eigenvectors.** Solve $H \lvert \psi \rangle = \lambda \lvert \psi \rangle$. Because $H^2 = I$, the minimal polynomial divides $x^2 - 1$, so eigenvalues are $\lambda = \pm 1$.

For $\lambda = 1$ solve $(H - I) \lvert \psi \rangle = 0$:

$$
H - I = \frac{1}{\sqrt{2}} \begin{pmatrix}
1 & 1 \\\\
1 & -1
\end{pmatrix} - \begin{pmatrix}
1 & 0 \\\\
0 & 1
\end{pmatrix} = \begin{pmatrix}
\frac{1}{\sqrt{2}} - 1 & \frac{1}{\sqrt{2}} \\\\
\frac{1}{\sqrt{2}} & -\frac{1}{\sqrt{2}} - 1
\end{pmatrix}.
$$

The null space is spanned by $\lvert + \rangle = \frac{1}{\sqrt{2}} (\lvert 0 \rangle + \lvert 1 \rangle)$, so $H \lvert + \rangle = \lvert + \rangle$.

For $\lambda = -1$ solve $(H + I) \lvert \psi \rangle = 0$:

$$
H + I = \frac{1}{\sqrt{2}} \begin{pmatrix}
1 & 1 \\\\
1 & -1
\end{pmatrix} + \begin{pmatrix}
1 & 0 \\\\
0 & 1
\end{pmatrix} = \begin{pmatrix}
\frac{1}{\sqrt{2}} + 1 & \frac{1}{\sqrt{2}} \\\\
\frac{1}{\sqrt{2}} & -\frac{1}{\sqrt{2}} + 1
\end{pmatrix}.
$$

The null space is spanned by $\lvert - \rangle = \frac{1}{\sqrt{2}} (\lvert 0 \rangle - \lvert 1 \rangle)$, giving $H \lvert - \rangle = - \lvert - \rangle$.

Thus

$$
H = \lvert + \rangle \langle + \rvert - \lvert - \rangle \langle - \rvert,
$$

providing its spectral decomposition. Geometrically, $H$ maps computational-basis vectors to $\lvert \pm \rangle$ and acts as a rotation by $\pi$ about the $X+Z$ axis on the Bloch sphere.
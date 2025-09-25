The Pauli matrices X, Y, and Z all have eigenvalues +1 and −1. Their eigenvectors are the quantum states pointing along the ±x, ±y, and ±z directions on the Bloch sphere. Each Pauli matrix can be written in its diagonal form M = U D U†, where D = diag(1, −1) and the columns of U are the normalized eigenvectors.

---

### Q12. (Eigendecomposition of the Pauli matrices)

The Pauli matrices:
$$
X=\begin{pmatrix}0&1\\[4pt]1&0\end{pmatrix},\qquad
Y=\begin{pmatrix}0&-i\\[4pt]i&0\end{pmatrix},\qquad
Z=\begin{pmatrix}1&0\\[4pt]0&-1\end{pmatrix}.
$$

1. Finding eigenvalues and eigenvectors

Eigenvalues:
All Pauli matrices satisfy $\sigma^2=I$. If $\sigma|\psi\rangle=\lambda|\psi\rangle$, then $\lambda^2=1$, so $\lambda=\pm1$.

Eigenvectors (normalized):
- Z:
    - $\lambda=+1$: $|0\rangle=\begin{pmatrix}1\\[4pt]0\end{pmatrix}$
    - $\lambda=-1$: $|1\rangle=\begin{pmatrix}0\\[4pt]1\end{pmatrix}$
- X:
    - $\lambda=+1$: $|+\rangle=\tfrac{1}{\sqrt{2}}(|0\rangle+|1\rangle)=\tfrac{1}{\sqrt{2}}\begin{pmatrix}1\\[4pt]1\end{pmatrix}$
    - $\lambda=-1$: $|-\rangle=\tfrac{1}{\sqrt{2}}(|0\rangle-|1\rangle)=\tfrac{1}{\sqrt{2}}\begin{pmatrix}1\\[4pt]-1\end{pmatrix}$
- Y:
    - $\lambda=+1$: $|i\rangle=\tfrac{1}{\sqrt{2}}(|0\rangle+i|1\rangle)=\tfrac{1}{\sqrt{2}}\begin{pmatrix}1\\[4pt]i\end{pmatrix}$
    - $\lambda=-1$: $|-i\rangle=\tfrac{1}{\sqrt{2}}(|0\rangle-i|1\rangle)=\tfrac{1}{\sqrt{2}}\begin{pmatrix}1\\[4pt]-i\end{pmatrix}$

Summary table:

| Matrix | Eigenvalue | Ket | Column vector |
|:------:|:----------:|:---:|:-------------:|
| Z | +1 | \|0&rang; | $\begin{pmatrix}1\\[4pt]0\end{pmatrix}$ |
| Z | −1 | \|1&rang; | $\begin{pmatrix}0\\[4pt]1\end{pmatrix}$ |
| X | +1 | \|+&rang; | $\tfrac{1}{\sqrt{2}}\begin{pmatrix}1\\[4pt]1\end{pmatrix}$ |
| X | −1 | \|-&rang; | $\tfrac{1}{\sqrt{2}}\begin{pmatrix}1\\[4pt]-1\end{pmatrix}$ |
| Y | +1 | \|i&rang; | $\tfrac{1}{\sqrt{2}}\begin{pmatrix}1\\[4pt]i\end{pmatrix}$ |
| Y | −1 | \|-i&rang; | $\tfrac{1}{\sqrt{2}}\begin{pmatrix}1\\[4pt]-i\end{pmatrix}$ |

2. Diagonal representations

The common diagonal matrix (with +1 first) is
$$
D=\begin{pmatrix}1&0\\[4pt]0&-1\end{pmatrix}.
$$

Unitary matrices whose columns are the eigenvectors:

- For Z: $U_Z=I$, so
    $$
    Z=I\,D\,I^\dagger.
    $$

- For X: columns $|+\rangle,|-\rangle$ give the Hadamard
    $$
    U_X=H=\frac{1}{\sqrt{2}}\begin{pmatrix}1&1\\[4pt]1&-1\end{pmatrix},
    \qquad X=H\,D\,H^\dagger.
    $$

- For Y: columns $|i\rangle,|-i\rangle$ give
    $$
    U_Y=\frac{1}{\sqrt{2}}\begin{pmatrix}1&1\\[4pt]i&-i\end{pmatrix},
    \qquad Y=U_Y\,D\,U_Y^\dagger.
    $$

Each decomposition expresses the Pauli operator in the basis of its eigenvectors.

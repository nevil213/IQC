# 7. Let $B = \begin{pmatrix} 0 & 1 + i \\\\ 1 - i & 0 \end{pmatrix}$. Show that $B$ is Hermitian.

## Solution

The matrix is defined as:

$$
B = \begin{pmatrix} 0 & 1 + i \\\\ 1 - i & 0 \end{pmatrix}
$$

To check if Hermitian, compute $B^\dagger$, the conjugate transpose.

First, transpose $B$:

$$
B^T = \begin{pmatrix} 0 & 1 - i \\\\ 1 + i & 0 \end{pmatrix}
$$

Now, take the complex conjugate:

$$
B^\dagger = \begin{pmatrix} 0 & {1 - i} \\\\ {1 + i} & 0 \end{pmatrix}^* = \begin{pmatrix} 0 & 1 + i \\\\ 1 - i & 0 \end{pmatrix} = B
$$

Since $B^\dagger = B$, the matrix is Hermitian.

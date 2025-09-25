<!-- 6. Show that the Pauli matrices are Hermitian and unitary. -->

## Solution

The Pauli matrices are:
$$
X = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}, \quad Y = \begin{pmatrix} 0 & -i \\ i & 0 \end{pmatrix}, \quad Z = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}
$$

### Hermitian Property

A matrix is Hermitian if $ A^\dagger = A $, where $ A^\dagger $ is the conjugate transpose.

For $ X $:
$$
X^\dagger = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix} = X
$$

For $ Y $:
$$
Y^\dagger = \begin{pmatrix} 0 & i \\ -i & 0 \end{pmatrix}^\dagger = \begin{pmatrix} 0 & -i \\ i & 0 \end{pmatrix} = Y
$$

For $ Z $:
$$
Z^\dagger = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix} = Z
$$

Thus, all Pauli matrices are Hermitian.

### Unitary Property

A matrix is unitary if $ U^\dagger U = I $.

For $ X $:
$$
X^\dagger X = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I
$$

For $ Y $:
$$
Y^\dagger Y = \begin{pmatrix} 0 & -i \\ i & 0 \end{pmatrix} \begin{pmatrix} 0 & -i \\ i & 0 \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I
$$

For $ Z $:
$$
Z^\dagger Z = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix} \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I
$$

Thus, all Pauli matrices are unitary.

# 10. Calculate the matrix representation of the tensor products of the Pauli operators: (a) $X \otimes Z$, (b) $I \otimes X$, (c) $X \otimes I$. Is the tensor product commutative?

## Solution

The Pauli matrices are defined as:

$$
I = \begin{pmatrix} 1 & 0 \\\\ 0 & 1 \end{pmatrix}, \quad X = \begin{pmatrix} 0 & 1 \\\\ 1 & 0 \end{pmatrix}, \quad Z = \begin{pmatrix} 1 & 0 \\\\ 0 & -1 \end{pmatrix}
$$

The Kronecker product $A \otimes B$ for 2×2 matrices results in a 4×4 matrix.

### (a) $X \otimes Z$

$$
X \otimes Z = \begin{pmatrix} 0 \cdot Z & 1 \cdot Z \\\\ 1 \cdot Z & 0 \cdot Z \end{pmatrix} = \begin{pmatrix} \begin{pmatrix} 0 & 0 \\\\ 0 & 0 \end{pmatrix} & \begin{pmatrix} 1 & 0 \\\\ 0 & -1 \end{pmatrix} \\\\ \begin{pmatrix} 1 & 0 \\\\ 0 & -1 \end{pmatrix} & \begin{pmatrix} 0 & 0 \\\\ 0 & 0 \end{pmatrix} \end{pmatrix} = \begin{pmatrix}
0 & 0 & 1 & 0 \\\\
0 & 0 & 0 & -1 \\\\
1 & 0 & 0 & 0 \\\\
0 & -1 & 0 & 0
\end{pmatrix}
$$

### (b) $I \otimes X$

$$
I \otimes X = \begin{pmatrix} 1 \cdot X & 0 \cdot X \\\\ 0 \cdot X & 1 \cdot X \end{pmatrix} = \begin{pmatrix} \begin{pmatrix} 0 & 1 \\\\ 1 & 0 \end{pmatrix} & \begin{pmatrix} 0 & 0 \\\\ 0 & 0 \end{pmatrix} \\\\ \begin{pmatrix} 0 & 0 \\\\ 0 & 0 \end{pmatrix} & \begin{pmatrix} 0 & 1 \\\\ 1 & 0 \end{pmatrix} \end{pmatrix} = \begin{pmatrix}
0 & 1 & 0 & 0 \\\\
1 & 0 & 0 & 0 \\\\
0 & 0 & 0 & 1 \\\\
0 & 0 & 1 & 0
\end{pmatrix}
$$

### (c) $X \otimes I$

$$
X \otimes I = \begin{pmatrix} 0 \cdot I & 1 \cdot I \\\\ 1 \cdot I & 0 \cdot I \end{pmatrix} = \begin{pmatrix} \begin{pmatrix} 0 & 0 \\\\ 0 & 0 \end{pmatrix} & \begin{pmatrix} 1 & 0 \\\\ 0 & 1 \end{pmatrix} \\\\ \begin{pmatrix} 1 & 0 \\\\ 0 & 1 \end{pmatrix} & \begin{pmatrix} 0 & 0 \\\\ 0 & 0 \end{pmatrix} \end{pmatrix} = \begin{pmatrix}
0 & 0 & 1 & 0 \\\\
0 & 0 & 0 & 1 \\\\
1 & 0 & 0 & 0 \\\\
0 & 1 & 0 & 0
\end{pmatrix}
$$

### Is the tensor product commutative?

Compare $I \otimes X$ and $X \otimes I$: they are different matrices, so the tensor product is not commutative.

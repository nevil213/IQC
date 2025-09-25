# 4. Verify that the Pauli matrices X and Y anticommute, i.e., $XY = -YX$.

## Solution

The Pauli matrices are defined as:

$$
X = \begin{pmatrix} 0 & 1 \\\\ 1 & 0 \end{pmatrix}, \quad Y = \begin{pmatrix} 0 & -i \\\\ i & 0 \end{pmatrix}, \quad Z = \begin{pmatrix} 1 & 0 \\\\ 0 & -1 \end{pmatrix}
$$

Compute $XY$:

$$
XY = \begin{pmatrix} 0 & 1 \\\\ 1 & 0 \end{pmatrix} \begin{pmatrix} 0 & -i \\\\ i & 0 \end{pmatrix} = \begin{pmatrix} 0 \cdot 0 + 1 \cdot i & 0 \cdot (-i) + 1 \cdot 0 \\\\ 1 \cdot 0 + 0 \cdot i & 1 \cdot (-i) + 0 \cdot 0 \end{pmatrix} = \begin{pmatrix} i & 0 \\\\ 0 & -i \end{pmatrix} = i Z
$$

Compute $YX$:

$$
YX = \begin{pmatrix} 0 & -i \\\\ i & 0 \end{pmatrix} \begin{pmatrix} 0 & 1 \\\\ 1 & 0 \end{pmatrix} = \begin{pmatrix} 0 \cdot 0 + (-i) \cdot 1 & 0 \cdot 1 + (-i) \cdot 0 \\\\ i \cdot 0 + 0 \cdot 1 & i \cdot 1 + 0 \cdot 0 \end{pmatrix} = \begin{pmatrix} -i & 0 \\\\ 0 & i \end{pmatrix} = -i Z
$$

Therefore, $XY = i Z$, $YX = -i Z$, so $XY = -YX$.

Thus, X and Y anticommute.

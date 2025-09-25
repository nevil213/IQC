<!-- 1. Show that the set {(1,1),(1,−1)} is linearly independent in R2. -->

## Solution

A set of vectors is linearly independent if the only solution to the equation $a \mathbf{v}_1 + b \mathbf{v}_2 = \mathbf{0}$ is $a = 0$, $b = 0$.

The vectors are defined as:

$$
\mathbf{v}_1 = (1, 1), \quad \mathbf{v}_2 = (1, -1)
$$

Assume $a(1, 1) + b(1, -1) = (0, 0)$.

This gives the system:

$$
a + b = 0 \\
a - b = 0
$$

Adding the equations: $2a = 0$ ⇒ $a = 0$.

Substituting into the first equation: $0 + b = 0$ ⇒ $b = 0$.

Thus, the only solution is $a = 0$, $b = 0$, so the set is linearly independent.

### Alternative Method: Determinant

Form the matrix with the vectors as columns:

$$
\begin{pmatrix}
1 & 1 \\\\
1 & -1
\end{pmatrix}
$$

The determinant is $1 \cdot (-1) - 1 \cdot 1 = -1 - 1 = -2 \neq 0$.

Since the determinant is non-zero, the vectors are linearly independent.

### Alternative Method: Rank

The rank of the matrix above is 2 (full rank for 2×2), so the vectors span $\mathbb{R}^2$ and are independent.

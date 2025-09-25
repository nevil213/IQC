<!-- 8. Let V be the subspace of R3spanned by {(1,0,1),(0,1,1),(1,1,2)}. Find a basis
for V and compute its dimension. -->

## Solution

The vectors are:
\[
\mathbf{v}_1 = (1, 0, 1), \quad \mathbf{v}_2 = (0, 1, 1), \quad \mathbf{v}_3 = (1, 1, 2)
\]

Notice that \( \mathbf{v}_3 = \mathbf{v}_1 + \mathbf{v}_2 \):
\[
(1, 0, 1) + (0, 1, 1) = (1, 1, 2)
\]

Thus, \( \mathbf{v}_3 \) is a linear combination of \( \mathbf{v}_1 \) and \( \mathbf{v}_2 \), so the span is the same as span{ \( \mathbf{v}_1, \mathbf{v}_2 \) }.

To check if \( \mathbf{v}_1 \) and \( \mathbf{v}_2 \) are linearly independent, assume \( a \mathbf{v}_1 + b \mathbf{v}_2 = \mathbf{0} \):
\[
a(1, 0, 1) + b(0, 1, 1) = (0, 0, 0)
\]
\[
(a, b, a + b) = (0, 0, 0)
\]
So \( a = 0 \), \( b = 0 \), \( a + b = 0 \), yes.

Thus, a basis for V is { \( \mathbf{v}_1, \mathbf{v}_2 \) }, and the dimension is 2.

### Alternative Method: Row Reduction

Form the matrix with the vectors as rows:
\[
\begin{pmatrix}
1 & 0 & 1 \\
0 & 1 & 1 \\
1 & 1 & 2
\end{pmatrix}
\]

Row reduce:
Subtract row 1 from row 3:
\[
\begin{pmatrix}
1 & 0 & 1 \\
0 & 1 & 1 \\
0 & 1 & 1
\end{pmatrix}
\]

Subtract row 2 from row 3:
\[
\begin{pmatrix}
1 & 0 & 1 \\
0 & 1 & 1 \\
0 & 0 & 0
\end{pmatrix}
\]

Rank is 2, so dimension 2. Basis: first two rows.
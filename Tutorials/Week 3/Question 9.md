<!-- Q9. Basis change: Suppose A′ and A′′ are matrix representations of an operator A on a
vector space V with respect to two different orthonormal bases {|vi⟩} and {|wi⟩}.
Derive the relationship between A′ and A′′
. -->

### Solution

Let $A$ be a linear operator on a finite-dimensional Hilbert space $V$. Denote by $A'$ its matrix representation in the orthonormal basis $\{\lvert v_i \rangle\}$ and by $A''$ the representation in the orthonormal basis $\{\lvert w_i \rangle\}$.

**Method 1 – Unitary change-of-basis matrix.** Define the unitary matrix $S$ whose columns are the coordinates of the $\lvert w_i \rangle$ vectors expressed in the $\{\lvert v_i \rangle\}$ basis:

$$
S_{ij} = \langle v_i \vert w_j \rangle.
$$

Then

$$
\lvert w_j \rangle = \sum_i S_{ij} \lvert v_i \rangle.
$$

For any vector with coordinate column $\mathbf{x}$ in the $\{\lvert v_i \rangle\}$ basis, the coordinates in the $\{\lvert w_i \rvert\}$ basis are $\mathbf{x}'' = S^\dagger \mathbf{x}$. Acting with $A$ and translating between coordinates yields

$$
A'' = S^\dagger A' S.
$$

**Method 2 – Dirac notation derivation.** The matrix elements of $A$ in the two bases are

$$
A'_{ij} = \langle v_i \vert A \vert v_j \rangle, \qquad A''_{ij} = \langle w_i \vert A \vert w_j \rangle.
$$

Insert resolutions of the identity in the $\{\lvert v_k \rangle\}$ basis:

$$
A''_{ij} = \sum_{k,\ell} \langle w_i \vert v_k \rangle \langle v_k \vert A \vert v_\ell \rangle \langle v_\ell \vert w_j \rangle = \sum_{k,\ell} S_{ki}^* A'_{k \ell} S_{\ell j},
$$

which is exactly the $(i,j)$ entry of $S^\dagger A' S$.

**Method 3 – Coordinate transformation of vectors.** Write the coordinate isomorphisms $\Phi_v : V \to \mathbb{C}^n$ and $\Phi_w : V \to \mathbb{C}^n$ associated with the two bases. They are related by $\Phi_w = S^\dagger \Phi_v$. The matrix representations satisfy

$$
\Phi_v \circ A = A' \circ \Phi_v, \qquad \Phi_w \circ A = A'' \circ \Phi_w.
$$

Substituting $\Phi_w = S^\dagger \Phi_v$ and rearranging yields $A'' = S^\dagger A' S$ once more. This categorical viewpoint emphasizes that similarity transformations encode basis changes.

Therefore the matrix representations are related by a unitary similarity transformation determined by the change-of-basis matrix between the two orthonormal bases.

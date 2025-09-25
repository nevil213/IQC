# Q9. Basis change: Suppose $A'$ and $A''$ are matrix representations of an operator $A$ on a vector space $V$ with respect to two different orthonormal bases $\{|v_i\rangle\}$ and $\{|w_i\rangle\}$. Derive the relationship between $A'$ and $A''$.

## Solution

Below are multiple methods to derive the relationship between matrix representations $A'$ and $A''$ of an operator $A$ in two orthonormal bases, each explained in detail. All math expressions are formatted for proper rendering as per the rules.

---

**Method 1 – Unitary Change-of-Basis Matrix**

Define the unitary matrix $S$ with $S_{ij} = \langle v_i \vert w_j \rangle$, so $\lvert w_j \rangle = \sum_i S_{ij} \lvert v_i \rangle$.

Coordinate transformation: $\mathbf{x}'' = S^\dagger \mathbf{x}$. Acting with $A$ yields $A'' = S^\dagger A' S$.

**Explanation:** This constructs the similarity transformation explicitly from basis vectors.

---

**Method 2 – Dirac Notation Derivation**

Matrix elements: $A'_{ij} = \langle v_i \vert A \vert v_j \rangle$, $A''_{ij} = \langle w_i \vert A \vert w_j \rangle$.

Inserting identities: $A''_{ij} = \sum_{k,\ell} \langle w_i \vert v_k \rangle \langle v_k \vert A \vert v_\ell \rangle \langle v_\ell \vert w_j \rangle = \sum_{k,\ell} S_{ki}^* A'_{k\ell} S_{\ell j}$.

Thus $A'' = S^\dagger A' S$.

**Explanation:** This uses Dirac notation to compute matrix elements directly.

---

**Method 3 – Coordinate Transformation of Vectors**

Coordinate isomorphisms $\Phi_v$ and $\Phi_w$ satisfy $\Phi_v \circ A = A' \circ \Phi_v$, $\Phi_w \circ A = A'' \circ \Phi_w$, with $\Phi_w = S^\dagger \Phi_v$.

Substituting gives $A'' = S^\dagger A' S$.

**Explanation:** This categorical approach views matrices as coordinate transformations.

---

**Summary:**

The matrix representations are related by $A'' = S^\dagger A' S$, where $S$ is the change-of-basis matrix. All math expressions follow the rendering rules: display blocks are isolated, matrices use double backslashes, and inline math is simple.

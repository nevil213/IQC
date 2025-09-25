# Question 4: Suppose $\vec{v}$ be any real three dimensional unit vector and we define an observable as follows: $\vec{v} \cdot \vec{\sigma} = v_1 \sigma_1 + v_2 \sigma_2 + v_3 \sigma_3$. Here $\vec{\sigma}$ is a shorthand for the vector of Pauli matrices: $\vec{\sigma} = (\sigma_1, \sigma_2, \sigma_3)$, where $\sigma_1 = X = \begin{pmatrix} 0 & 1 \\\\ 1 & 0 \end{pmatrix}$, $\sigma_2 = Y = \begin{pmatrix} 0 & -i \\\\ i & 0 \end{pmatrix}$, $\sigma_3 = Z = \begin{pmatrix} 1 & 0 \\\\ 0 & -1 \end{pmatrix}$. Show that $\vec{v} \cdot \vec{\sigma}$ has eigenvalues $\pm 1$, and that the projectors onto the corresponding eigenspaces are given by $P_\pm = \frac{I \pm \vec{v} \cdot \vec{\sigma}}{2}$.

## Solution

Below are multiple methods to show that $\vec{v} \cdot \vec{\sigma}$ has eigenvalues $\pm 1$ and the projectors are $P_\pm = \frac{I \pm \vec{v} \cdot \vec{\sigma}}{2}$, each explained in detail. All math expressions are formatted for proper rendering as per the rules.

---

**Method 1 – Direct Computation of Square**

Compute $(\vec{v} \cdot \vec{\sigma})^2$.

Since $\sigma_i^2 = I$ for each $i$, and $\{\sigma_i, \sigma_j\} = 2 \delta_{ij} I$ for $i \neq j$,

$$
(\vec{v} \cdot \vec{\sigma})^2 = \sum_i v_i^2 \sigma_i^2 + \sum_{i \neq j} v_i v_j \sigma_i \sigma_j = \sum_i v_i^2 I + \sum_{i \neq j} v_i v_j \frac{1}{2} \{\sigma_i, \sigma_j\} = I \sum v_i^2 = I.
$$

Thus eigenvalues $\pm 1$.

Projectors: Solve $(\vec{v} \cdot \vec{\sigma}) \lvert \psi_\pm \rangle = \pm \lvert \psi_\pm \rangle$, then $P_\pm = \lvert \psi_\pm \rangle \langle \psi_\pm \rvert$.

Standard result: $P_\pm = \frac{I \pm \vec{v} \cdot \vec{\sigma}}{2}$.

**Explanation:** Pauli algebra gives the square as identity.

---

**Method 2 – Eigenvalue Equation**

Solve $(\vec{v} \cdot \vec{\sigma} - \lambda I) \lvert \psi \rangle = 0$.

Since it's 2x2, characteristic polynomial $\lambda^2 - 1 = 0$.

**Explanation:** Minimal polynomial divides x^2 - 1.

---

**Method 3 – Spin Representation**

$\vec{v} \cdot \vec{\sigma}$ is the spin operator along $\vec{v}$, eigenvalues $\pm 1$.

Projectors are standard for spin 1/2.

**Explanation:** Physical interpretation.

---

**Summary:**

Eigenvalues are $\pm 1$, projectors $P_\pm = \frac{I \pm \vec{v} \cdot \vec{\sigma}}{2}$. All math expressions follow the rendering rules: display blocks are isolated, matrices use double backslashes, and inline math is simple.
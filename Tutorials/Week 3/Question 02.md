The Gram-Schmidt procedure is guaranteed to produce an orthonormal basis because each step is explicitly designed to remove any components of a vector that are parallel to the previously processed vectors, leaving only the orthogonal part, which is then normalized. This ensures orthogonality and normality by construction, while the process of linear combination ensures the new basis spans the same space as the original.

***

### **Q2. Prove that the Gram–Schmidt procedure produces an orthonormal basis.**

To prove that the set $\{|e_1\rangle, \dots, |e_n\rangle\}$ produced by the Gram-Schmidt procedure is an orthonormal basis, we must demonstrate three properties:
1.  **Orthogonality**: The vectors are mutually perpendicular ($\langle e_i | e_j \rangle = 0$ for $i \neq j$).
2.  **Normality**: Each vector has a length of one ($\langle e_i | e_i \rangle = 1$).
3.  **Spanning**: The new set spans the same subspace as the original set.

The procedure is defined by the iterative formula:

$$|w_k\rangle = |v_k\rangle - \sum_{j=1}^{k-1} \langle e_j | v_k \rangle |e_j\rangle \quad \text{and} \quad |e_k\rangle = \frac{|w_k\rangle}{\||w_k\rangle\|}$$

---

## **Solution 1: Proof by Mathematical Induction**

This rigorous method proves each property step-by-step.

### **1. Proving Orthogonality**
We'll use induction to show that the set $\{|e_1\rangle, \dots, |e_k\rangle\}$ is orthogonal for any $k$.

* **Base Case (k=2):** We must show that $|e_2\rangle$ is orthogonal to $|e_1\rangle$. This is equivalent to showing $\langle e_1 | w_2 \rangle = 0$.
    $$
    \langle e_1 | w_2 \rangle = \langle e_1 | \left( |v_2\rangle - \langle e_1 | v_2 \rangle |e_1\rangle \right)
    $$
    $$
    = \langle e_1 | v_2 \rangle - \langle e_1 | v_2 \rangle \langle e_1 | e_1 \rangle
    $$
    Since $|e_1\rangle$ is normalized, $\langle e_1 | e_1 \rangle = 1$.
    $$
    \langle e_1 | w_2 \rangle = \langle e_1 | v_2 \rangle - \langle e_1 | v_2 \rangle = 0
    $$
    The base case holds.

* **Inductive Hypothesis:** Assume that the set $\{|e_1\rangle, \dots, |e_{k-1}\rangle\}$ is orthonormal.

* **Inductive Step:** We must show that the newly constructed vector $|w_k\rangle$ is orthogonal to all previous vectors $|e_j\rangle$ for $j < k$.
    $$
    \langle e_j | w_k \rangle = \left\langle e_j \left| \left( |v_k\rangle - \sum_{i=1}^{k-1} \langle e_i | v_k \rangle |e_i\rangle \right) \right. \right\rangle
    $$
    $$
    = \langle e_j | v_k \rangle - \sum_{i=1}^{k-1} \langle e_i | v_k \rangle \langle e_j | e_i \rangle
    $$
    By our hypothesis, the set $\{|e_i\rangle\}$ is orthonormal, so $\langle e_j | e_i \rangle = \delta_{ji}$. The only term in the sum that survives is when $i=j$.
    $$
    \langle e_j | w_k \rangle = \langle e_j | v_k \rangle - \langle e_j | v_k \rangle \langle e_j | e_j \rangle = \langle e_j | v_k \rangle - \langle e_j | v_k \rangle = 0
    $$
    This proves orthogonality by induction.

### **2. Proving Normality**
This property is true **by construction**. The final action in every step of the algorithm is to normalize the vector $|w_k\rangle$:
$$|e_k\rangle = \frac{|w_k\rangle}{\||w_k\rangle\|}$$
By definition, the resulting vector $|e_k\rangle$ has a norm of 1, so $\langle e_k | e_k \rangle = 1$.

### **3. Proving Spanning**
We must show that the new basis spans the same space as the old one. We do this by showing that each new basis vector can be written as a combination of the old ones, and vice-versa.
* The formula for $|e_k\rangle$ is a linear combination of $|v_k\rangle$ and the previous $\{|e_j\rangle\}_{j<k}$. By induction, this means every $|e_k\rangle$ is a linear combination of $\{|v_1\rangle, \dots, |v_k\rangle\}$.
* We can rearrange the formula to solve for $|v_k\rangle$:
    $$
    |v_k\rangle = |w_k\rangle + \sum_{j=1}^{k-1} \langle e_j | v_k \rangle |e_j\rangle = \||w_k\rangle\||e_k\rangle + \sum_{j=1}^{k-1} \langle e_j | v_k \rangle |e_j\rangle
    $$
    This shows that every $|v_k\rangle$ is a linear combination of $\{|e_1\rangle, \dots, |e_k\rangle\}$.

Since each set of vectors can be constructed from the other, they must span the same subspace.

---

## **Solution 2: Proof by Geometric Interpretation**

This proof is more conceptual and relies on the geometric meaning of the procedure's core operation. 

### **1. Proving Orthogonality**
Let $U_{k-1} = \text{span}\{|e_1\rangle, \dots, |e_{k-1}\rangle\}$ be the subspace spanned by the first $k-1$ orthonormal vectors. The term
$$|\text{proj}_{U_{k-1}} |v_k\rangle \rangle = \sum_{j=1}^{k-1} \langle e_j | v_k \rangle |e_j\rangle$$
is the **orthogonal projection** of $|v_k\rangle$ onto the subspace $U_{k-1}$. It represents the "shadow" of $|v_k\rangle$ in that subspace.

The Gram-Schmidt formula for the unnormalized vector $|w_k\rangle$ is:

$$|w_k\rangle = |v_k\rangle - |\text{proj}_{U_{k-1}} |v_k\rangle \rangle$$

By the fundamental definition of an orthogonal projection, the vector that remains after subtracting the projection ($|w_k\rangle$) is **guaranteed to be orthogonal to every vector in the subspace** $U_{k-1}$. Therefore, $|w_k\rangle$ (and its normalized version $|e_k\rangle$) is orthogonal to all previous vectors in the set by construction.

### **2. Normality and Spanning**
The arguments for why the resulting set is normalized and spans the same space are algebraic in nature and are the same as those presented in Solution 1.
### **Q2. Prove that the Gram–Schmidt procedure produces an orthonormal basis.**

To prove that the set of vectors $\{|e_1\rangle, |e_2\rangle, \dots, |e_n\rangle\}$ produced by the Gram-Schmidt procedure is an **orthonormal basis** for the subspace spanned by the original vectors $\{|v_1\rangle, |v_2\rangle, \dots, |v_n\rangle\}$, we must demonstrate three key properties:

1.  **Orthogonality**: The vectors are mutually perpendicular, i.e., $\langle e_i | e_j \rangle = 0$ for $i \neq j$.
2.  **Normality**: Each vector has a length of 1, i.e., $\langle e_i | e_i \rangle = 1$.
3.  **Spanning**: The new set spans the same subspace as the original set.

We'll use the standard Gram-Schmidt construction for the proof:

$$|w_k\rangle = |v_k\rangle - \sum_{j=1}^{k-1} \langle e_j | v_k \rangle |e_j\rangle \quad \text{and} \quad |e_k\rangle = \frac{|w_k\rangle}{\||w_k\rangle\|}$$

---

## **Solution 1: Proof by Mathematical Induction**

This is the most common and rigorous way to prove the properties of the Gram-Schmidt procedure. We will tackle each of the three properties separately.

### **Part 1: Proving Orthogonality**

We will use induction to prove that the set $\{|e_1\rangle, \dots, |e_k\rangle\}$ is orthogonal for any $k$. Since normalization doesn't change the direction (and thus orthogonality), it's sufficient to prove that the intermediate set $\{|w_1\rangle, \dots, |w_k\rangle\}$ is orthogonal.

**Base Case (k=2):**
We must show that $|w_1\rangle$ is orthogonal to $|w_2\rangle$. Let's compute their inner product:

$$\langle w_1 | w_2 \rangle = \langle w_1 | \left( |v_2\rangle - \langle e_1 | v_2 \rangle |e_1\rangle \right) \rangle$$

Using the linearity of the inner product:

$$\langle w_1 | w_2 \rangle = \langle w_1 | v_2 \rangle - \langle e_1 | v_2 \rangle \langle w_1 | e_1 \rangle$$

We know that $|w_1\rangle = |v_1\rangle$ and $|e_1\rangle = \frac{|w_1\rangle}{\||w_1\rangle\|}$. Substituting $|w_1\rangle = \||w_1\rangle\| |e_1\rangle$:

$$\langle w_1 | w_2 \rangle = \||w_1\rangle\| \langle e_1 | v_2 \rangle - \langle e_1 | v_2 \rangle \left( \||w_1\rangle\| \langle e_1 | e_1 \rangle \right)$$

Since $|e_1\rangle$ is normalized, $\langle e_1 | e_1 \rangle = 1$.

$$\langle w_1 | w_2 \rangle = \||w_1\rangle\| \langle e_1 | v_2 \rangle - \langle e_1 | v_2 \rangle \||w_1\rangle\| = 0$$

The base case holds: $|w_1\rangle$ and $|w_2\rangle$ are orthogonal.

**Inductive Hypothesis:**
Assume that the set $\{|e_1\rangle, \dots, |e_{k-1}\rangle\}$ is orthonormal.

**Inductive Step:**
We need to show that the newly constructed vector $|w_k\rangle$ is orthogonal to all previous vectors $|e_j\rangle$ where $j < k$. Let's compute the inner product $\langle e_j | w_k \rangle$ for an arbitrary $j < k$.

$$\langle e_j | w_k \rangle = \left\langle e_j \left| \left( |v_k\rangle - \sum_{i=1}^{k-1} \langle e_i | v_k \rangle |e_i\rangle \right) \right. \right\rangle$$

Again, using linearity:

$$\langle e_j | w_k \rangle = \langle e_j | v_k \rangle - \sum_{i=1}^{k-1} \langle e_i | v_k \rangle \langle e_j | e_i \rangle$$

According to our **inductive hypothesis**, the set $\{|e_1\rangle, \dots, |e_{k-1}\rangle\}$ is orthonormal. This means $\langle e_j | e_i \rangle = \delta_{ji}$ (it is 1 if $j=i$ and 0 otherwise). Therefore, in the summation, the only term that survives is the one where $i=j$.

$$\langle e_j | w_k \rangle = \langle e_j | v_k \rangle - \langle e_j | v_k \rangle \langle e_j | e_j \rangle$$

Since $\langle e_j | e_j \rangle = 1$:

$$\langle e_j | w_k \rangle = \langle e_j | v_k \rangle - \langle e_j | v_k \rangle = 0$$

This proves that $|w_k\rangle$ is orthogonal to all $|e_j\rangle$ (and thus all $|w_j\rangle$) for $j < k$. By induction, the entire set $\{|w_1\rangle, \dots, |w_n\rangle\}$ is orthogonal.

### **Part 2: Proving Normality**

This part is true **by construction**. The final step of the algorithm for each vector is normalization:

$$|e_k\rangle = \frac{|w_k\rangle}{\||w_k\rangle\|}$$

The norm of $|e_k\rangle$ is:

$$\||e_k\rangle\| = \left\| \frac{|w_k\rangle}{\||w_k\rangle\|} \right\| = \frac{1}{\||w_k\rangle\|} \||w_k\rangle\| = 1$$

The squared norm is $\langle e_k | e_k \rangle = 1$. This holds for all $k$. ✅

### **Part 3: Proving Spanning**

We must show that the subspace spanned by the original vectors is the same as the subspace spanned by the new vectors. Let $V_k = \text{span}\{|v_1\rangle, \dots, |v_k\rangle\}$ and $E_k = \text{span}\{|e_1\rangle, \dots, |e_k\rangle\}$. We will show by induction that $V_k = E_k$ for all $k$.

**Base Case (k=1):**
$|w_1\rangle = |v_1\rangle$ and $|e_1\rangle$ is just a scaled version of $|w_1\rangle$. Therefore, $\text{span}\{|v_1\rangle\} = \text{span}\{|e_1\rangle\}$.

**Inductive Hypothesis:**
Assume that $V_{k-1} = E_{k-1}$.

**Inductive Step:**
We need to show $V_k = E_k$. We can do this by showing that $|v_k\rangle \in E_k$ and $|e_k\rangle \in V_k$.

1.  **Show $|v_k\rangle \in E_k$**:
    Let's rearrange the Gram-Schmidt formula:
    
    $$
    |v_k\rangle = |w_k\rangle + \sum_{j=1}^{k-1} \langle e_j | v_k \rangle |e_j\rangle
    $$
    
    Since $|w_k\rangle = \||w_k\rangle\| |e_k\rangle$, this becomes:

    $$
    |v_k\rangle = \||w_k\rangle\| |e_k\rangle + \sum_{j=1}^{k-1} \langle e_j | v_k \rangle |e_j\rangle
    $$
    
    This equation explicitly shows that $|v_k\rangle$ is a linear combination of $\{|e_1\rangle, \dots, |e_k\rangle\}$. Therefore, $|v_k\rangle \in E_k$. Since all vectors in $V_{k-1}$ are in $E_{k-1}$ by our hypothesis, and $|v_k\rangle \in E_k$, it follows that $V_k \subseteq E_k$.

2.  **Show $|e_k\rangle \in V_k$**:
    The formula for $|e_k\rangle$ is:

    $$
    |e_k\rangle = \frac{1}{\||w_k\rangle\|} \left( |v_k\rangle - \sum_{j=1}^{k-1} \langle e_j | v_k \rangle |e_j\rangle \right)
    $$

    By our hypothesis, each $|e_j\rangle$ for $j < k$ is in the span of $V_{k-1} = \text{span}\{|v_1\rangle, \dots, |v_{k-1}\rangle\}$. Thus, the summation term is a linear combination of vectors from $V_{k-1}$. The expression shows that $|e_k\rangle$ is a linear combination of $|v_k\rangle$ and vectors from $V_{k-1}$. Therefore, $|e_k\rangle \in V_k$. This implies $E_k \subseteq V_k$.

Since $V_k \subseteq E_k$ and $E_k \subseteq V_k$, we must have $V_k = E_k$. The spans are identical.

**Conclusion:** The procedure produces a set of vectors that is orthogonal, normal, and spans the same space as the original set. It is therefore an orthonormal basis. 🥳

---

## **Solution 2: Proof by Geometric Projection Argument**

This proof is less formal than induction but provides a powerful intuition for *why* the procedure works. It relies on the properties of orthogonal projections.

### **The Argument for Orthogonality**

Let $U_{k-1} = \text{span}\{|e_1\rangle, \dots, |e_{k-1}\rangle\}$ be the subspace spanned by the first $k-1$ orthonormal vectors. The term

$$|\text{proj}_{U_{k-1}} |v_k\rangle \rangle = \sum_{j=1}^{k-1} \langle e_j | v_k \rangle |e_j\rangle$$

is the **orthogonal projection** of the vector $|v_k\rangle$ onto the subspace $U_{k-1}$. It represents the "shadow" that $|v_k\rangle$ casts on that subspace. 

The Gram-Schmidt formula for the intermediate vector $|w_k\rangle$ is:

$$|w_k\rangle = |v_k\rangle - |\text{proj}_{U_{k-1}} |v_k\rangle \rangle$$

By the fundamental theorem of projections in an inner product space, when you subtract a vector's projection onto a subspace from the vector itself, the resulting vector is **orthogonal to every vector in that subspace**.

Therefore, $|w_k\rangle$ is guaranteed to be orthogonal to $U_{k-1}$. This means $\langle e_j | w_k \rangle = 0$ for all $j=1, \dots, k-1$. This single geometric fact proves the orthogonality of the entire set without needing a formal inductive argument.

The proofs for **normality** and **spanning** remain the same as in Solution 1, as they are direct consequences of the algebraic construction of the procedure.
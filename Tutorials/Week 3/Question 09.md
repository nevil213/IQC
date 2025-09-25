The matrix representations of the same operator in two different orthonormal bases, $A'$ and $A''$, are related by a **unitary similarity transformation**:

$$A'' = U^\dagger A' U$$

Here, $U$ is the unitary matrix that transforms vectors from the first basis to the second. This relationship is fundamental for understanding how the description of a quantum operation changes when we change our measurement perspective.

***

### **Q9. Basis change: Suppose $A'$ and $A''$ are matrix representations of an operator $A$ on a vector space $V$ with respect to two different orthonormal bases $\{|v_i\rangle\}$ and $\{|w_i\rangle\}$. Derive the relationship between $A'$ and $A''$.**

### **1. Definitions**

* **Matrix Elements:** The elements of a matrix representing an operator are found by sandwiching the operator between the basis vectors.
    * The matrix $A'$ in the basis $\{|v_i\rangle\}$ has elements: $A'_{ij} = \langle v_i | A | v_j \rangle$.
    * The matrix $A''$ in the basis $\{|w_i\rangle\}$ has elements: $A''_{kl} = \langle w_k | A | w_l \rangle$.

* **Change of Basis Matrix:** The relationship between the two orthonormal bases is described by a **unitary matrix** $U$. The elements of this matrix are the inner products of the basis vectors:
    $$U_{ij} = \langle v_i | w_j \rangle$$
    This matrix's conjugate transpose, $U^\dagger$, has elements $(U^\dagger)_{ij} = (U_{ji})^* = (\langle v_j | w_i \rangle)^* = \langle w_i | v_j \rangle$.

---

### **2. Derivations**

We can derive the relationship in two distinct ways.

#### **Solution 1: Proof using Insertion of the Identity**
This is the standard, rigorous proof which relies on the completeness of an orthonormal basis.

**1. Start with the definition of $A''$**
We begin with the formula for an element of the matrix $A''$:
$$A''_{kl} = \langle w_k | A | w_l \rangle$$

**2. Insert the Identity Operator**
The key step is to insert the identity operator, $I$, on either side of $A$. We can express the identity operator using the **completeness relation** for the first basis, $\{|v_i\rangle\}$:
$$I = \sum_i |v_i\rangle\langle v_i|$$Inserting this twice:$$A''_{kl} = \langle w_k | I \cdot A \cdot I | w_l \rangle$$
$$A''_{kl} = \left\langle w_k \left| \left(\sum_i |v_i\rangle\langle v_i|\right) A \left(\sum_j |v_j\rangle\langle v_j|\right) \right| w_l \right\rangle$$

**3. Expand and Identify Terms**
We can pull the sums and scalars out of the inner product:
$$A''_{kl} = \sum_{i,j} \langle w_k | v_i \rangle \langle v_i | A | v_j \rangle \langle v_j | w_l \rangle$$
Now, we identify each of the three terms in the sum:
* $\langle w_k | v_i \rangle = (U^\dagger)_{ki}$
* $\langle v_i | A | v_j \rangle = A'_{ij}$
* $\langle v_j | w_l \rangle = U_{jl}$

**4. Reconstruct the Matrix Product**
Substituting these back into the sum:
$$A''_{kl} = \sum_{i,j} (U^\dagger)_{ki} A'_{ij} U_{jl}$$This expression is precisely the definition of the $(k,l)$-th element of the matrix product $U^\dagger A' U$. Since this holds for all elements, we have the matrix relationship:$$A'' = U^\dagger A' U$$

#### **Solution 2: Proof using Operator Transformation**
This method focuses on the transformation of the abstract operators themselves.

**1. Define the Change of Basis Operator**
Let $U$ be the abstract unitary operator that transforms the basis vectors:
$$|w_i\rangle = U |v_i\rangle \quad \implies \quad \langle w_k| = \langle v_k| U^\dagger$$

**2. Transform the Matrix Element Expression**
Again, we start with the definition of an element of $A''$:
$$A''_{kl} = \langle w_k | A | w_l \rangle$$Now, substitute the expressions for $\langle w_k|$ and $|w_l\rangle$ from Step 1:$$A''_{kl} = (\langle v_k| U^\dagger) A (U |v_l\rangle)$$
$$A''_{kl} = \langle v_k | (U^\dagger A U) | v_l \rangle$$

**3. Interpret the Result**
This final expression tells us that the $(k,l)$-th element of the matrix $A''$ (which is defined in the $\{|w\rangle\}$ basis) is equal to the $(k,l)$-th element of the operator $(U^\dagger A U)$ when expressed in the $\{|v\rangle\}$ basis.

The matrix for the operator $A$ in the $\{|v\rangle\}$ basis is $A'$. Therefore, the matrix for the operator $U^\dagger A U$ in the $\{|v\rangle\}$ basis is the product of the matrices representing each operator: $U^\dagger A' U$.

Equating the two gives us the final result:
$$A'' = U^\dagger A' U$$
Both methods confirm that the matrix representations are related by a unitary similarity transformation. 🔄
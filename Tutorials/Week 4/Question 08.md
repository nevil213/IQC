Yes, this relationship can be shown to be true for any measurement operator. The expression $M_m = U_m \sqrt{E_m}$ is a direct result of the **polar decomposition theorem**, a fundamental result in linear algebra that applies to any square matrix or operator.

***

### **Question 8: Suppose a measurement is described by measurement operators $M_m$. Show that there exist unitary operators $U_m$ such that $M_m = U_m \sqrt{E_m}$, where $E_m$ is the POVM associated to the measurement.**

We need to prove that for any given measurement operator $M_m$, we can find a unitary operator $U_m$ that satisfies the equation. We can prove this by directly citing the relevant theorem or by explicitly constructing the unitary operator.

---

### **Solution 1: Proof via the Polar Decomposition Theorem**

This is the most direct and concise proof, as it relies on a standard theorem of linear algebra.

**1. The Polar Decomposition Theorem**
The polar decomposition theorem is the matrix analogue of writing a complex number in polar form ($z = e^{i\theta}|z|$). The theorem states that any square matrix (or linear operator) $A$ can be written as the product of a unitary operator $U$ and a unique positive semi-definite Hermitian operator $P$:

$$A = UP$$

Furthermore, the theorem states that $P$ is uniquely determined by $A$ as:

$$P = \sqrt{A^\dagger A}$$

**2. Applying the Theorem**
We can apply this theorem directly to our measurement operator, $M_m$. Let $A = M_m$.
According to the theorem, we can write:

$$M_m = U_m P_m$$

where $U_m$ is some unitary operator and $P_m = \sqrt{M_m^\dagger M_m}$.

**3. Identifying the POVM Element**
The POVM element $E_m$ associated with the measurement operator $M_m$ is defined as:

$$E_m \equiv M_m^\dagger M_m$$

Therefore, the positive semi-definite part of the decomposition is simply the square root of the POVM element:

$$P_m = \sqrt{E_m}$$

**4. Conclusion**
Substituting this back into the polar decomposition of $M_m$, we get:

$$M_m = U_m \sqrt{E_m}$$

The polar decomposition theorem guarantees that such a unitary operator $U_m$ exists for any measurement operator $M_m$. ✅

---

### **Solution 2: Constructive Proof**

This proof is more foundational as it explicitly constructs the unitary operator $U_m$, showing how it can be defined.

**1. The Goal and The Challenge**
Our goal is to find a unitary operator $U_m$ such that $M_m = U_m \sqrt{E_m}$. One might be tempted to define $U_m = M_m (\sqrt{E_m})^{-1}$, but the inverse $(\sqrt{E_m})^{-1}$ does not exist if the operator $\sqrt{E_m}$ has any zero eigenvalues (i.e., if it is not invertible). The following construction works even in that case.

**2. Decomposing the Vector Space**
The operator $\sqrt{E_m}$ is Hermitian and acts on the quantum state space. We can split this space into two orthogonal subspaces:
* The **support** of $\sqrt{E_m}$: The subspace spanned by the eigenvectors of $\sqrt{E_m}$ with non-zero eigenvalues.
* The **null space** of $\sqrt{E_m}$: The subspace spanned by the eigenvectors of $\sqrt{E_m}$ with an eigenvalue of zero.

**3. Defining the Unitary Operator $U_m$**
We define the action of $U_m$ on any vector $|\psi\rangle$ that lies in the **support** of $\sqrt{E_m}$ as follows:

$$U_m ( \sqrt{E_m} |\psi\rangle ) \equiv M_m |\psi\rangle$$

This definition maps vectors from the support of $\sqrt{E_m}$ to the support of $M_m$. We must verify that this mapping is a **unitary transformation** (specifically, an isometry, meaning it preserves vector norms).

Let's check the norm of an input vector $|\phi_{in}\rangle = \sqrt{E_m} |\psi\rangle$:
$$||\phi_{in}||^2 = \langle \psi | (\sqrt{E_m})^\dagger (\sqrt{E_m}) |\psi \rangle = \langle \psi | E_m | \psi \rangle$$

Now let's check the norm of the corresponding output vector $|\phi_{out}\rangle = M_m |\psi\rangle$:
$$||\phi_{out}||^2 = \langle \psi | M_m^\dagger M_m |\psi\rangle = \langle \psi | E_m | \psi \rangle$$

Since $||\phi_{in}||^2 = ||\phi_{out}||^2$, the operator $U_m$ preserves norms for all vectors in the support of $\sqrt{E_m}$.

For the **null space**, we have the freedom to define $U_m$ as any norm-preserving map from the null space of $\sqrt{E_m}$ to the null space of $M_m$. (It can be shown that these two null spaces have the same dimension).

**4. Conclusion**
By defining the action of $U_m$ on the support and null space separately, we have constructed a complete operator that is unitary over the entire state space. This construction proves that for any $M_m$, a unitary $U_m$ satisfying $M_m = U_m \sqrt{E_m}$ must exist. 🏛️
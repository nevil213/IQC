The Cauchy-Schwarz inequality provides a fundamental upper bound on the inner product of two vectors. In simple terms, it states that the "overlap" between two vectors cannot be greater than the product of their individual lengths.

***

### **Q3. Discuss the Cauchy–Schwarz inequality.**

### **The Inequality and Its Meaning**
For any two vectors, $|\psi\rangle$ and $|\phi\rangle$, in a complex vector space with an inner product, the **Cauchy-Schwarz inequality** states:

$$|\langle \psi | \phi \rangle|^2 \le \langle \psi | \psi \rangle \langle \phi | \phi \rangle$$

Using the definition of the norm, $||\psi\rangle|| = \sqrt{\langle \psi | \psi \rangle}$, we can take the square root of both sides to get the more intuitive form:

$$|\langle \psi | \phi \rangle| \le |||\psi\rangle|| \cdot |||\phi\rangle||$$

**Geometric Intuition:** This inequality is a generalization of a familiar concept from Euclidean geometry. For two geometric vectors $\vec{a}$ and $\vec{b}$, their dot product is $|\vec{a} \cdot \vec{b}| = ||\vec{a}|| ||\vec{b}|| |\cos\theta|$. Since $|\cos\theta| \le 1$, the dot product is always less than or equal to the product of their lengths. The inner product in quantum mechanics is a generalized notion of a dot product, representing the overlap or projection of one state vector onto another. The Cauchy-Schwarz inequality guarantees that this overlap is bounded by the "lengths" (norms) of the state vectors. 

---

### **Formal Proof**

Here are two common ways to prove the inequality.

#### **Solution 1: The Projection Method**
This proof is based on the idea that the length of any vector must be non-negative.

1.  **Setup:** Consider two vectors, $|\psi\rangle$ and $|\phi\rangle$. If either is the zero vector, the inequality is trivially true ($0 \le 0$). So, let's assume they are non-zero.
2.  **Construct an Orthogonal Vector:** Let's define a new vector, $|z\rangle$, which is the component of $|\psi\rangle$ that is orthogonal to $|\phi\rangle$. We create this by subtracting the projection of $|\psi\rangle$ onto $|\phi\rangle$ from $|\psi\rangle$ itself:
    $$
    |z\rangle = |\psi\rangle - \frac{\langle \phi | \psi \rangle}{\langle \phi | \phi \rangle} |\phi\rangle
    $$
3.  **Use the Norm Property:** The norm of any vector is non-negative, so $\langle z | z \rangle \ge 0$.
    $$
    \left\langle \left( |\psi\rangle - \frac{\langle \phi | \psi \rangle}{\langle \phi | \phi \rangle} |\phi\rangle \right) \middle| \left( |\psi\rangle - \frac{\langle \phi | \psi \rangle}{\langle \phi | \phi \rangle} |\phi\rangle \right) \right\rangle \ge 0
    $$
4.  **Expand and Simplify:** Expanding this inner product and simplifying (using the fact that $\langle \phi|z \rangle = 0$) gives:
    $$
    \langle z|z\rangle = \langle \psi | \psi \rangle - \frac{|\langle \phi | \psi \rangle|^2}{\langle \phi | \phi \rangle} \ge 0
    $$
5.  **Rearrange:** Rearranging the terms yields the Cauchy-Schwarz inequality:
    $$
    \langle \psi | \psi \rangle \ge \frac{|\langle \phi | \psi \rangle|^2}{\langle \phi | \phi \rangle}
    $$
    $$
    \implies \langle \psi | \psi \rangle \langle \phi | \phi \rangle \ge |\langle \psi | \phi \rangle|^2
    $$

#### **Solution 2: The Minimization Method**
This proof considers a function representing the norm of a combination of the vectors.

1.  **Define a Function:** For any complex number $\lambda$, define the function $f(\lambda)$ as the squared norm of the vector $|\psi\rangle + \lambda|\phi\rangle$. Since norms are always non-negative, we have:
    $$
    f(\lambda) = \langle \psi + \lambda\phi | \psi + \lambda\phi \rangle \ge 0
    $$
2.  **Expand:**
    $$
    f(\lambda) = \langle \psi | \psi \rangle + \lambda^*\langle \phi | \psi \rangle + \lambda\langle \psi | \phi \rangle + |\lambda|^2\langle \phi | \phi \rangle \ge 0
    $$
3.  **Choose a Specific Value:** This inequality must hold for any value of $\lambda$. Let's choose the specific value that minimizes the function: $\lambda = - \frac{\langle \phi | \psi \rangle}{\langle \phi | \phi \rangle}$.
4.  **Substitute and Simplify:** Substituting this value of $\lambda$ into the expanded function and simplifying gives:
    $$
    \langle \psi | \psi \rangle - \frac{|\langle \phi | \psi \rangle|^2}{\langle \phi | \phi \rangle} \ge 0
    $$
    Rearranging this gives the Cauchy-Schwarz inequality, just as in the first method.

---

### **Condition for Equality**

The Cauchy-Schwarz inequality becomes an equality, $|\langle \psi | \phi \rangle|^2 = \langle \psi | \psi \rangle \langle \phi | \phi \rangle$, if and only if the two vectors are **linearly dependent**.

This occurs when the vector $|z\rangle$ in the first proof is the zero vector.
$$|z\rangle = |\psi\rangle - \frac{\langle \phi | \psi \rangle}{\langle \phi | \phi \rangle} |\phi\rangle = 0$$
This can only be true if $|\psi\rangle$ is a scalar multiple of $|\phi\rangle$ (i.e., $|\psi\rangle = c|\phi\rangle$ for some scalar $c$). Geometrically, this means the vectors point in the same (or opposite) direction. 🎯
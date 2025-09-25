The eigenvalues of a projector can only be 0 or 1. This is a direct consequence of a projector's defining mathematical property—**idempotence**—which means that applying the projection twice is the same as applying it once ($P^2=P$). Any eigenvalue $\lambda$ must therefore satisfy the simple equation $\lambda^2 = \lambda$, whose only solutions are 0 and 1.

***

### **Q7. Show that the eigenvalues of a projector $P$ are all either 0 or 1.**

A **projector** is an operator $P$ that is **idempotent**, meaning it satisfies the relation $P^2 = P$. To find its eigenvalues, we start with the standard eigenvalue equation, where $|\psi\rangle$ is an eigenvector and $\lambda$ is its corresponding eigenvalue:

$$P|\psi\rangle = \lambda|\psi\rangle$$

Below are three methods to prove that $\lambda$ must be either 0 or 1.

---

## **Solution 1: Algebraic Proof**

This proof uses the eigenvalue equation and the property of idempotence directly.

**1. Apply the Projector Twice**
We start with the eigenvalue equation and apply the operator $P$ to both sides:

$$P(P|\psi\rangle) = P(\lambda|\psi\rangle)$$

**2. Simplify Both Sides**
* For the left side, we use the idempotence property ($P^2=P$):
    $$
    P^2|\psi\rangle = P|\psi\rangle
    $$
* For the right side, since $\lambda$ is a scalar, it comes out of the operation:
    $$
    P(\lambda|\psi\rangle) = \lambda(P|\psi\rangle)
    $$
    Substituting the original eigenvalue equation, $P|\psi\rangle = \lambda|\psi\rangle$, into this result gives:
    $$
    \lambda(\lambda|\psi\rangle) = \lambda^2|\psi\rangle
    $$

**3. Equate and Solve**
Equating the simplified left and right sides gives us:

$$P|\psi\rangle = \lambda^2|\psi\rangle$$

But from the original definition, we know $P|\psi\rangle = \lambda|\psi\rangle$. Therefore:

$$\lambda|\psi\rangle = \lambda^2|\psi\rangle$$

$$\implies (\lambda^2 - \lambda)|\psi\rangle = 0$$

Since an eigenvector $|\psi\rangle$ is, by definition, non-zero, the scalar factor must be zero:

$$\lambda^2 - \lambda = 0 \quad \implies \quad \lambda(\lambda-1) = 0$$

The only possible solutions for the eigenvalue $\lambda$ are **0** and **1**.

---

## **Solution 2: Proof using Spectral Decomposition**

This method applies to **orthogonal projectors**, which are both idempotent ($P^2=P$) and Hermitian ($P^\dagger=P$). Since Hermitian operators are normal, they have a spectral decomposition.

The **spectral theorem** states that such a projector $P$ can be written as:

$$P = \sum_k \lambda_k |k\rangle\langle k|$$

where $\{\lambda_k\}$ are the eigenvalues of $P$ and $\{|k\rangle\}$ is a corresponding orthonormal basis of eigenvectors.

Now, we compute $P^2$ using this form:

$$P^2 = \left( \sum_j \lambda_j |j\rangle\langle j| \right) \left( \sum_k \lambda_k |k\rangle\langle k| \right) = \sum_{j,k} \lambda_j \lambda_k |j\rangle \langle j|k \rangle \langle k|$$

Because the basis is orthonormal, $\langle j|k \rangle = \delta_{jk}$. The sum collapses to terms where $j=k$:

$$P^2 = \sum_k \lambda_k^2 |k\rangle\langle k|$$

Finally, we enforce the idempotence condition, $P^2=P$:

$$\sum_k \lambda_k^2 |k\rangle\langle k| = \sum_k \lambda_k |k\rangle\langle k|$$

For this equality to hold, the coefficients for each term must be equal:

$$\lambda_k^2 = \lambda_k \quad \implies \quad \lambda_k(\lambda_k-1)=0$$

This confirms that every eigenvalue $\lambda_k$ must be either **0** or **1**.

---

## **Solution 3: Geometric Argument**

This proof relies on the intuitive, geometric meaning of a projection. 

A projector $P$ projects any vector onto a specific subspace, which we can call the **range** of $P$. Let's denote this subspace as $S$. The space of all vectors orthogonal to $S$ is its **orthogonal complement**, $S^\perp$. Any vector can be uniquely decomposed into a part in $S$ and a part in $S^\perp$.

* **Case 1: Vectors within the Subspace S**
    If a vector $|\psi\rangle$ is already in the subspace $S$, projecting it onto $S$ leaves it unchanged.
    $$
    P|\psi\rangle = |\psi\rangle = 1 \cdot |\psi\rangle
    $$
    Therefore, all vectors in the range of the projector are eigenvectors with an eigenvalue of **1**.

* **Case 2: Vectors Orthogonal to the Subspace S**
    If a vector $|\phi\rangle$ is in the orthogonal complement $S^\perp$, its projection onto $S$ is the zero vector.
    $$
    P|\phi\rangle = 0 = 0 \cdot |\phi\rangle
    $$
    Therefore, all vectors in the orthogonal complement of the projector's range are eigenvectors with an eigenvalue of **0**.

Since these two cases cover all possible eigenvectors, the only possible eigenvalues are **0** and **1**. 🎯
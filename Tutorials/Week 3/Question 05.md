Yes, any unitary operator $U$ can be written in the form $U = \exp(iK)$ for some Hermitian operator $K$. This is a cornerstone of quantum mechanics, as it connects the unitary operators that describe quantum evolution with the Hermitian operators that describe physical observables (like the Hamiltonian). We can prove this using the **spectral decomposition theorem**.

***

### **Q5. Use the spectral decomposition to show that $K \equiv -i \log(U)$ is Hermitian for any unitary $U$, and thus $U = \exp(iK)$ for some Hermitian $K$.**

The proof involves three main steps: decomposing the unitary operator $U$, using this to define the operator $K$ and prove it is Hermitian, and finally exponentiating $K$ to show that we recover $U$.

---

### **Step 1: Spectral Decomposition of the Unitary Operator U**

The **spectral theorem** states that any normal operator (one that commutes with its Hermitian conjugate) can be diagonalized. Since a unitary operator $U$ satisfies $U^\dagger U = U U^\dagger = I$, it is normal. Therefore, it has a spectral decomposition of the form:

$$U = \sum_j \lambda_j |j\rangle\langle j|$$

where $\{|j\rangle\}$ is a complete orthonormal basis of eigenvectors of $U$, and $\{\lambda_j\}$ are the corresponding eigenvalues.

An important property of these eigenvalues is that they are complex numbers with a magnitude of 1. We can show this by considering the norm of an eigenvector after applying $U$:

$$\langle j | U^\dagger U | j \rangle = \langle j | I | j \rangle = 1$$

$$\langle j | U^\dagger U | j \rangle = |\lambda_j|^2 \langle j|j\rangle = |\lambda_j|^2$$

Therefore, $|\lambda_j|^2 = 1$. This means each eigenvalue can be written as a pure phase:

$$\lambda_j = e^{i\theta_j} \quad \text{for some real number } \theta_j$$

---

### **Step 2: Define K and Prove it is Hermitian**

We can define a function of an operator, such as a logarithm, using its spectral decomposition.
$$\log(U) = \sum_j \log(\lambda_j) |j\rangle\langle j|$$
Substituting $\lambda_j = e^{i\theta_j}$:
$$\log(U) = \sum_j \log(e^{i\theta_j}) |j\rangle\langle j| = \sum_j i\theta_j |j\rangle\langle j|$$
Now we define the operator $K$ as given in the question:
$$K \equiv -i \log(U) = -i \left( \sum_j i\theta_j |j\rangle\langle j| \right) = \sum_j \theta_j |j\rangle\langle j|$$
To prove that $K$ is **Hermitian**, we must show that $K^\dagger = K$. Let's compute the Hermitian conjugate of $K$:
$$K^\dagger = \left( \sum_j \theta_j |j\rangle\langle j| \right)^\dagger = \sum_j (\theta_j |j\rangle\langle j|)^\dagger$$
Using the property $(cA)^\dagger = c^*A^\dagger$ and $(|a\rangle\langle b|)^\dagger = |b\rangle\langle a|$:
$$K^\dagger = \sum_j \theta_j^* (|j\rangle\langle j|)^\dagger = \sum_j \theta_j^* |j\rangle\langle j|$$
Since each $\theta_j$ is a **real number**, its complex conjugate is itself, $\theta_j^* = \theta_j$.
$$K^\dagger = \sum_j \theta_j |j\rangle\langle j| = K$$
Thus, we have proven that $K$ is a Hermitian operator. ✅

---

### **Step 3: Show that U = exp(iK)**
Finally, we exponentiate the operator $iK$ to show that it reconstructs the original unitary $U$. We use the spectral decomposition of $K$ that we just found: $K = \sum_j \theta_j |j\rangle\langle j|$.
$$\exp(iK) = \sum_j \exp(i\theta_j) |j\rangle\langle j|$$
We recognize that $e^{i\theta_j}$ is simply the original eigenvalue $\lambda_j$ of the unitary operator $U$.
$$\exp(iK) = \sum_j \lambda_j |j\rangle\langle j|$$
This is precisely the spectral decomposition of $U$ that we started with. Therefore:
$$U = \exp(iK)$$
This completes the proof. We have shown that any unitary operator can be written as the exponential of $i$ times some Hermitian operator. 🔑
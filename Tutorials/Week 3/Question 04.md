Yes, the time evolution operator is unitary. This is a crucial feature of quantum mechanics, as it ensures that the total probability of all outcomes remains 1 over time. The proof relies directly on the fact that the Hamiltonian operator, $H$, is **Hermitian**.

***

### **Q4. Prove that $U(t_1, t_2) = \exp\left( -\frac{i}{\hbar} H (t_2 - t_1) \right)$ is unitary.**

To prove that an operator $U$ is **unitary**, we must show that its Hermitian conjugate (or adjoint), $U^\dagger$, is also its inverse. That is, we must prove:

$$U^\dagger U = I$$

The time evolution operator $U$ is defined by the **Hamiltonian** $H$, which is a **Hermitian** operator. This means it is equal to its own Hermitian conjugate: $H^\dagger = H$.

---

## **Solution 1: Direct Proof using Operator Properties**
This proof uses the algebraic properties of the matrix exponential and the Hermitian conjugate. Let's simplify the notation by setting $\Delta t = t_2 - t_1$.

$$U = \exp\left( -\frac{i}{\hbar} H \Delta t \right)$$

**1. Find the Hermitian Conjugate ($U^\dagger$)**
We take the Hermitian conjugate of the entire operator. A key property of the matrix exponential is that $(e^A)^\dagger = e^{A^\dagger}$.

$$U^\dagger = \left[ \exp\left( -\frac{i}{\hbar} H \Delta t \right) \right]^\dagger = \exp\left[ \left( -\frac{i}{\hbar} H \Delta t \right)^\dagger \right]$$

Now, we find the conjugate of the exponent. Since $\Delta t$ and $\hbar$ are real numbers, the complex conjugate of $-i$ is $+i$. Because H is Hermitian ($H^\dagger=H$), we get:

$$U^\dagger = \exp\left( +\frac{i}{\hbar} H^\dagger \Delta t \right) = \exp\left( \frac{i}{\hbar} H \Delta t \right)$$

**2. Multiply $U^\dagger$ by $U$**
Now we can compute the product $U^\dagger U$:

$$U^\dagger U = \exp\left( \frac{i}{\hbar} H \Delta t \right) \exp\left( -\frac{i}{\hbar} H \Delta t \right)$$

Since the two exponents are just scalar multiples of the same operator $H$, they commute. This allows us to use the property $e^A e^B = e^{A+B}$:

$$U^\dagger U = \exp\left( \frac{i}{\hbar} H \Delta t - \frac{i}{\hbar} H \Delta t \right) = \exp(0) = I$$

Since $U^\dagger U = I$, the operator $U$ is unitary. ✅

---

## **Solution 2: Proof using the Energy Eigenbasis**
This proof shows how the operator acts on states, confirming that it preserves the norm of any state vector.

**1. Action on Eigenstates**
Since $H$ is Hermitian, it has a complete orthonormal basis of eigenvectors, which we'll call the energy eigenbasis $\{|E_n\rangle\}$, with corresponding real eigenvalues $\{E_n\}$. By definition:

$$H|E_n\rangle = E_n|E_n\rangle$$

Let's see how $U$ acts on one of these basis states. For any function of an operator, $f(H)|E_n\rangle = f(E_n)|E_n\rangle$.

$$U|E_n\rangle = \exp\left( -\frac{i}{\hbar} H \Delta t \right)|E_n\rangle = \exp\left( -\frac{i}{\hbar} E_n \Delta t \right)|E_n\rangle$$

The operator simply multiplies the eigenvector by a phase factor.

**2. Preserving the Norm**
A unitary operator is one that preserves the norm (length) of any vector it acts upon. Let's take an arbitrary state $|\psi\rangle$ and expand it in the energy eigenbasis:

$$|\psi\rangle = \sum_n c_n |E_n\rangle$$

The squared norm of this state is $||\psi\rangle||^2 = \langle \psi | \psi \rangle = \sum_n |c_n|^2$.

Now let's apply $U$ to $|\psi\rangle$:

$$U|\psi\rangle = U\left(\sum_n c_n |E_n\rangle\right) = \sum_n c_n (U|E_n\rangle) = \sum_n c_n \exp\left( -\frac{i}{\hbar} E_n \Delta t \right)|E_n\rangle$$

Let's compute the squared norm of this new state, $||\psi'\rangle||^2 = \langle \psi' | \psi' \rangle$:

$$||U|\psi\rangle||^2 = \left( \sum_m c_m^* \exp\left( \frac{i}{\hbar} E_m \Delta t \right)\langle E_m | \right) \left( \sum_n c_n \exp\left( -\frac{i}{\hbar} E_n \Delta t \right)|E_n\rangle \right)$$

Because the basis is orthonormal, $\langle E_m | E_n \rangle = \delta_{mn}$, and the sum collapses to terms where $m=n$:

$$= \sum_n c_n^* c_n \exp\left( \frac{i}{\hbar} E_n \Delta t \right) \exp\left( -\frac{i}{\hbar} E_n \Delta t \right) = \sum_n |c_n|^2 e^0 = \sum_n |c_n|^2$$

Since $||U|\psi\rangle||^2 = ||\psi\rangle||^2$, the operator preserves the norm of any state and is therefore unitary. ⚛️
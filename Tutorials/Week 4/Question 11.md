Yes, the four Bell states form an orthonormal basis for the two-qubit state space. We can verify this by either directly calculating the inner products between the states or by showing that they are a unitary transformation of the standard computational basis.

***

### **Question 11: Verify that the Bell basis forms an orthonormal basis for the two qubit state space.**

To prove that a set of vectors forms an **orthonormal basis**, we must show two things:
1.  **Normality:** Each state is a unit vector (its inner product with itself is 1).
2.  **Orthogonality:** Any two distinct states are orthogonal (their inner product is 0).

Since the two-qubit Hilbert space is 4-dimensional and there are four Bell states, proving these two conditions is sufficient to show they form a basis.

The four Bell states are:
$$|\Phi^+\rangle = \frac{1}{\sqrt{2}}(|00\rangle + |11\rangle) \quad , \quad |\Phi^-\rangle = \frac{1}{\sqrt{2}}(|00\rangle - |11\rangle)$$
$$|\Psi^+\rangle = \frac{1}{\sqrt{2}}(|01\rangle + |10\rangle) \quad , \quad |\Psi^-\rangle = \frac{1}{\sqrt{2}}(|01\rangle - |10\rangle)$$

---

### **Solution 1: Direct Calculation of Inner Products**

This method involves explicitly calculating the 16 inner products between the four states and showing they satisfy the condition $\langle\text{Bell}_i|\text{Bell}_j\rangle = \delta_{ij}$.

#### **1. Verifying Normality**
Let's calculate the inner product of $|\Phi^+\rangle$ with itself. We use the fact that the computational basis is orthonormal (e.g., $\langle 00|00 \rangle = 1$ and $\langle 00|11 \rangle = 0$).

$$\langle \Phi^+ | \Phi^+ \rangle = \left( \frac{1}{\sqrt{2}}(\langle 00| + \langle 11|) \right) \left( \frac{1}{\sqrt{2}}(|00\rangle + |11\rangle) \right)$$

$$= \frac{1}{2} (\langle 00|00\rangle + \langle 00|11\rangle + \langle 11|00\rangle + \langle 11|11\rangle)$$

$$= \frac{1}{2} (1 + 0 + 0 + 1) = 1$$

The calculation is identical for the other three Bell states, confirming they are all normalized to 1. ✅

#### **2. Verifying Orthogonality**
We must show that the inner product of any two distinct Bell states is zero. Let's check two representative pairs.

* **Pair 1: $\langle \Phi^+ | \Phi^- \rangle$**
    $$
    \langle \Phi^+ | \Phi^- \rangle = \left( \frac{1}{\sqrt{2}}(\langle 00| + \langle 11|) \right) \left( \frac{1}{\sqrt{2}}(|00\rangle - |11\rangle) \right)
    $$ $$
    = \frac{1}{2} (\langle 00|00\rangle - \langle 00|11\rangle + \langle 11|00\rangle - \langle 11|11\rangle)
    $$ $$
    = \frac{1}{2} (1 - 0 + 0 - 1) = 0
    $$
* **Pair 2: $\langle \Phi^+ | \Psi^+ \rangle$**
    $$
    \langle \Phi^+ | \Psi^+ \rangle = \left( \frac{1}{\sqrt{2}}(\langle 00| + \langle 11|) \right) \left( \frac{1}{\sqrt{2}}(|01\rangle + |10\rangle) \right)
    $$ $$
    = \frac{1}{2} (\langle 00|01\rangle + \langle 00|10\rangle + \langle 11|01\rangle + \langle 11|10\rangle)
    $$ $$
    = \frac{1}{2} (0 + 0 + 0 + 0) = 0
    $$

Similar calculations show that all 6 distinct pairs are orthogonal. ✅

Since the four Bell states are mutually orthogonal and normalized, they form an orthonormal basis.

---

### **Solution 2: Proof by Unitary Transformation**

This method uses the principle that a **unitary operator always maps an orthonormal basis to another orthonormal basis**.

**1. The Transformation**
Consider the quantum circuit that consists of a **Hadamard gate** on the first qubit, followed by a **CNOT gate** where the first qubit is the control and the second is the target. The unitary operator for this circuit is $U = U_{CNOT} (H \otimes I)$. 

**2. Applying the Transformation to the Computational Basis**
Let's see what this unitary operator does to each of the four computational basis states.
* $U|00\rangle = U_{CNOT} (H|0\rangle \otimes |0\rangle) = U_{CNOT} \left(\frac{|0\rangle+|1\rangle}{\sqrt{2}} \otimes |0\rangle\right) = \frac{1}{\sqrt{2}}(|00\rangle+|11\rangle) = |\Phi^+\rangle$
* $U|01\rangle = U_{CNOT} (H|0\rangle \otimes |1\rangle) = U_{CNOT} \left(\frac{|0\rangle+|1\rangle}{\sqrt{2}} \otimes |1\rangle\right) = \frac{1}{\sqrt{2}}(|01\rangle+|10\rangle) = |\Psi^+\rangle$
* $U|10\rangle = U_{CNOT} (H|1\rangle \otimes |0\rangle) = U_{CNOT} \left(\frac{|0\rangle-|1\rangle}{\sqrt{2}} \otimes |0\rangle\right) = \frac{1}{\sqrt{2}}(|00\rangle-|11\rangle) = |\Phi^-\rangle$
* $U|11\rangle = U_{CNOT} (H|1\rangle \otimes |1\rangle) = U_{CNOT} \left(\frac{|0\rangle-|1\rangle}{\sqrt{2}} \otimes |1\rangle\right) = \frac{1}{\sqrt{2}}(|01\rangle-|10\rangle) = |\Psi^-\rangle$

**3. Conclusion**
The operator $U$ performs the following mapping:

$$U: \{|00\rangle, |01\rangle, |10\rangle, |11\rangle\} \to \{|\Phi^+\rangle, |\Psi^+\rangle, |\Phi^-\rangle, |\Psi^-\rangle\}$$

Since the computational basis $\{|00\rangle, |01\rangle, |10\rangle, |11\rangle\}$ is an orthonormal basis, and we have found a unitary transformation that maps it to the set of Bell states, the Bell states must also form an orthonormal basis. 💫
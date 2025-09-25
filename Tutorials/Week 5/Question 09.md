A Bell measurement forces a quantum system to collapse into one of the four maximally entangled Bell states. When performed on a separable (non-entangled) state like $|+\rangle|+\rangle$, this measurement projects it onto one of the entangled basis states, thereby creating entanglement where none existed before.

***

### **Question 9: Entanglement via measurement: Consider two qubits initialized in $|+\rangle|+\rangle$.**
**(a) Show the effect of measuring them in the Bell basis instead of the computational basis.**
**(b) Why does this measurement create entanglement between the qubits even if they started as a product state?**

---

### **(a) The Effect of a Bell Basis Measurement**

To see the effect, we first need to express the initial state in the computational basis and then rewrite it in the Bell basis to easily find the measurement probabilities.

#### **Solution 1: Rewriting the State in the Bell Basis**

**1. Initial State in the Computational Basis**
The initial state is a product state of two qubits, each in the $|+\rangle$ state:
$$|\psi\rangle = |+\rangle \otimes |+\rangle = \frac{1}{\sqrt{2}}(|0\rangle + |1\rangle) \otimes \frac{1}{\sqrt{2}}(|0\rangle + |1\rangle)$$
$$|\psi\rangle = \frac{1}{2} \left( |00\rangle + |01\rangle + |10\rangle + |11\rangle \right)$$

**2. Rewriting in the Bell Basis**
The four Bell states are:
* $|\Phi^+\rangle = \frac{1}{\sqrt{2}}(|00\rangle + |11\rangle)$
* $|\Phi^-\rangle = \frac{1}{\sqrt{2}}(|00\rangle - |11\rangle)$
* $|\Psi^+\rangle = \frac{1}{\sqrt{2}}(|01\rangle + |10\rangle)$
* $|\Psi^-\rangle = \frac{1}{\sqrt{2}}(|01\rangle - |10\rangle)$

We can express the computational basis states in terms of the Bell states:
* $|00\rangle = \frac{1}{\sqrt{2}}(|\Phi^+\rangle + |\Phi^-\rangle)$
* $|11\rangle = \frac{1}{\sqrt{2}}(|\Phi^+\rangle - |\Phi^-\rangle)$
* $|01\rangle = \frac{1}{\sqrt{2}}(|\Psi^+\rangle + |\Psi^-\rangle)$
* $|10\rangle = \frac{1}{\sqrt{2}}(|\Psi^+\rangle - |\Psi^-\rangle)$

Substituting these into our initial state $|\psi\rangle$:
$$|\psi\rangle = \frac{1}{2} \left[ \frac{1}{\sqrt{2}}(|\Phi^+\rangle + |\Phi^-\rangle) + \frac{1}{\sqrt{2}}(|\Psi^+\rangle + |\Psi^-\rangle) + \frac{1}{\sqrt{2}}(|\Psi^+\rangle - |\Psi^-\rangle) + \frac{1}{\sqrt{2}}(|\Phi^+\rangle - |\Phi^-\rangle) \right]$$
Combining terms, we see that the $|\Phi^-\rangle$ and $|\Psi^-\rangle$ components cancel out:
$$|\psi\rangle = \frac{1}{2\sqrt{2}} \left( 2|\Phi^+\rangle + 2|\Psi^+\rangle \right) = \frac{1}{\sqrt{2}}(|\Phi^+\rangle + |\Psi^+\rangle)$$

**3. Measurement Outcomes**
From this form, we can directly read off the probabilities using the Born rule. The probability of measuring a certain Bell state is the squared magnitude of its coefficient.
* **Probability of measuring $|\Phi^+\rangle$**: $P(\Phi^+) = \left|\frac{1}{\sqrt{2}}\right|^2 = \frac{1}{2}$
* **Probability of measuring $|\Psi^+\rangle$**: $P(\Psi^+) = \left|\frac{1}{\sqrt{2}}\right|^2 = \frac{1}{2}$
* **Probability of measuring $|\Phi^-\rangle$**: $P(\Phi^-) = |0|^2 = 0$
* **Probability of measuring $|\Psi^-\rangle$**: $P(\Psi^-) = |0|^2 = 0$

**Effect:** When the state $|+\rangle|+\rangle$ is measured in the Bell basis, the system will collapse to either the state **$|\Phi^+\rangle$ with 50% probability** or the state **$|\Psi^+\rangle$ with 50% probability**. Both possible post-measurement states are maximally entangled.

---

### **(b) Why Measurement Creates Entanglement**

The creation of entanglement in this scenario is a direct consequence of the **measurement postulate** of quantum mechanics.

1.  **Initial State is Not Entangled:** The starting state, $|+\rangle|+\rangle$, is a **product state** (or separable state). This means the state of the first qubit ($|+\rangle$) can be described completely independently of the state of the second qubit ($|+\rangle$). There are no intrinsic correlations between them.

2.  **Measurement is a Projection:** A quantum measurement is a **projective operation**. When you perform a measurement in a specific basis (like the Bell basis), you are asking the system, "Which of these basis states are you in?" The system is then forced to "choose" one, and its state vector collapses to the basis state corresponding to the measurement outcome.

3.  **The Bell Basis is Entangled:** The crucial point is that the basis states themselves—the four Bell states—are all **maximally entangled**. None of them can be written as a simple product of two individual qubit states. Their definitions inherently contain correlations. For example, in the $|\Phi^+\rangle$ state, if the first qubit is measured to be $|0\rangle$, the second is guaranteed to be $|0\rangle$.

**Conclusion:** The act of measuring in the Bell basis forces the initially independent qubits to collapse into one of the basis's constituent states. Since every one of these possible outcomes is an entangled state, the measurement process itself **projects the separable state onto an entangled one**, thereby creating entanglement.
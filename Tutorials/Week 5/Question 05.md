The four Bell states are a set of specific, maximally entangled two-qubit quantum states that form a complete orthonormal basis. The standard quantum circuit to create the Bell state $|\Phi^+\rangle$ from an initial $|00\rangle$ state involves applying a Hadamard gate to the first qubit to create a superposition, followed by a CNOT gate to entangle the two qubits.

***

### **Question 5: Bell states**
**(a) List the four Bell states.**
**(b) Design a quantum circuit that produces the Bell state $|\Phi^+\rangle= \frac{1}{\sqrt{2}}(|00\rangle+ |11\rangle)$ starting from the initial state $|00\rangle$.**

---

### **(a) The Four Bell States**

The four Bell states form the Bell basis and are the simplest examples of quantum entanglement. They are:

1.  **$|\Phi^+\rangle$**
    $$
    |\Phi^+\rangle = \frac{1}{\sqrt{2}}(|00\rangle + |11\rangle)
    $$
2.  **$|\Phi^-\rangle$**
    $$
    |\Phi^-\rangle = \frac{1}{\sqrt{2}}(|00\rangle - |11\rangle)
    $$
3.  **$|\Psi^+\rangle$**
    $$
    |\Psi^+\rangle = \frac{1}{\sqrt{2}}(|01\rangle + |10\rangle)
    $$
4.  **$|\Psi^-\rangle$**
    $$
    |\Psi^-\rangle = \frac{1}{\sqrt{2}}(|01\rangle - |10\rangle)
    $$

---

### **(b) Circuit to Create the $|\Phi^+\rangle$ State**

Here are two equivalent circuit designs that can create the $|\Phi^+\rangle$ Bell state from the initial state $|00\rangle$.

#### **Solution 1: Standard Circuit Design**

This circuit uses the first qubit as the control qubit.
1.  Apply a **Hadamard (H) gate** to the first qubit.
2.  Apply a **Controlled-NOT (CNOT) gate**, with the first qubit as the control and the second qubit as the target.



**Step-by-Step Derivation:**

1.  **Initial State:** The system starts in the state $|\psi_0\rangle = |00\rangle$.

2.  **After Hadamard Gate:** The H gate is applied to the first qubit ($q_1$), creating a superposition. The second qubit ($q_2$) is unaffected.
    $$
    |\psi_1\rangle = (H \otimes I) |00\rangle = (H|0\rangle) \otimes |0\rangle
    $$
    Since $H|0\rangle = \frac{1}{\sqrt{2}}(|0\rangle + |1\rangle)$, the state becomes:
    $$
    |\psi_1\rangle = \frac{1}{\sqrt{2}}(|0\rangle + |1\rangle) \otimes |0\rangle = \frac{1}{\sqrt{2}}(|00\rangle + |10\rangle)
    $$

3.  **After CNOT Gate:** The CNOT gate flips the target qubit ($q_2$) if the control qubit ($q_1$) is $|1\rangle$. We apply it to our superposition state:
    $$
    |\psi_f\rangle = \text{CNOT}|\psi_1\rangle = \frac{1}{\sqrt{2}}(\text{CNOT}|00\rangle + \text{CNOT}|10\rangle)
    $$
    * For the $|00\rangle$ part, the control is $|0\rangle$, so the target is unchanged: $\text{CNOT}|00\rangle \rightarrow |00\rangle$.
    * For the $|10\rangle$ part, the control is $|1\rangle$, so the target is flipped: $\text{CNOT}|10\rangle \rightarrow |11\rangle$.

    The final state is the desired Bell state:
    $$
    |\psi_f\rangle = \frac{1}{\sqrt{2}}(|00\rangle + |11\rangle) = |\Phi^+\rangle
    $$

#### **Solution 2: Alternative Circuit Design**

This circuit uses the second qubit as the control qubit.
1.  Apply a **Hadamard (H) gate** to the second qubit.
2.  Apply a **Controlled-NOT (CNOT) gate**, with the second qubit as the control and the first qubit as the target.



**Step-by-Step Derivation:**

1.  **Initial State:** $|\psi_0\rangle = |00\rangle$.

2.  **After Hadamard Gate:** The H gate is applied to the second qubit ($q_2$).
    $$
    |\psi_1\rangle = (I \otimes H) |00\rangle = |0\rangle \otimes (H|0\rangle)
    $$
    $$
    |\psi_1\rangle = |0\rangle \otimes \frac{1}{\sqrt{2}}(|0\rangle + |1\rangle) = \frac{1}{\sqrt{2}}(|00\rangle + |01\rangle)
    $$

3.  **After CNOT Gate:** The CNOT gate flips the target qubit ($q_1$) if the control qubit ($q_2$) is $|1\rangle$.
    $$
    |\psi_f\rangle = \text{CNOT}_{2 \rightarrow 1}|\psi_1\rangle = \frac{1}{\sqrt{2}}(\text{CNOT}_{2 \rightarrow 1}|00\rangle + \text{CNOT}_{2 \rightarrow 1}|01\rangle)
    $$
    * For the $|00\rangle$ part, the control ($q_2$) is $|0\rangle$, so the target ($q_1$) is unchanged: $\text{CNOT}_{2 \rightarrow 1}|00\rangle \rightarrow |00\rangle$.
    * For the $|01\rangle$ part, the control ($q_2$) is $|1\rangle$, so the target ($q_1$) is flipped: $\text{CNOT}_{2 \rightarrow 1}|01\rangle \rightarrow |11\rangle$.

    The final state is again the desired Bell state:
    $$
    |\psi_f\rangle = \frac{1}{\sqrt{2}}(|00\rangle + |11\rangle) = |\Phi^+\rangle
    $$
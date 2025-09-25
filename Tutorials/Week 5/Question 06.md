The quantum teleportation protocol uses shared entanglement and classical communication to transmit a quantum state from one location to another. The initial steps performed by Alice entangle the unknown qubit with her half of the shared pair, transferring the state's information into correlations across all three qubits.

### **Question 6: Teleportation protocol – Step analysis: Consider the quantum teleportation circuit (Alice has qubits 1 and 2, Bob has qubit 3).**
**(a) If Alice’s qubit 1 is in an unknown state $|\psi\rangle = \alpha|0\rangle+ \beta|1\rangle$, and qubits 2 and 3 are in the Bell state $\frac{1}{\sqrt{2}}(|00\rangle+ |11\rangle)$, write the combined initial state of the three qubits.**
**(b) Show how Alice’s application of CNOT (control = qubit 1, target = qubit 2) and Hadamard on qubit 1 transforms the state.**



---

### **(a) The Combined Initial State**

The initial state of the three-qubit system, $|\psi_0\rangle$, is the tensor product of Alice's unknown state ($|\psi\rangle_1$) and the entangled Bell pair shared between Alice and Bob ($|\Phi^+\rangle_{23}$).

$$|\psi_0\rangle = |\psi\rangle_1 \otimes |\Phi^+\rangle_{23}$$

Substituting the expressions for the states:
$$|\psi_0\rangle = (\alpha|0\rangle_1 + \beta|1\rangle_1) \otimes \frac{1}{\sqrt{2}}(|0\rangle_2|0\rangle_3 + |1\rangle_2|1\rangle_3)$$We distribute the tensor product to expand the expression. The subscript on each ket indicates which qubit it belongs to.$$= \frac{1}{\sqrt{2}} \left[ \alpha|0\rangle_1 \otimes (|0\rangle_2|0\rangle_3 + |1\rangle_2|1\rangle_3) + \beta|1\rangle_1 \otimes (|0\rangle_2|0\rangle_3 + |1\rangle_2|1\rangle_3) \right]$$Combining the kets, the full initial state of the system is:$$|\psi_0\rangle = \frac{1}{\sqrt{2}} \left( \alpha|000\rangle + \alpha|011\rangle + \beta|100\rangle + \beta|111\rangle \right)$$

---

### **(b) Transformation by Alice's Gates**

Alice now performs two operations on her two qubits (qubit 1 and qubit 2). We will track the evolution of the state step-by-step.

#### **Step 1: Apply CNOT Gate**
Alice applies a CNOT gate with her first qubit ($q_1$) as the control and her second qubit ($q_2$) as the target. We apply this $CNOT_{12}$ gate to the state $|\psi_0\rangle$. By linearity, we can apply it to each term in the superposition.

$$|\psi_1\rangle = CNOT_{12} |\psi_0\rangle$$

* $\alpha|000\rangle$: Control ($q_1$) is 0, target ($q_2$) is unchanged $\rightarrow \alpha|000\rangle$
* $\alpha|011\rangle$: Control ($q_1$) is 0, target ($q_2$) is unchanged $\rightarrow \alpha|011\rangle$
* $\beta|100\rangle$: Control ($q_1$) is 1, target ($q_2$) is flipped ($0 \rightarrow 1$) $\rightarrow \beta|110\rangle$
* $\beta|111\rangle$: Control ($q_1$) is 1, target ($q_2$) is flipped ($1 \rightarrow 0$) $\rightarrow \beta|101\rangle$

The state after the CNOT gate is:
$$|\psi_1\rangle = \frac{1}{\sqrt{2}} \left( \alpha|000\rangle + \alpha|011\rangle + \beta|110\rangle + \beta|101\rangle \right)$$

#### **Step 2: Apply Hadamard Gate**
Next, Alice applies a Hadamard gate to her first qubit ($q_1$). The operation is $H_1 = H \otimes I \otimes I$. We apply it to the state $|\psi_1\rangle$.

$$|\psi_2\rangle = H_1 |\psi_1\rangle$$

We use the transformations $H|0\rangle = \frac{1}{\sqrt{2}}(|0\rangle+|1\rangle)$ and $H|1\rangle = \frac{1}{\sqrt{2}}(|0\rangle-|1\rangle)$ on the first qubit of each term:

$$|\psi_2\rangle = \frac{1}{\sqrt{2}} \left[ \alpha(H|0\rangle)|00\rangle + \alpha(H|0\rangle)|11\rangle + \beta(H|1\rangle)|10\rangle + \beta(H|1\rangle)|01\rangle \right]$$
$$= \frac{1}{\sqrt{2}} \left[ \frac{\alpha}{\sqrt{2}}(|0\rangle+|1\rangle)|00\rangle + \frac{\alpha}{\sqrt{2}}(|0\rangle+|1\rangle)|11\rangle + \frac{\beta}{\sqrt{2}}(|0\rangle-|1\rangle)|10\rangle + \frac{\beta}{\sqrt{2}}(|0\rangle-|1\rangle)|01\rangle \right]$$

Expanding and combining the constants gives the final state:
$$|\psi_2\rangle = \frac{1}{2} \left[ \alpha(|000\rangle+|100\rangle) + \alpha(|011\rangle+|111\rangle) + \beta(|010\rangle-|110\rangle) + \beta(|001\rangle-|101\rangle) \right]$$

#### **Insightful Re-grouping of the Final State**
This expression shows the state of the system, but its true significance is revealed when we re-group the terms according to Alice's two qubits ($q_1, q_2$). This shows how the state of Bob's qubit ($q_3$) is now correlated with Alice's measurement outcome.

$$
|\psi_2\rangle = \frac{1}{2} \Big[
|00\rangle_{12} \otimes (\alpha|0\rangle_3 + \beta|1\rangle_3) \ +
$$
$$|01\rangle_{12} \otimes (\alpha|1\rangle_3 + \beta|0\rangle_3) \ +$$
$$|10\rangle_{12} \otimes (\alpha|0\rangle_3 - \beta|1\rangle_3) \ +$$
$$
|11\rangle_{12} \otimes (\alpha|1\rangle_3 - \beta|0\rangle_3)
\Big]
$$
This transformed state is the heart of the teleportation protocol. It shows that if Alice measures her two qubits and gets the result `00`, Bob's qubit ($q_3$) will instantly be in the original state $|\psi\rangle$. If she gets a different result, Bob's qubit will be in a state that can be simply corrected (by applying X and/or Z gates) to recover the original $|\psi\rangle$.  teleport ➡️
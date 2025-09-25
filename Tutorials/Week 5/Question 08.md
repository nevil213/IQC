Yes, two consecutive Hadamard gates cancel each other out. This property, along with the way the Hadamard gate swaps the Pauli-X and Pauli-Z operations, leads to a fascinating equivalence in the teleportation circuit. If Bob applies Hadamards around his correction step, the protocol still works perfectly, provided he also swaps his interpretation of the two classical bits he receives from Alice.

***

### **Question 8: Show that applying two consecutive Hadamard gates to a qubit is equivalent to the identity operation. Then, using this, prove that the teleportation circuit still works correctly if Bob mistakenly applies an extra Hadamard both before and after his correction step.**

---

### **Part 1: Proving H · H = I**

We can show that the Hadamard gate is its own inverse in two ways.

#### **Solution 1.1: Direct Matrix Multiplication**

The Hadamard matrix is defined as:

$$
H = \frac{1}{\sqrt{2}} \begin{pmatrix}
1 & 1 \\\\
1 & -1
\end{pmatrix}
$$

Multiplying the matrix by itself gives:

$$
H \cdot H = \left(\frac{1}{\sqrt{2}}\right)^2 \begin{pmatrix}
1 & 1 \\\\
1 & -1
\end{pmatrix} \begin{pmatrix}
1 & 1 \\\\
1 & -1
\end{pmatrix}
$$

$$
= \frac{1}{2} \begin{pmatrix}
(1)(1)+(1)(1) & (1)(1)+(1)(-1) \\\\
(1)(1)+(-1)(1) & (1)(1)+(-1)(-1)
\end{pmatrix}
$$

$$
= \frac{1}{2} \begin{pmatrix}
2 & 0 \\\\
0 & 2
\end{pmatrix} = \begin{pmatrix}
1 & 0 \\\\
0 & 1
\end{pmatrix} = I
$$

This shows that applying the Hadamard gate twice is equivalent to the identity operation.

#### **Solution 1.2: Action on Basis States**

We can also prove this by showing that applying H twice to the computational basis states, $|0\rangle$ and $|1\rangle$, returns them to their original form.

* **For $|0\rangle$**:
    $$
    H(H|0\rangle) = H\left(\frac{1}{\sqrt{2}}(|0\rangle + |1\rangle)\right) = \frac{1}{\sqrt{2}}(H|0\rangle + H|1\rangle)
    $$
    $$
    = \frac{1}{\sqrt{2}}\left(\frac{1}{\sqrt{2}}(|0\rangle + |1\rangle) + \frac{1}{\sqrt{2}}(|0\rangle - |1\rangle)\right) = \frac{1}{2}(2|0\rangle) = |0\rangle
    $$
* **For $|1\rangle$**:
    $$
    H(H|1\rangle) = H\left(\frac{1}{\sqrt{2}}(|0\rangle - |1\rangle)\right) = \frac{1}{\sqrt{2}}(H|0\rangle - H|1\rangle)
    $$
    $$
    = \frac{1}{\sqrt{2}}\left(\frac{1}{\sqrt{2}}(|0\rangle + |1\rangle) - \frac{1}{\sqrt{2}}(|0\rangle - |1\rangle)\right) = \frac{1}{2}(2|1\rangle) = |1\rangle
    $$

Since the operation acts as the identity for all basis states, it is the identity operator.

---

### **Part 2: Bob's "Mistake" in the Teleportation Protocol**

The proof that the protocol still works relies on a key insight: applying Hadamards before and after an operation is equivalent to performing that operation in a different basis. This basis change swaps the roles of the Pauli-X and Pauli-Z gates.

**1. The Key Identities**
Conjugating the Pauli gates by the Hadamard gate yields the following identities:
* $H X H = Z$
* $H Z H = X$

**2. The Consequence for Bob's Correction**
In the standard protocol, when Alice sends Bob the classical bits $m_1m_2$, he applies the correction $U_{corr} = X^{m_2} Z^{m_1}$. If he mistakenly applies Hadamards around this step, his new operation is $U_{new} = H (X^{m_2} Z^{m_1}) H$.

For the protocol to remain correct, his new operation must successfully transform the state he receives into the original state $|\psi\rangle$. This requires that his interpretation of Alice's bits must also be transformed according to the identities above. The bit $m_2$ that controlled the X gate must now control the Z gate, and the bit $m_1$ that controlled the Z gate must now control the X gate.

**3. Case-by-Case Proof with Swapped Logic**
Let's verify that the protocol works for all four of Alice's measurement outcomes, assuming Bob swaps his interpretation of the bits.

* **Alice sends 00 ($m_1=0, m_2=0$)**:
    * Bob receives the state $|\psi\rangle$.
    * Bob swaps the bits (still 00) and applies the correction for "00", which is $I$. His physical operation is $H I H = I$.
    * **Final State**: $I |\psi\rangle = |\psi\rangle$. **(Success)**

* **Alice sends 01 ($m_1=0, m_2=1$)**:
    * Bob receives the state $X|\psi\rangle$.
    * Bob swaps the bits to "10". The standard correction for "10" is $Z$. His physical operation is $H Z H = X$.
    * **Final State**: $X (X|\psi\rangle) = X^2|\psi\rangle = |\psi\rangle$. **(Success)**

* **Alice sends 10 ($m_1=1, m_2=0$)**:
    * Bob receives the state $Z|\psi\rangle$.
    * Bob swaps the bits to "01". The standard correction for "01" is $X$. His physical operation is $H X H = Z$.
    * **Final State**: $Z (Z|\psi\rangle) = Z^2|\psi\rangle = |\psi\rangle$. **(Success)**

* **Alice sends 11 ($m_1=1, m_2=1$)**:
    * Bob receives the state $XZ|\psi\rangle$.
    * Bob swaps the bits (still 11) and applies the correction for "11", which is $XZ$. His physical operation is $H (XZ) H = iY$.
    * **Final State**: $(iY) (XZ|\psi\rangle) = (iY) (-iY|\psi\rangle) = Y^2|\psi\rangle = |\psi\rangle$. **(Success)**

**Conclusion:** The teleportation protocol is robust to this "mistake." Applying Hadamards before and after the correction step is equivalent to Bob performing the protocol in the Hadamard basis. As long as he consistently translates the classical information from Alice into this new basis (by swapping the bits), the final state is correctly restored. ⚛️
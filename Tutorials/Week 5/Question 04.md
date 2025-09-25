A universal quantum cloning circuit cannot exist because the fundamental principles of quantum mechanics, specifically the **linearity of quantum operators**, forbid it. If a machine could perfectly copy basis states like $|0\rangle$ and $|1\rangle$, linearity dictates that its attempt to copy a superposition state like $|+\rangle$ would fail, producing an entangled state instead of two identical copies.

### **Question 4: Explain why a quantum circuit that copies an arbitrary qubit state $|\psi\rangle$ into $|\psi\rangle|\psi\rangle$ cannot exist. Provide a short mathematical justification.**

***

### **Solution 1: Proof by Linearity and Contradiction**

This is the standard proof of the no-cloning theorem. It works by assuming a cloning device exists and then showing that this assumption leads to a contradiction when applied to a superposition state.

**1. Assume a Cloning Operator Exists**
Let's assume there is a unitary operator, $U_{clone}$, that can copy any arbitrary state $|\psi\rangle$ onto a blank initial state, say $|0\rangle$. The operation would be:

$$U_{clone} (|\psi\rangle \otimes |0\rangle) = |\psi\rangle \otimes |\psi\rangle$$

This must be true for *any* state $|\psi\rangle$.

**2. Test the Cloner on Basis States**
Let's see how this operator must behave for the computational basis states.
* If we want to clone the state $|\psi\rangle = |0\rangle$:
    $$
    U_{clone} (|0\rangle \otimes |0\rangle) = |0\rangle \otimes |0\rangle
    $$
* If we want to clone the state $|\psi\rangle = |1\rangle$:
    $$
    U_{clone} (|1\rangle \otimes |0\rangle) = |1\rangle \otimes |1\rangle
    $$
So far, the cloner's required behavior is well-defined for the basis states.

**3. Test the Cloner on a Superposition State**
Now, the critical step. Let's try to clone a superposition state, such as $|+\rangle = \frac{1}{\sqrt{2}}(|0\rangle + |1\rangle)$.

* **The Desired Output:** A perfect cloning machine should produce:
    $$
    |\text{desired}\rangle = |+\rangle \otimes |+\rangle = \frac{1}{2}(|0\rangle + |1\rangle) \otimes (|0\rangle + |1\rangle) = \frac{1}{2}(|00\rangle + |01\rangle + |10\rangle + |11\rangle)
    $$
* **The Actual Output:** According to the rules of quantum mechanics, the operator $U_{clone}$ must act **linearly**. Let's see what happens when we apply it to the input state $|+\rangle \otimes |0\rangle$:
    $$
    |\text{actual}\rangle = U_{clone}(|+\rangle \otimes |0\rangle) = U_{clone}\left[ \left(\frac{1}{\sqrt{2}}(|0\rangle + |1\rangle)\right) \otimes |0\rangle \right]
    $$
    $$
    = U_{clone}\left[ \frac{1}{\sqrt{2}}(|00\rangle + |10\rangle) \right]
    $$
    By linearity, we can apply the operator to each part of the superposition:
    $$
    = \frac{1}{\sqrt{2}} \left( U_{clone}|00\rangle + U_{clone}|10\rangle \right)
    $$
    Now, we substitute the behavior we defined in Step 2:
    $$
    = \frac{1}{\sqrt{2}} (|00\rangle + |11\rangle)
    $$

**4. The Contradiction**
We compare the desired output with the actual output:
* $|\text{desired}\rangle = \frac{1}{2}(|00\rangle + |01\rangle + |10\rangle + |11\rangle)$
* $|\text{actual}\rangle = \frac{1}{\sqrt{2}}(|00\rangle + |11\rangle)$

Clearly, $|\text{actual}\rangle \neq |\text{desired}\rangle$. The actual result is a famous entangled Bell state, not two separate copies of $|+\rangle$. This contradiction proves that our initial assumption was false. **No universal unitary operator $U_{clone}$ can exist.** 🚫

---

### **Solution 2: Proof by Preservation of Inner Products**

This proof uses a different core property of quantum mechanics: **unitary operations preserve the inner product** between quantum states.

**1. Inner Products Before and After Cloning**
Let $|\psi\rangle$ and $|\phi\rangle$ be two different, non-orthogonal quantum states.
* **Before Cloning:** The initial state for cloning $|\psi\rangle$ is $|\psi_{in}\rangle = |\psi\rangle \otimes |0\rangle$, and for $|\phi\rangle$ it's $|\phi_{in}\rangle = |\phi\rangle \otimes |0\rangle$. Their inner product is:
    $$
    \langle \psi_{in} | \phi_{in} \rangle = (\langle\psi| \otimes \langle0|) (|\phi\rangle \otimes |0\rangle) = \langle\psi|\phi\rangle \langle0|0\rangle = \langle\psi|\phi\rangle
    $$
* **After Cloning:** If a cloner existed, the output states would be $|\psi_{out}\rangle = |\psi\rangle \otimes |\psi\rangle$ and $|\phi_{out}\rangle = |\phi\rangle \otimes |\phi\rangle$. Their inner product would be:
    $$
    \langle \psi_{out} | \phi_{out} \rangle = (\langle\psi| \otimes \langle\psi|) (|\phi\rangle \otimes |\phi\rangle) = \langle\psi|\phi\rangle \langle\psi|\phi\rangle = (\langle\psi|\phi\rangle)^2
    $$

**2. The Contradiction**
Any quantum evolution, including cloning, must be described by a unitary operator. Unitary operators must preserve the inner product, meaning $\langle \psi_{in} | \phi_{in} \rangle$ must equal $\langle \psi_{out} | \phi_{out} \rangle$.
Therefore, we must have:

$$\langle\psi|\phi\rangle = (\langle\psi|\phi\rangle)^2$$

Let $x = \langle\psi|\phi\rangle$. The equation $x = x^2$ has only two possible solutions: $x=0$ or $x=1$.
* $x=0$ means the states $|\psi\rangle$ and $|\phi\rangle$ are orthogonal.
* $x=1$ means the states $|\psi\rangle$ and $|\phi\rangle$ are identical.

This implies that a cloning machine could only work on a set of states that are all mutually orthogonal. However, the defining characteristic of a qubit is that it can exist in a continuum of superposition states that are not orthogonal (e.g., $|0\rangle$ and $|+\rangle$). For $|0\rangle$ and $|+\rangle$, the inner product is $\langle 0 | + \rangle = 1/\sqrt{2}$. For these states, the required condition becomes:

$$\frac{1}{\sqrt{2}} = \left(\frac{1}{\sqrt{2}}\right)^2 = \frac{1}{2}$$

This is false. Therefore, a device that can clone an **arbitrary** quantum state cannot exist.
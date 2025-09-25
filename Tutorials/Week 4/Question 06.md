It's impossible to reliably distinguish between two non-orthogonal quantum states because they have a non-zero overlap in the Hilbert space. Any measurement designed to perfectly identify one state will have a non-zero probability of being triggered by the other state, making perfect distinction impossible. This is a direct consequence of the linearity and unitarity of quantum mechanics.

***

### **Question 6: Show a formal proof establishing that the two non-orthogonal states cannot be reliably distinguished.**

Let $|\psi\rangle$ and $|\phi\rangle$ be two **non-orthogonal** quantum states, which means their inner product is non-zero:

$$\langle \psi | \phi \rangle \neq 0$$

To "reliably distinguish" them means that a physical process—a quantum measurement—must exist that can determine which of the two states was provided with 100% certainty. We can prove that such a process is impossible by showing that its existence leads to a logical contradiction.

---

## **Solution 1: Proof by Unitarity of Evolution**

This proof assumes that a distinguishing procedure exists and shows that this assumption violates the requirement that all quantum evolutions must be **unitary**.

**1. The Setup**
Let's assume a distinguishing device exists. Such a device can be described by a unitary operator $U$. It would take the unknown input state (e.g., $|\psi\rangle$) and an initial "blank" state of the device, $|d_0\rangle$, and evolve them to a final state where the device's state indicates the result.

For the device to work perfectly:
* If the input is $|\psi\rangle$, the device's final state must be an orthogonal state $|d_\psi\rangle$ that signifies "the state was psi".
    $$U (|\psi\rangle \otimes |d_0\rangle) = |\psi\rangle \otimes |d_\psi\rangle$$
* If the input is $|\phi\rangle$, the device's final state must be a different, orthogonal state $|d_\phi\rangle$ that signifies "the state was phi".
    $$U (|\phi\rangle \otimes |d_0\rangle) = |\phi\rangle \otimes |d_\phi\rangle$$
For the distinction to be **reliable**, the indicator states must be orthogonal: $\langle d_\psi | d_\phi \rangle = 0$.

**2. The Inner Product**
A key property of any unitary operator $U$ is that it **preserves the inner product** between states. Let's compare the inner product of the two initial states with the inner product of the two final states.

* **Initial Inner Product:**
    $$
    \langle \text{initial}_1 | \text{initial}_2 \rangle = (\langle \psi | \otimes \langle d_0 |) (|\phi\rangle \otimes |d_0\rangle) = \langle \psi | \phi \rangle \langle d_0 | d_0 \rangle
    $$
    Since $|d_0\rangle$ is a normalized state, $\langle d_0 | d_0 \rangle = 1$. So, the initial inner product is simply $\langle \psi | \phi \rangle$.

* **Final Inner Product:**
    $$
    \langle \text{final}_1 | \text{final}_2 \rangle = (\langle \psi | \otimes \langle d_\psi |) (|\phi\rangle \otimes |d_\phi\rangle) = \langle \psi | \phi \rangle \langle d_\psi | d_\phi \rangle
    $$

**3. The Contradiction**
Because the evolution $U$ is unitary, the initial and final inner products must be equal:
$$\langle \psi | \phi \rangle = \langle \psi | \phi \rangle \langle d_\psi | d_\phi \rangle$$For the measurement to be reliable, the indicator states must be perfectly distinguishable, meaning they must be orthogonal: $\langle d_\psi | d_\phi \rangle = 0$. Substituting this into our equation:$$\langle \psi | \phi \rangle = \langle \psi | \phi \rangle \cdot 0$$
$$\langle \psi | \phi \rangle = 0$$
This is a **contradiction**. We started with the premise that the states were **non-orthogonal** ($\langle \psi | \phi \rangle \neq 0$), but the assumption of a perfect distinguishing procedure forced us to conclude that they must be orthogonal. Therefore, our initial assumption must be false.

No such unitary procedure can exist. 🚫

---

## **Solution 2: Proof by Geometric Interpretation**

This approach uses the geometric interpretation of quantum states and measurement.

**1. The Setup**
* A quantum state is a vector in a Hilbert space. Two states being **non-orthogonal** means the vectors are not perpendicular.
* A **measurement** projects the state vector onto one of the basis vectors of the measurement.
* To **reliably distinguish** $|\psi\rangle$ and $|\phi\rangle$, we would need to find a measurement basis (let's call its vectors $|b_1\rangle, |b_2\rangle, \dots$) such that:
    1.  When the state is $|\psi\rangle$, the measurement outcome is always "$b_1$".
    2.  When the state is $|\phi\rangle$, the measurement outcome is always "$b_2$".
    3.  Crucially, $b_1$ and $b_2$ must be different outcomes.

**2. The Implication of Perfect Measurement**
* For the measurement of $|\psi\rangle$ to *always* yield the outcome "$b_1$", the state $|\psi\rangle$ must be perfectly aligned with the basis vector $|b_1\rangle$. This means $|\psi\rangle$ must be equal to $|b_1\rangle$ (up to a global phase, which we can ignore).
    $$|\psi\rangle = |b_1\rangle$$
* Similarly, for the measurement of $|\phi\rangle$ to *always* yield the outcome "$b_2$", the state $|\phi\rangle$ must be identical to the basis vector $|b_2\rangle$.
    $$|\phi\rangle = |b_2\rangle$$

**3. The Contradiction**
The vectors of any valid measurement basis, $\{|b_i\rangle\}$, must be **mutually orthogonal**. Therefore, $|b_1\rangle$ and $|b_2\rangle$ must be orthogonal.
$$\langle b_1 | b_2 \rangle = 0$$Substituting our findings from the previous step:$$\langle \psi | \phi \rangle = 0$$
This is a **contradiction**. We began with the assumption that $|\psi\rangle$ and $|\phi\rangle$ were non-orthogonal. The requirement of a perfect measurement forces them to be orthogonal. Thus, no such measurement can exist.
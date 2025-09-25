When a qubit in the state $|+\rangle$ is measured, the outcomes and their probabilities depend entirely on the basis in which the measurement is performed.

* In the **computational basis**, the outcomes $|0\rangle$ and $|1\rangle$ are equally likely, each with a 50% probability.
* In the **Hadamard basis**, the outcome is certain to be $|+\rangle$, with a 100% probability.

***

### **Question 2: Suppose a qubit is in the state $|+\rangle = \frac{1}{\sqrt{2}}(|0\rangle + |1\rangle)$.**
**(a) What are the possible outcomes if it is measured in the computational basis $\{|0\rangle,|1\rangle\}$?**
**(b) What are the possible outcomes if it is measured in the Hadamard basis $\{|+\rangle,|-\rangle\}$?**



To find the probability of measuring a state $|\psi\rangle$ and getting the outcome of a basis state $|b\rangle$, we use the Born rule:

$$P(b) = |\langle b | \psi \rangle|^2$$

---

## **(a) Measurement in the Computational Basis**

Here, our state is $|\psi\rangle = |+\rangle$, and we're measuring against the basis vectors $|0\rangle$ and $|1\rangle$.

#### **Outcome $|0\rangle$**

We calculate the inner product $\langle 0 | +\rangle$:

$$\langle 0 | +\rangle = \left\langle 0 \left| \left( \frac{1}{\sqrt{2}}(|0\rangle + |1\rangle) \right) \right. \right\rangle = \frac{1}{\sqrt{2}} (\langle 0 | 0 \rangle + \langle 0 | 1 \rangle)$$

Since $\langle 0 | 0 \rangle = 1$ and $\langle 0 | 1 \rangle = 0$, this simplifies to:

$$\langle 0 | +\rangle = \frac{1}{\sqrt{2}} (1 + 0) = \frac{1}{\sqrt{2}}$$

The probability is the squared magnitude:

$$P(0) = \left| \frac{1}{\sqrt{2}} \right|^2 = \frac{1}{2}$$

#### **Outcome $|1\rangle$**

Similarly, we calculate the inner product $\langle 1 | +\rangle$:

$$\langle 1 | +\rangle = \frac{1}{\sqrt{2}} (\langle 1 | 0 \rangle + \langle 1 | 1 \rangle) = \frac{1}{\sqrt{2}} (0 + 1) = \frac{1}{\sqrt{2}}$$

The probability is:

$$P(1) = \left| \frac{1}{\sqrt{2}} \right|^2 = \frac{1}{2}$$

**Conclusion:** The possible outcomes are $|0\rangle$ and $|1\rangle$, each with a **50% probability**.

---

## **(b) Measurement in the Hadamard Basis**

Here, we're measuring the same state, $|\psi\rangle = |+\rangle$, against the basis vectors $|+\rangle$ and $|-\rangle$.

#### **Outcome $|+\rangle$**

We calculate the inner product $\langle + | +\rangle$. Since the state we're measuring is identical to the basis state and is already normalized, the inner product is 1.

$$\langle + | + \rangle = 1$$

The probability is:

$$P(+) = |1|^2 = 1$$

#### **Outcome $|-\rangle$**

We calculate the inner product $\langle - | +\rangle$. The Hadamard basis states are orthogonal, meaning the inner product of distinct states is 0.

$$\langle - | + \rangle = 0$$

The probability is:

$$P(-) = |0|^2 = 0$$

**Conclusion:** The only possible outcome is $|+\rangle$, which occurs with **100% probability**. 🎯
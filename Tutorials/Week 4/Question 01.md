The average value of a quantum measurement, also called the **expectation value**, is $\langle M \rangle = \langle \psi | M | \psi \rangle$. The **standard deviation**, which measures the statistical spread of the outcomes, is given by the formula $\Delta M = \sqrt{\langle M^2 \rangle - \langle M \rangle^2}$.

***

### **Question 1: Show that the average value of the measurement is $\langle \psi | M | \psi \rangle$. Also, compute the formula for standard deviation.**

This derivation uses the basic principles of quantum measurement. We consider a physical **observable** represented by a Hermitian operator $M$. This operator has **eigenvalues** $\{m\}$, which are the possible measurement outcomes, and corresponding **eigenvectors** $\{|m\rangle\}$.

---

## **Average (Expectation) Value**

The average value of a measurement is found by summing each possible outcome multiplied by its probability of occurring.

**1. Definition of Average Value**
From statistics, the average is the sum of (outcome $\times$ probability of outcome).

$$\langle M \rangle = \sum_m m \cdot P(m)$$

**2. The Born Rule**
Quantum mechanics gives us the probability $P(m)$ of measuring the outcome $m$ from a state $|\psi\rangle$ via the **Born rule**:

$$P(m) = |\langle m | \psi \rangle|^2$$

Substituting this into the definition:

$$\langle M \rangle = \sum_m m |\langle m | \psi \rangle|^2$$

**3. Simplification**
Using the identity $|z|^2 = z^*z$ (where $z = \langle m | \psi \rangle$), and the eigenvalue equation $M|m\rangle = m|m\rangle$, we can rewrite the expression:

$$\langle M \rangle = \sum_m m \langle \psi | m \rangle \langle m | \psi \rangle = \sum_m \langle \psi | (m|m\rangle) \langle m | \psi \rangle = \sum_m \langle \psi | (M|m\rangle) \langle m | \psi \rangle$$

This can be regrouped as:

$$\langle M \rangle = \langle \psi | M \left( \sum_m |m\rangle\langle m| \right) |\psi \rangle$$

**4. The Completeness Relation**
The set of eigenvectors $\{|m\rangle\}$ forms a complete basis. This gives us the **completeness relation**, which states that the sum of the projectors onto these basis states is the identity operator, $I$:

$$\sum_m |m\rangle\langle m| = I$$

Substituting this into our expression gives the final result:

$$\langle M \rangle = \langle \psi | M I |\psi \rangle = \langle \psi | M | \psi \rangle$$

---

## **Standard Deviation**

The **standard deviation** $\Delta M$ measures the uncertainty in the measurement outcomes. It's the square root of the **variance** $(\Delta M)^2$.

**1. Definition of Variance**
The variance is the expectation value of the squared deviation from the mean. The operator for this is $(M - \langle M \rangle I)^2$.

$$(\Delta M)^2 = \left\langle (M - \langle M \rangle I)^2 \right\rangle$$

**2. Expansion and Simplification**
We can expand the operator inside the expectation value:

$$(M - \langle M \rangle I)^2 = M^2 - 2\langle M \rangle M + \langle M \rangle^2 I$$

Using the linearity of the expectation value:

$$(\Delta M)^2 = \langle M^2 \rangle - \langle 2\langle M \rangle M \rangle + \langle \langle M \rangle^2 I \rangle$$

Since $\langle M \rangle$ is a scalar, we can pull it out of the expectation values:

$$(\Delta M)^2 = \langle M^2 \rangle - 2\langle M \rangle \langle M \rangle + \langle M \rangle^2 \langle I \rangle$$

The expectation value of the identity operator $\langle I \rangle$ is always 1 for a normalized state. This leaves:

$$(\Delta M)^2 = \langle M^2 \rangle - 2\langle M \rangle^2 + \langle M \rangle^2 = \langle M^2 \rangle - \langle M \rangle^2$$

**3. Final Formula**
The **standard deviation** is the square root of the variance. 📈

$$\Delta M = \sqrt{(\Delta M)^2} = \sqrt{\langle M^2 \rangle - \langle M \rangle^2}$$

In bra-ket notation, this is:

$$\Delta M = \sqrt{\langle \psi | M^2 | \psi \rangle - (\langle \psi | M | \psi \rangle)^2}$$
If a quantum system is in an eigenstate of an observable, a measurement of that observable is deterministic. The average value of the measurement will be the corresponding **eigenvalue $m$**, and the **standard deviation will be zero**, indicating there is no uncertainty in the outcome.

***

### **Question 2: Suppose we prepare a quantum system in an eigenstate $|\psi\rangle$ of some observable $M$, with corresponding eigenvalue $m$. What is the average observed value of $M$, and the standard deviation?**

The fact that the system is in an **eigenstate** $|\psi\rangle$ of the operator $M$ is described by the eigenvalue equation:

$$M|\psi\rangle = m|\psi\rangle$$

This means that the state $|\psi\rangle$ has a definite, well-defined value of the physical property represented by $M$.

---

### **Solution 1: Using Expectation Value Formulas**

This method uses the general formulas for the average and standard deviation and applies the specific condition of being in an eigenstate.

#### **Average Value**
The formula for the average (or expectation) value is $\langle M \rangle = \langle \psi | M | \psi \rangle$.

We can substitute the eigenvalue equation directly into this formula:
$$\langle M \rangle = \langle \psi | (M|\psi\rangle)$$
$$\langle M \rangle = \langle \psi | (m|\psi\rangle)$$Since the eigenvalue $m$ is a scalar, we can pull it out of the inner product:$$\langle M \rangle = m \langle \psi | \psi \rangle$$For any valid quantum state, the state vector is normalized, meaning $\langle \psi | \psi \rangle = 1$.$$\langle M \rangle = m \cdot 1 = m$$
The average value is exactly the eigenvalue.

#### **Standard Deviation**
The formula for the standard deviation is $\Delta M = \sqrt{\langle M^2 \rangle - \langle M \rangle^2}$.

First, let's find the expectation value of $M^2$:
$$\langle M^2 \rangle = \langle \psi | M^2 | \psi \rangle = \langle \psi | M(M|\psi\rangle)$$We apply the eigenvalue equation twice:$$\langle M^2 \rangle = \langle \psi | M(m|\psi\rangle) = m\langle \psi | M|\psi\rangle = m\langle \psi | m|\psi\rangle = m^2\langle \psi | \psi \rangle$$Since $\langle \psi | \psi \rangle = 1$, we get:$$\langle M^2 \rangle = m^2$$Now, we substitute our results for $\langle M \rangle$ and $\langle M^2 \rangle$ into the variance formula:$$(\Delta M)^2 = \langle M^2 \rangle - \langle M \rangle^2 = m^2 - (m)^2 = 0$$The standard deviation is the square root of the variance:$$\Delta M = \sqrt{0} = 0$$

---

### **Solution 2: Using the Measurement Postulate**

This method uses the physical interpretation of eigenstates and measurement.

#### **Average Value**
According to the **measurement postulate** of quantum mechanics, if a system is in an eigenstate of an observable $M$, then a measurement of $M$ will **always** yield the corresponding eigenvalue $m$. The probability of getting this outcome is 1, and the probability of getting any other outcome is 0.

The average value is the sum of each outcome multiplied by its probability. Since only one outcome is possible:
$$\langle M \rangle = m \cdot P(m) = m \cdot 1 = m$$

#### **Standard Deviation**
The standard deviation measures the statistical spread or uncertainty in the measurement outcomes. Since the outcome is **always** $m$, there is no spread and no uncertainty. The deviation from the mean ($m-m$) is always zero.

Mathematically, the variance is the average of the squared deviation from the mean. Since the only outcome is the mean itself:
$$(\Delta M)^2 = (m - \langle M \rangle)^2 \cdot P(m) = (m - m)^2 \cdot 1 = 0$$Therefore, the standard deviation is:$$\Delta M = 0$$

Both methods confirm that for a system in an eigenstate, the measurement result is certain. 🎯
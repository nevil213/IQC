When measuring the observable $X$ on a qubit prepared in the state $|0\rangle$, the **average value of the measurement is 0**, and the **standard deviation is 1**. This indicates that the two possible outcomes, +1 and -1, are equally likely, resulting in maximum uncertainty.

***

### **Question 3: Suppose we have a qubit in the state $|0\rangle$, and we measure the observable $X$. What is the average value of $X$? What is the standard deviation?**

The state of the system is $|\psi\rangle = |0\rangle$, and the observable is the Pauli-X matrix, $M=X$.

$$
X = \begin{pmatrix}
0 & 1 \\\\
1 & 0
\end{pmatrix}
$$

---

## **Solution 1: Using Expectation Value Formulas**

This method directly applies the general formulas for expectation value and standard deviation.

#### **Average Value**
The average value is given by the formula $\langle X \rangle = \langle \psi | X | \psi \rangle$.

$$\langle X \rangle = \langle 0 | X | 0 \rangle$$

First, we apply the $X$ gate to the state $|0\rangle$:

$$X|0\rangle = |1\rangle$$

Substituting this back into the expression:

$$\langle X \rangle = \langle 0 | 1 \rangle$$

Since the computational basis states $|0\rangle$ and $|1\rangle$ are orthogonal, their inner product is zero.

$$\langle X \rangle = 0$$

#### **Standard Deviation**
The standard deviation is given by the formula $\Delta X = \sqrt{\langle X^2 \rangle - \langle X \rangle^2}$.

First, we need to find $\langle X^2 \rangle = \langle 0 | X^2 | 0 \rangle$. The Pauli-X matrix squares to the identity matrix, $X^2 = I$.

$$\langle X^2 \rangle = \langle 0 | I | 0 \rangle = \langle 0 | 0 \rangle$$

Since the state $|0\rangle$ is normalized, $\langle 0 | 0 \rangle = 1$.

$$\langle X^2 \rangle = 1$$

Now we can calculate the variance:

$$(\Delta X)^2 = \langle X^2 \rangle - \langle X \rangle^2 = 1 - (0)^2 = 1$$

The standard deviation is the square root of the variance:

$$\Delta X = \sqrt{1} = 1$$

---

## **Solution 2: Using Eigenvalues and Probabilities**

This method involves finding the possible measurement outcomes (the eigenvalues of X) and their probabilities.

#### **1. Find Eigenvalues and Eigenvectors of X**
The observable $X$ has two eigenvalues, which are the only possible outcomes of the measurement:
* Eigenvalue $m_1 = +1$, with corresponding eigenvector $|+\rangle = \frac{1}{\sqrt{2}}(|0\rangle + |1\rangle)$.
* Eigenvalue $m_2 = -1$, with corresponding eigenvector $|-\rangle = \frac{1}{\sqrt{2}}(|0\rangle - |1\rangle)$.

#### **2. Calculate Measurement Probabilities**
We use the Born rule, $P(m) = |\langle m | \psi \rangle|^2$, to find the probability of each outcome when the system is in the state $|\psi\rangle = |0\rangle$.

* **Probability of outcome +1:**
    $$
    P(+1) = |\langle + | 0 \rangle|^2 = \left| \left( \frac{1}{\sqrt{2}}(\langle 0 | + \langle 1 |) \right) |0\rangle \right|^2 = \left| \frac{1}{\sqrt{2}}(1+0) \right|^2 = \frac{1}{2}
    $$
* **Probability of outcome -1:**
    $$
    P(-1) = |\langle - | 0 \rangle|^2 = \left| \left( \frac{1}{\sqrt{2}}(\langle 0 | - \langle 1 |) \right) |0\rangle \right|^2 = \left| \frac{1}{\sqrt{2}}(1-0) \right|^2 = \frac{1}{2}
    $$
We see that the outcomes +1 and -1 are equally likely.

#### **3. Calculate Average and Standard Deviation**
* **Average Value:**
    $$
    \langle X \rangle = \sum_m m \cdot P(m) = (+1) \cdot P(+1) + (-1) \cdot P(-1)
    $$
    $$
    \langle X \rangle = (1)\left(\frac{1}{2}\right) + (-1)\left(\frac{1}{2}\right) = 0
    $$
* **Standard Deviation:**
    The variance is $(\Delta X)^2 = \langle X^2 \rangle - \langle X \rangle^2$. First we find $\langle X^2 \rangle$:
    $$
    \langle X^2 \rangle = \sum_m m^2 \cdot P(m) = (+1)^2 \cdot P(+1) + (-1)^2 \cdot P(-1)
    $$
    $$
    \langle X^2 \rangle = (1)\left(\frac{1}{2}\right) + (1)\left(\frac{1}{2}\right) = 1
    $$
    So, the variance is $(\Delta X)^2 = 1 - (0)^2 = 1$. The standard deviation is:
    $$
    \Delta X = \sqrt{1} = 1
    $$

Both methods confirm that the average value is 0 and the standard deviation is 1. 🎯
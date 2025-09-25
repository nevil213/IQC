Of course. The question asks to realize the Hadamard gate as a product of three simpler gates, each being a rotation with a potential global phase. This is a practical application of unitary decomposition, breaking a complex operation into a sequence of simpler, physically implementable ones.

We'll assume "Theorem 0.2" refers to the general principle that any single-qubit unitary can be decomposed into a sequence of rotations around standard axes (an Euler angle decomposition). We can find several such decompositions.

### **Question 10: Use Theorem 0.2 to realize the Hadamard gate H as a product of three gates A, B, C, where A, B, C are of the form $e^{i\alpha} R_{\hat{n}}(\theta)$ for suitable $\alpha, \theta, \hat{n}$.**

***

### **Solution 1: The Z-Y-Z Decomposition**

One of the most common ways to decompose any unitary is the **Z-Y-Z decomposition**, which states that any unitary $U$ can be written as $U = e^{i\alpha} R_z(\beta) R_y(\gamma) R_z(\delta)$. We can find the specific angles for the Hadamard gate and then group the terms into three gates $A, B, C$.

A known Z-Y-Z decomposition for the Hadamard gate is:

$$H = e^{i\pi/2} R_z(0) R_y(\pi/2) R_z(\pi)$$

We can verify this product expands to the Hadamard gate. Now, we group these four components into three gates $A, B, C$ such that $H = ABC$. A natural grouping is to associate the global phase with the first rotation.

* $A = e^{i\pi/2} R_z(0)$
* $B = R_y(\pi/2)$
* $C = R_z(\pi)$

Let's check the form of each gate:
* **Gate A:** Here $\alpha = \pi/2$, the rotation axis is $\hat{n} = \hat{z}$, and the angle is $\theta=0$. Since $R_z(0) = I$, this gate is just a global phase $A = e^{i\pi/2}I = iI$.
* **Gate B:** Here $\alpha = 0$, the rotation axis is $\hat{n} = \hat{y}$, and the angle is $\theta=\pi/2$.
* **Gate C:** Here $\alpha = 0$, the rotation axis is $\hat{n} = \hat{z}$, and the angle is $\theta=\pi$.

All three gates are of the required form $e^{i\alpha} R_{\hat{n}}(\theta)$.

***

### **Solution 2: The Z-X-Z Decomposition**

An equally valid decomposition uses rotations around the Z and X axes. A known Z-X-Z decomposition for the Hadamard gate is:

$$H = e^{i\pi/2} R_z(\pi/2) R_x(\pi/2) R_z(\pi/2)$$

This is a very symmetric and common representation of the Hadamard gate. . We can group this into three gates $A, B, C$:

* $A = e^{i\pi/2} R_z(\pi/2)$
* $B = R_x(\pi/2)$
* $C = R_z(\pi/2)$

Let's check the form of each gate:
* **Gate A:** $\alpha = \pi/2$, $\hat{n} = \hat{z}$, $\theta=\pi/2$.
* **Gate B:** $\alpha = 0$, $\hat{n} = \hat{x}$, $\theta=\pi/2$.
* **Gate C:** $\alpha = 0$, $\hat{n} = \hat{z}$, $\theta=\pi/2$.

This provides a different, yet equally correct, decomposition into three gates of the specified form.

***

### **Solution 3: Decomposition of the Rotation Axis**

Another approach is to start with the representation of the Hadamard gate as a *single* rotation about a specific axis. It's known that:

$$H = e^{i\pi/2} R_{\hat{n}}(\pi) \quad \text{where} \quad \hat{n} = \frac{1}{\sqrt{2}}(\hat{x} + \hat{z})$$

Now, the task is to decompose the single rotation $R_{\hat{n}}(\pi)$ into a product of simpler rotations. Any rotation can be decomposed by a change of basis. We can find a rotation $V$ that maps the $\hat{z}$ axis to our desired axis $\hat{n}$, such that $R_{\hat{n}}(\theta) = V R_z(\theta) V^\dagger$.

The vector $\hat{n}$ is in the X-Z plane, at an angle of $\pi/4$ from the Z-axis. A rotation about the Y-axis by $-\pi/4$ achieves this mapping: $V = R_y(-\pi/4)$. Therefore:

$$R_{\hat{n}}(\pi) = R_y(-\pi/4) R_z(\pi) R_y(\pi/4)$$

Substituting this back into our expression for $H$:

$$H = e^{i\pi/2} \left[ R_y(-\pi/4) R_z(\pi) R_y(\pi/4) \right]$$

We can now group this into three gates $A, B, C$:

* $A = e^{i\pi/2} R_y(-\pi/4)$
* $B = R_z(\pi)$
* $C = R_y(\pi/4)$

This decomposition is also valid and provides yet another way to construct the Hadamard gate from three fundamental rotation operations. 💎
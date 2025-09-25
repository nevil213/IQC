For a qubit in the state $|0\rangle$, the probability of measuring the outcome +1 for the observable $\vec{v} \cdot \vec{\sigma}$ is $P(+1) = \frac{1+v_3}{2}$. If this outcome is obtained, the qubit collapses to the corresponding normalized eigenvector of the observable.

***

### **Question 5: Calculate the probability of obtaining the result +1 for a measurement of $\vec{v} \cdot \vec{\sigma}$, given that the state prior to measurement is $|0\rangle$. What is the state of the system after the measurement if +1 is obtained?**

This problem builds on the results for the observable $M \equiv \vec{v} \cdot \vec{\sigma}$, namely that its eigenvalues are $\pm 1$ and its projector onto the +1 eigenspace is $P_+ = \frac{I + M}{2}$. The initial state of the system is $|\psi\rangle = |0\rangle$.

---

### **Solution 1: Using the Projector Operator**

This method uses the projector $P_+$ to directly calculate the probability and the post-measurement state.

#### **1. Calculating the Probability**
The probability of measuring an outcome is the expectation value of the projector corresponding to that outcome.

$$P(+1) = \langle \psi | P_+ | \psi \rangle = \langle 0 | P_+ | 0 \rangle$$

Substituting the formula for the projector $P_+$:
$$P(+1) = \left\langle 0 \left| \frac{I + \vec{v} \cdot \vec{\sigma}}{2} \right| 0 \right\rangle$$Using the linearity of the inner product:$$P(+1) = \frac{1}{2} \left( \langle 0 | I | 0 \rangle + v_1\langle 0 | X | 0 \rangle + v_2\langle 0 | Y | 0 \rangle + v_3\langle 0 | Z | 0 \rangle \right)$$We evaluate each term:
* $\langle 0 | I | 0 \rangle = \langle 0 | 0 \rangle = 1$
* $\langle 0 | X | 0 \rangle = \langle 0 | 1 \rangle = 0$
* $\langle 0 | Y | 0 \rangle = \langle 0 | (i|1\rangle) = 0$
* $\langle 0 | Z | 0 \rangle = \langle 0 | (+1)|0\rangle = 1$

Plugging these values back in gives the probability:
$$P(+1) = \frac{1}{2} (1 + 0 + 0 + v_3) = \frac{1 + v_3}{2}$$

#### **2. Finding the Post-Measurement State**
When a measurement yields a specific outcome, the state of the system collapses. The new state is found by applying the projector to the initial state and then re-normalizing.
$$|\psi_{post}\rangle = \frac{P_+ |\psi\rangle}{\sqrt{P(+1)}}$$First, we apply the projector to the state $|0\rangle$:
$$P_+|0\rangle = \frac{I + v_1 X + v_2 Y + v_3 Z}{2} |0\rangle = \frac{1}{2}(I|0\rangle + v_1 X|0\rangle + v_2 Y|0\rangle + v_3 Z|0\rangle)$$$$= \frac{1}{2}(|0\rangle + v_1|1\rangle + iv_2|1\rangle + v_3|0\rangle) = \frac{1}{2}\left( (1+v_3)|0\rangle + (v_1+iv_2)|1\rangle \right)$$Now, we normalize this vector by dividing by $\sqrt{P(+1)} = \sqrt{\frac{1+v_3}{2}}$:$$|\psi_{post}\rangle = \frac{\frac{1}{2}\left( (1+v_3)|0\rangle + (v_1+iv_2)|1\rangle \right)}{\sqrt{\frac{1+v_3}{2}}} = \frac{(1+v_3)|0\rangle + (v_1+iv_2)|1\rangle}{\sqrt{2(1+v_3)}}$$

---

### **Solution 2: Using Eigenvectors and the Born Rule**

This method first finds the eigenvector corresponding to the +1 outcome and then uses the standard measurement postulates.

#### **1. Finding the Eigenvector for the +1 Outcome**
The post-measurement state will be the normalized eigenvector, let's call it $|\psi_+\rangle$, associated with the eigenvalue +1. We can find this vector by applying the projector $P_+$ to any state not orthogonal to the eigenspace (like $|0\rangle$) and normalizing the result. This is exactly the calculation we performed in the second part of Solution 1.

The normalized eigenvector for the eigenvalue +1 is:
$$|\psi_+\rangle = \frac{(1+v_3)|0\rangle + (v_1+iv_2)|1\rangle}{\sqrt{2(1+v_3)}}$$

#### **2. Calculating the Probability**
The probability of measuring +1 is given by the Born rule: $P(+1) = |\langle \psi_+ | \psi \rangle|^2$, where the initial state is $|\psi\rangle = |0\rangle$.

$$\langle \psi_+ | 0 \rangle = \frac{(1+v_3)\langle 0|0 \rangle + (v_1-iv_2)\langle 1|0 \rangle}{\sqrt{2(1+v_3)}} = \frac{1+v_3}{\sqrt{2(1+v_3)}}$$

Squaring the magnitude to find the probability:
$$P(+1) = \left| \frac{1+v_3}{\sqrt{2(1+v_3)}} \right|^2 = \frac{(1+v_3)^2}{2(1+v_3)} = \frac{1+v_3}{2}$$

#### **3. Finding the Post-Measurement State**
According to the measurement postulate, when a measurement yields the outcome +1, the system collapses to the corresponding normalized eigenvector.
Therefore, the post-measurement state is simply the eigenvector $|\psi_+\rangle$ we found in step 1.

Both methods yield the same results. The probability depends only on $v_3$, the component of the measurement axis along the z-axis, highlighting the relationship between the initial state $|0\rangle$ (an eigenstate of Z) and the general measurement. 🎯
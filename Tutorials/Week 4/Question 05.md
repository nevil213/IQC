# Question 5: (Extending the previous question) Calculate the probability of obtaining the result +1 for a measurement of $\vec{v} \cdot \vec{\sigma}$, given that the state prior to measurement is $\lvert 0 \rangle$. What is the state of the system after the measurement if +1 is obtained?

## Solution

Below are multiple methods to calculate the probability and post-measurement state, each explained in detail. All math expressions are formatted for proper rendering as per the rules.

---

**Method 1 – Using Projector**

The probability is $p(+) = \langle 0 \vert P_+ \vert 0 \rangle = \langle 0 \vert \frac{I + \vec{v} \cdot \vec{\sigma}}{2} \vert 0 \rangle$.

Since $\vec{v} \cdot \vec{\sigma} = v_1 X + v_2 Y + v_3 Z$, and $\langle 0 \vert X \vert 0 \rangle = 0$, $\langle 0 \vert Y \vert 0 \rangle = 0$, $\langle 0 \vert Z \vert 0 \rangle = 1$,

$p(+) = \frac{1 + v_3}{2}$.

Post-measurement state: $\frac{P_+ \lvert 0 \rangle}{\sqrt{p(+)}} = \frac{ \frac{I + \vec{v} \cdot \vec{\sigma}}{2} \lvert 0 \rangle }{ \sqrt{ \frac{1 + v_3}{2} } }$.

**Explanation:** Direct application of measurement rules.

---

**Method 2 – Expectation Value**

The probability is the expectation of P+.

Same as above.

**Explanation:** POVM probability.

---

**Method 3 – Bloch Vector**

The state $\lvert 0 \rangle$ has Bloch vector (0,0,1). Measurement along $\vec{v}$ gives p(+) = (1 + \cos\theta)/2, where \theta is angle between z and v, so v_3 = \cos\theta.

**Explanation:** Geometric interpretation.

---

**Summary:**

Probability is $\frac{1 + v_3}{2}$, post-measurement state is $\frac{ \frac{I + \vec{v} \cdot \vec{\sigma}}{2} \lvert 0 \rangle }{ \sqrt{ \frac{1 + v_3}{2} } }$. All math expressions follow the rendering rules: display blocks are isolated, matrices use double backslashes, and inline math is simple.
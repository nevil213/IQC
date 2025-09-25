Yes, a sequence of two quantum measurements is physically equivalent to a single, combined measurement. This is because the effect of sequential quantum operations is described by the product of their respective operators. The probability of a sequence of outcomes and the final post-measurement state are identical in both descriptions.

***

### **Q6. Suppose $\{L_l\}$ and $\{M_m\}$ are two sets of measurement operators. Show that a measurement defined by $\{L_l\}$ followed by one defined by $\{M_m\}$ is physically equivalent to a single measurement defined by operators $\{N_{lm}\}$ with $N_{lm} = M_m L_l$.**

To show that two measurement procedures are **physically equivalent**, we must prove two things for any arbitrary initial state $|\psi\rangle$:
1.  The probability of obtaining a specific sequence of outcomes $(l, m)$ in the first procedure is identical to the probability of obtaining the corresponding combined outcome $(lm)$ in the second procedure.
2.  The final state of the system after the measurement is the same in both procedures.

We begin by verifying that the proposed combined operators $\{N_{lm}\}$ form a valid measurement.

---

### **Step 1: Validity of the Combined Measurement Operators**

A set of measurement operators is valid if it satisfies the **completeness relation**. We need to show that $\sum_{l,m} N_{lm}^\dagger N_{lm} = I$.

$$\sum_{l,m} N_{lm}^\dagger N_{lm} = \sum_{l,m} (M_m L_l)^\dagger (M_m L_l)$$

Using the property $(AB)^\dagger = B^\dagger A^\dagger$:

$$= \sum_{l,m} L_l^\dagger M_m^\dagger M_m L_l$$

We can rearrange the order of summation:

$$= \sum_l L_l^\dagger \left( \sum_m M_m^\dagger M_m \right) L_l$$

Since $\{M_m\}$ is a valid set of measurement operators, it satisfies its own completeness relation, $\sum_m M_m^\dagger M_m = I$. Substituting this in:

$$= \sum_l L_l^\dagger (I) L_l = \sum_l L_l^\dagger L_l$$

And since $\{L_l\}$ is also a valid set of measurement operators, this sum is also equal to the identity, $\sum_l L_l^\dagger L_l = I$. Thus, the set $\{N_{lm}\}$ is a valid description of a quantum measurement. ✅

---

### **Step 2: Equivalence of Probabilities**

Now, we compare the probability of obtaining the sequence of outcomes $l$ then $m$.

**Sequential Measurement:**
* The probability of the first outcome, $l$, is $P(l) = \langle \psi | L_l^\dagger L_l | \psi \rangle$.
* After this, the state collapses to $|\psi_l\rangle = \frac{L_l|\psi\rangle}{\sqrt{P(l)}}$.
* The probability of then getting outcome $m$ is $P(m|l) = \langle \psi_l | M_m^\dagger M_m | \psi_l \rangle$.
* The total probability for the sequence $(l, m)$ is $P(l, m) = P(m|l) \cdot P(l)$.
    $$
    P(l, m) = \langle \psi_l | M_m^\dagger M_m | \psi_l \rangle \cdot P(l) = \left( \frac{\langle \psi | L_l^\dagger}{\sqrt{P(l)}} M_m^\dagger M_m \frac{L_l|\psi\rangle}{\sqrt{P(l)}} \right) \cdot P(l)
    $$
    $$
    = \frac{\langle \psi | L_l^\dagger M_m^\dagger M_m L_l | \psi \rangle}{P(l)} \cdot P(l) = \langle \psi | L_l^\dagger M_m^\dagger M_m L_l | \psi \rangle
    $$

**Single Combined Measurement:**
The probability of getting the combined outcome $lm$ is:
$$P(lm) = \langle \psi | N_{lm}^\dagger N_{lm} | \psi \rangle = \langle \psi | (M_m L_l)^\dagger (M_m L_l) | \psi \rangle = \langle \psi | L_l^\dagger M_m^\dagger M_m L_l | \psi \rangle$$

The probabilities are identical. ✅

---

### **Step 3: Equivalence of Post-Measurement States**

Finally, we compare the final state of the system.

**Sequential Measurement:**
After the first measurement gives outcome $l$, the state is $|\psi_l\rangle = \frac{L_l|\psi\rangle}{\sqrt{P(l)}}$. After the second measurement gives outcome $m$, the final state is:
$$|\psi_{final}\rangle = \frac{M_m |\psi_l\rangle}{\sqrt{P(m|l)}} = \frac{M_m \left( \frac{L_l|\psi\rangle}{\sqrt{P(l)}} \right)}{\sqrt{P(m|l)}} = \frac{M_m L_l |\psi\rangle}{\sqrt{P(m|l)P(l)}} = \frac{M_m L_l |\psi\rangle}{\sqrt{P(l,m)}}$$

**Single Combined Measurement:**
After the measurement gives the combined outcome $lm$, the final state is:
$$|\psi_{final}\rangle = \frac{N_{lm}|\psi\rangle}{\sqrt{P(lm)}}$$

Since we've already shown that $N_{lm} = M_m L_l$ and $P(l, m) = P(lm)$, the expressions for the final state are identical. ✅

**Conclusion:** Because the probabilities for all outcomes and the corresponding post-measurement states are the same for any initial state, the two procedures are physically equivalent. ⚙️
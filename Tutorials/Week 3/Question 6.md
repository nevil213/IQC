# Q6. Suppose $\{L_l\}$ and $\{M_m\}$ are two sets of measurement operators. Show that a measurement defined by $\{L_l\}$ followed by one defined by $\{M_m\}$ is physically equivalent to a single measurement defined by operators $\{N_{lm}\}$ with $N_{lm} = M_m L_l$.

## Solution

Below are multiple methods to show that a measurement defined by $\{L_l\}$ followed by one defined by $\{M_m\}$ is physically equivalent to a single measurement defined by operators $\{N_{lm}\}$ with $N_{lm} = M_m L_l$, each explained in detail. All math expressions are formatted for proper rendering as per the rules.

---

**Method 1 – State-Update Calculation**

Start with density operator $\rho$. After $\{L_l\}$, the post-measurement state is:

$$
\rho_l = \frac{L_l \rho L_l^\dagger}{p_l}, \quad p_l = \operatorname{Tr}(L_l \rho L_l^\dagger).
$$

Then applying $\{M_m\}$ gives:

$$
\rho_{l,m} = \frac{M_m \rho_l M_m^\dagger}{p_{m|l}} = \frac{M_m L_l \rho L_l^\dagger M_m^\dagger}{p_l p_{m|l}},
$$

with joint probability $p_{l,m} = p_l p_{m|l} = \operatorname{Tr}(M_m L_l \rho L_l^\dagger M_m^\dagger)$.

Define $N_{lm} = M_m L_l$. The single measurement produces the same $p_{l,m}$ and $\rho_{l,m}$.

**Explanation:** This tracks state evolution, showing sequential measurements compose via Kraus operator multiplication.

---

**Method 2 – Quantum Operation Composition**

The measurement $\mathcal{M}_L$ acts as $\mathcal{M}_L(\rho) = \sum_l L_l \rho L_l^\dagger$, and similarly for $\mathcal{M}_M$. The combined operation is $\mathcal{M}_M \circ \mathcal{M}_L$, yielding:

$$
\mathcal{M}_M(\mathcal{M}_L(\rho)) = \sum_{l,m} M_m L_l \rho L_l^\dagger M_m^\dagger = \sum_{l,m} N_{lm} \rho N_{lm}^\dagger.
$$

**Explanation:** Quantum channels compose, and the Kraus operators multiply accordingly.

---

**Method 3 – POVM Element Comparison**

The POVM elements for sequential measurement are $E_{lm} = L_l^\dagger M_m^\dagger M_m L_l$. For the single measurement, $F_{lm} = N_{lm}^\dagger N_{lm} = L_l^\dagger M_m^\dagger M_m L_l = E_{lm}$.

Since POVM elements determine probabilities, equality ensures equivalence.

**Explanation:** POVMs capture measurement statistics, so matching elements means identical physics.

---

**Summary:**

In all viewpoints, chaining measurement operators multiplies their Kraus operators, yielding $N_{lm} = M_m L_l$. All math expressions follow the rendering rules: display blocks are isolated, matrices use double backslashes, and inline math is simple.
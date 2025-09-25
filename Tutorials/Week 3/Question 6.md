<!-- Q6. Suppose {Ll} and {Mm} are two sets of measurement operators. Show that a measurement defined by {Ll} followed by one defined by {Mm} is physically equivalent
to a single measurement defined by operators {Nlm} with Nlm = MmLl
. -->

### Solution

Let $\{L_l\}$ and $\{M_m\}$ be measurement operators (Kraus operators) satisfying the completeness relations

$$
\sum_l L_l^\dagger L_l = I, \qquad \sum_m M_m^\dagger M_m = I.
$$

**Method 1 – State-update calculation.** Start with a density operator $\rho$. Performing the $\{L_l\}$ measurement and recording outcome $l$ yields post-measurement state

$$
\rho_l = \frac{L_l \rho L_l^\dagger}{p_l}, \qquad p_l = \operatorname{Tr}(L_l \rho L_l^\dagger).
$$

Applying the second measurement with outcome $m$ gives

$$
\rho_{l,m} = \frac{M_m \rho_l M_m^\dagger}{p_{m|l}} = \frac{M_m L_l \rho L_l^\dagger M_m^\dagger}{p_l p_{m|l}},
$$

where the conditional probability is $p_{m|l} = \operatorname{Tr}(M_m \rho_l M_m^\dagger)$. The joint probability of outcomes $(l, m)$ is

$$
p_{l,m} = p_l p_{m|l} = \operatorname{Tr}(M_m L_l \rho L_l^\dagger M_m^\dagger).
$$

Define $N_{l m} = M_m L_l$. Then the single measurement with operators $\{N_{l m}\}$ produces joint probability $\operatorname{Tr}(N_{l m} \rho N_{l m}^\dagger) = p_{l,m}$ and post-measurement state $N_{l m} \rho N_{l m}^\dagger / p_{l,m}$, exactly matching the sequential procedure.

**Method 2 – Quantum operation composition.** The measurement $\mathcal{M}_L$ acts as

$$
\mathcal{M}_L(\rho) = \sum_l L_l \rho L_l^\dagger,
$$

and $\mathcal{M}_M$ similarly. The combined channel is $\mathcal{M}_M \circ \mathcal{M}_L$, yielding

$$
\mathcal{M}_M \big( \mathcal{M}_L(\rho) \big) = \sum_{l,m} M_m L_l \rho L_l^\dagger M_m^\dagger = \sum_{l,m} N_{l m} \rho N_{l m}^\dagger.
$$

Thus the composite operation has Kraus operators $\{N_{l m}\}$, reinforcing the equivalence.

**Method 3 – POVM element comparison.** The POVM elements corresponding to the sequential measurement are

$$
E_{l m} = L_l^\dagger M_m^\dagger M_m L_l.
$$

For the single measurement using $N_{l m}$ we have

$$
F_{l m} = N_{l m}^\dagger N_{l m} = L_l^\dagger M_m^\dagger M_m L_l = E_{l m}.
$$

Since POVM elements determine measurement probabilities completely, equality of $E_{l m}$ and $F_{l m}$ ensures physical equivalence, including that $\sum_{l,m} F_{l m} = I$ because the original measurements were complete.

In all viewpoints, chaining measurement operators multiplies their Kraus operators, yielding $N_{l m} = M_m L_l$.
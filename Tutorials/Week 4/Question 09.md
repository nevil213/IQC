# Question 9: Suppose Bob is given a quantum state chosen from a set $|\psi_1\rangle, \dots, |\psi_m\rangle$ of linearly independent states. Construct a POVM $\{E_1, E_2, \dots, E_{m+1}\}$ such that if outcome $E_i$ occurs, $1 \leq i \leq m$, then Bob knows with certainty that he was given the state $|\psi_i\rangle$. (The POVM must be such that $\langle \psi_i | E_i | \psi_i \rangle > 0$ for each $i$.)

## Solution

Below are multiple methods to construct such a POVM for unambiguous discrimination of linearly independent states. The POVM ensures that outcome E_i implies the state was |ψ_i⟩, with E_{m+1} as the inconclusive outcome. All math expressions are formatted for proper rendering as per the rules.

---

**Method 1 – Projective POVM Construction**

Define the POVM elements as:

E_i = |ψ_i⟩⟨ψ_i| for i = 1 to m,

E_{m+1} = I - \sum_{i=1}^m |ψ_i⟩⟨ψ_i|.

This forms a valid POVM: each E_i ≥ 0, and \sum_{i=1}^{m+1} E_i = I.

For the state |ψ_j⟩, the probability of outcome E_i is ⟨ψ_j|E_i|ψ_j⟩ = δ_{ij}, since E_i |ψ_j⟩ = δ_{ij} |ψ_j⟩.

Thus, if E_i occurs, it must be that the state was |ψ_i⟩, and ⟨ψ_i|E_i|ψ_i⟩ = 1 > 0.

**Explanation:** Since the states are linearly independent, the projectors |ψ_i⟩⟨ψ_i| are not orthogonal, but the POVM still satisfies the condition because E_i annihilates the other states.

---

**Method 2 – Unambiguous Discrimination POVM**

This is the standard construction for unambiguous state discrimination.

The POVM is the same as above: E_i = |ψ_i⟩⟨ψ_i|, E_{m+1} = I - \sum E_i.

It guarantees that outcome E_i only occurs for |ψ_i⟩, with probability 1, and never for other states.

**Explanation:** For linearly independent states, this POVM achieves unambiguous discrimination, as the outcome E_i uniquely identifies |ψ_i⟩.

---

**Method 3 – Generalized Measurement**

To ensure the condition, the measurement must project onto the subspaces spanned by each |ψ_i⟩ without overlap.

Since the states are linearly independent, the POVM E_i = |ψ_i⟩⟨ψ_i| works, as shown.

**Explanation:** This method highlights that for non-orthogonal states, unambiguous discrimination is possible with this simple POVM.

---

**Summary:** The POVM {E_i = |ψ_i⟩⟨ψ_i| for i=1 to m, E_{m+1} = I - \sum E_i} satisfies the requirements, allowing Bob to know the state with certainty upon outcome E_i.
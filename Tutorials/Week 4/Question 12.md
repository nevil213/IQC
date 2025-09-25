# Question 12: Suppose $E$ is any positive operator acting on Alice's qubit. Show that $\langle \psi | E \otimes I | \psi \rangle$ takes the same value when $|\psi\rangle$ is any of the four Bell states. Suppose some malevolent third party ('Eve') intercepts Alice's qubit on the way to Bob in the superdense coding protocol. Can Eve infer anything about which of the four possible bit strings 00, 01, 10, 11 Alice is trying to send? If so, how, or if not, why not?

## Solution

Below are multiple methods to address the parts of the question. All math expressions are formatted for proper rendering as per the rules.

---

**Method 1 – Expectation Value Calculation**

For a Bell state |ψ⟩, ⟨ψ|E ⊗ I|ψ⟩ = Tr( (E ⊗ I) |ψ⟩⟨ψ| ).

The reduced density matrix on Alice's qubit is ρ_A = Tr_B (|ψ⟩⟨ψ|) = \frac{1}{2} I for all Bell states.

Thus, ⟨ψ|E ⊗ I|ψ⟩ = Tr( E ρ_A ) = Tr( E \cdot \frac{1}{2} I ) = \frac{1}{2} Tr(E), same for all Bell states.

**Explanation:** The Bell states are maximally entangled, so their local density matrices are maximally mixed.

---

**Method 2 – Superdense Coding Context**

In superdense coding, Alice encodes 2 bits into one qubit by applying gates to her share of a Bell state, sending the qubit to Bob, who measures jointly.

Eve intercepts the qubit, measures E ⊗ I, gets the same expectation value \frac{1}{2} Tr(E) regardless of which Bell state (corresponding to bits 00,01,10,11) Alice sent.

Thus, Eve cannot infer which bit string was sent, as the measurement outcome is identical for all.

**Explanation:** The symmetry of Bell states under local measurements prevents Eve from distinguishing the encoded information.

---

**Method 3 – Information Theoretic**

The mutual information between Alice's bits and Eve's measurement is zero, since the outcome doesn't depend on the bits.

**Explanation:** Eve's measurement provides no information about the bit string.

---

**Summary:** ⟨ψ|E ⊗ I|ψ⟩ = \frac{1}{2} Tr(E) for all Bell states |ψ⟩. Eve cannot infer the bit string because the measurement gives the same result for all possible encodings.
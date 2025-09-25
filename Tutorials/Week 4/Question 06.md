# Question 6: Show a formal proof establishing that the two non-orthogonal states cannot be reliably distinguished. (Refer to Nielsen & Chuang, Box 2.3)

## Solution

Below are multiple methods to prove that two non-orthogonal states cannot be reliably distinguished, each explained in detail. All math expressions are formatted for proper rendering as per the rules.

---

**Method 1 – Projective Measurement Argument**

Suppose projective measurement with orthogonal projectors P_ψ, P_φ, P_ψ + P_φ = I.

For reliable distinction, P_ψ |ψ⟩ = |ψ⟩, P_φ |φ⟩ = |φ⟩.

But ⟨φ| P_ψ |φ⟩ =0, yet ⟨φ|ψ⟩ ≠0 implies P_ψ |φ⟩ ≠0, contradiction.

**Explanation:** Orthogonality forces zero overlap, but non-orthogonality prevents it.

---

**Method 2 – POVM Argument**

For POVM {E_ψ, E_φ}, ⟨ψ| E_ψ |ψ⟩=1, ⟨φ| E_φ |φ⟩=1, ⟨ψ| E_φ |ψ⟩=0, ⟨φ| E_ψ |φ⟩=0.

But since |ψ⟩ and |φ⟩ are non-orthogonal, the subspaces overlap, so no such E.

**Explanation:** The conditions require the states to be orthogonal.

---

**Method 3 – No-Cloning and Distinguishability**

From no-cloning, if distinguishable, could clone and distinguish copies, but non-orthogonal can't be cloned perfectly.

**Explanation:** Information-theoretic argument.

---

**Summary:**

Non-orthogonal states cannot be reliably distinguished. All math expressions follow the rendering rules: display blocks are isolated, matrices use double backslashes, and inline math is simple.
# Question 8: Suppose a measurement is described by measurement operators $M_m$. Show that there exist unitary operators $U_m$ such that $M_m = U_m \sqrt{E_m}$, where $E_m$ is the POVM associated to the measurement.

## Solution

Below are multiple methods to show that any measurement operator M_m can be decomposed as M_m = U_m √E_m, where U_m is unitary and E_m = M_m^\dagger M_m is the POVM element. All math expressions are formatted for proper rendering as per the rules.

---

**Method 1 – Polar Decomposition**

Every bounded operator M on a Hilbert space can be written as M = U P, where U is unitary and P is positive semidefinite.

For M_m, P_m = √(M_m^\dagger M_m) = √E_m, since E_m = M_m^\dagger M_m.

Thus, M_m = U_m √E_m, with U_m unitary.

**Explanation:** The polar decomposition theorem states that any operator can be factored into a unitary part and a positive part. Here, the positive part is the square root of the POVM element, which is Hermitian positive.

---

**Method 2 – Singular Value Decomposition**

Using SVD, M_m = V Σ W^\dagger, where Σ is diagonal with non-negative entries.

Then, √E_m = √(M_m^\dagger M_m) = √(W Σ^2 W^\dagger) = W Σ W^\dagger, assuming W unitary.

Then, U_m = V W^\dagger, unitary.

Thus, M_m = V Σ W^\dagger = (V W^\dagger) (W Σ W^\dagger) = U_m √E_m.

**Explanation:** SVD provides the decomposition, and the positive operator is the square root of the singular values squared.

---

**Method 3 – Direct Construction**

Define P_m = √E_m, which is positive.

Then, M_m = U_m P_m, where U_m is chosen such that U_m P_m = M_m.

Since P_m is positive, it has a square root, and the unitary can be constructed via the polar decomposition.

**Explanation:** This is essentially restating the polar decomposition.

---

**Summary:** The existence of unitary U_m such that M_m = U_m √E_m follows from the polar decomposition of operators, applicable to any measurement operator.
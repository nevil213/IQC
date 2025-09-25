Yes, any positive operator is necessarily Hermitian. The definition of a positive operator requires its expectation value, $\langle \psi | A | \psi \rangle$, to be a real number for any state $|\psi\rangle$. This fundamental requirement forces the operator to be equal to its own conjugate transpose.

***

### **Q8. Show that a positive operator is necessarily Hermitian.**

An operator $A$ is defined as **positive** (or positive semi-definite) if for every vector $|\psi\rangle$ in the state space, the following condition holds:

$$\langle \psi | A | \psi \rangle \ge 0$$

This implies that the expectation value of a positive operator is always a real, non-negative number. An operator is **Hermitian** if it is equal to its Hermitian conjugate (adjoint), $A = A^\dagger$. We will show that the first condition implies the second.

---

## **Solution 1: Proof using the Polarization Identity**

This proof shows that if the "diagonal" elements $\langle \psi | A | \psi \rangle$ are real, then the "off-diagonal" elements must behave in a way that forces the operator to be Hermitian.

**1. The Setup**
To prove that $A$ is Hermitian, we must show that $\langle \phi | A | \psi \rangle = \langle \phi | A^\dagger | \psi \rangle$ for any two vectors $|\psi\rangle$ and $|\phi\rangle$. By the definition of the adjoint, this is equivalent to proving:

$$\langle \phi | A | \psi \rangle = (\langle \psi | A | \phi \rangle)^*$$

**2. Applying the Positivity Condition**
Let's consider the expectation value of $A$ for a superposition state $|\chi\rangle = |\phi\rangle + |\psi\rangle$. We know it must be real.

$$\langle \phi+\psi | A | \phi+\psi \rangle = \langle \phi | A | \phi \rangle + \langle \psi | A | \psi \rangle + \langle \phi | A | \psi \rangle + \langle \psi | A | \phi \rangle$$

Since the left-hand side and the first two terms on the right are real by definition, the sum of the last two terms must also be real:
$$\langle \phi | A | \psi \rangle + \langle \psi | A | \phi \rangle \in \mathbb{R}$$
Now, let's consider a different superposition, $|\chi'\rangle = |\phi\rangle + i|\psi\rangle$. Its expectation value must also be real.

$$\langle \phi+i\psi | A | \phi+i\psi \rangle = \langle \phi|A|\phi \rangle - i^2\langle \psi|A|\psi \rangle + i\langle \phi|A|\psi \rangle - i\langle \psi|A|\phi \rangle$$

$$= \langle \phi|A|\phi \rangle + \langle \psi|A|\psi \rangle + i(\langle \phi|A|\psi \rangle - \langle \psi|A|\phi \rangle)$$

For this entire expression to be real, the last term must be purely real. For $i \times z$ to be real, $z$ must be purely imaginary. Therefore:
$$\langle \phi | A | \psi \rangle - \langle \psi | A | \phi \rangle \in i\mathbb{R}$$
**3. The Conclusion**
Let $X = \langle \phi | A | \psi \rangle$ and $Y = \langle \psi | A | \phi \rangle$. We have shown:
* $X+Y$ is real.
* $X-Y$ is purely imaginary.

If we let $X=a+ib$ and $Y=c+id$, the first condition implies $b+d=0$, and the second implies $a-c=0$. This gives us $a=c$ and $b=-d$. Therefore, $Y = c+id = a-ib = X^*$.

This means $\langle \psi | A | \phi \rangle = (\langle \phi | A | \psi \rangle)^*$, which is the condition for $A$ to be a Hermitian operator. ✅

---

## **Solution 2: Proof using Operator Decomposition**

This proof relies on the fact that any operator can be uniquely decomposed into a Hermitian and an anti-Hermitian part.

**1. The Decomposition**
Any operator $A$ can be written as $A = H_1 + iH_2$, where $H_1$ and $H_2$ are both Hermitian operators, defined as:
$$H_1 = \frac{A+A^\dagger}{2} \quad , \quad H_2 = \frac{A-A^\dagger}{2i}$$

**2. Applying the Positivity Condition**
Let's compute the expectation value of $A$ for an arbitrary state $|\psi\rangle$:
$$\langle \psi | A | \psi \rangle = \langle \psi | (H_1 + iH_2) | \psi \rangle = \langle \psi | H_1 | \psi \rangle + i \langle \psi | H_2 | \psi \rangle$$

**3. The Contradiction**
The expectation value of any Hermitian operator is always a real number. Therefore, both $\langle \psi | H_1 | \psi \rangle$ and $\langle \psi | H_2 | \psi \rangle$ are real.

The positivity condition for $A$ requires that $\langle \psi | A | \psi \rangle$ must be real for *any* state $|\psi\rangle$. For this to be true, the imaginary part of our expression must be zero:

$$i \langle \psi | H_2 | \psi \rangle = 0 \implies \langle \psi | H_2 | \psi \rangle = 0$$

This must hold for **all** possible states $|\psi\rangle$.

**4. The Conclusion**
If the expectation value of a Hermitian operator ($H_2$ in this case) is zero for every possible state, then the operator itself must be the zero operator.
$$H_2 = \mathbf{0}$$Substituting the definition of $H_2$:$$\frac{A-A^\dagger}{2i} = \mathbf{0} \implies A-A^\dagger = \mathbf{0} \implies A = A^\dagger$$
This proves that the operator $A$ must be Hermitian. 🏛️
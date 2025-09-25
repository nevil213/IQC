This problem describes a measurement strategy known as **unambiguous state discrimination**. The goal is to design a measurement that can, some of the time, perfectly identify which state from a known set was provided. The trade-off is that the measurement must also include an "I don't know" or inconclusive outcome for the times when a perfect distinction is not possible.

***

### **Question 9: Suppose Bob is given a quantum state chosen from a set $|\psi_1\rangle, \dots, |\psi_m\rangle$ of linearly independent states. Construct a POVM $\{E_1, E_2, \dots, E_{m+1}\}$ such that if outcome $E_i$ occurs, $1 \leq i \leq m$, then Bob knows with certainty that he was given the state $|\psi_i\rangle$.**

### **1. Formalizing the Conditions**

Let's translate the requirements for our POVM elements $\{E_1, \dots, E_{m+1}\}$ into mathematical conditions.

1.  **Certainty:** The condition "if outcome $i$ occurs, the state was $|\psi_i\rangle$" means that the probability of getting outcome $i$ if the state was anything else ($|\psi_j\rangle$ where $j \neq i$) must be zero.
    $$
    P(i|j) = \langle \psi_j | E_i | \psi_j \rangle = 0 \quad \text{for all } j \neq i
    $$
    Since POVM elements are positive semi-definite, this is equivalent to the stronger condition:
    $$
    E_i |\psi_j\rangle = 0 \quad \text{for all } j \neq i
    $$
2.  **Non-Zero Success Probability:** The measurement must have a chance of succeeding.
    $$
    P(i|i) = \langle \psi_i | E_i | \psi_i \rangle > 0 \quad \text{for all } i \in \{1, \dots, m\}
    $$
3.  **Completeness:** The set must be a valid POVM.
    $$
    \sum_{k=1}^{m+1} E_k = I
    $$

### **2. The Construction**

The construction hinges on finding special "detection" states that are orthogonal to all but one of the possible input states.

#### **Step 1: Define the "Detection States"**
For each state $|\psi_i\rangle$ in our set, we define a corresponding subspace $S_i$ that is the span of all the *other* states:
$$S_i \equiv \text{span}\{|\psi_j\rangle \text{ for } j \neq i\}$$
Since the set $\{|\psi_1\rangle, \dots, |\psi_m\rangle\}$ is **linearly independent**, we know that the state $|\psi_i\rangle$ is not in the subspace $S_i$. This means $|\psi_i\rangle$ has a non-zero component that is orthogonal to the subspace $S_i$.

Let $P_{S_i}$ be the projector onto the subspace $S_i$. We define an unnormalized state $|\phi_i\rangle$ by projecting $|\psi_i\rangle$ onto the subspace *orthogonal* to $S_i$:
$$|\phi_i\rangle \equiv (I - P_{S_i})|\psi_i\rangle$$This vector $|\phi_i\rangle$ is, by construction, orthogonal to all $|\psi_j\rangle$ where $j \neq i$. We then normalize it to create our "detection state" $|\tilde{\psi}_i\rangle$:$$|\tilde{\psi}_i\rangle = \frac{|\phi_i\rangle}{\sqrt{\langle \phi_i | \phi_i \rangle}}$$

#### **Step 2: Define the "Conclusive" POVM Elements**
We now define the first $m$ POVM elements as scaled projectors onto these detection states:
$$E_i = c_i |\tilde{\psi}_i\rangle\langle\tilde{\psi}_i| \quad \text{for } i=1, \dots, m$$where $c_i$ are positive real numbers that we will determine later.

Let's check if this form meets the first two conditions:
* **Certainty:** For any $j \neq i$, the state $|\psi_j\rangle$ is in the subspace $S_i$. Our detection state $|\tilde{\psi}_i\rangle$ is orthogonal to $S_i$. Therefore, $\langle \tilde{\psi}_i | \psi_j \rangle = 0$, which means:
  $$E_i |\psi_j\rangle = c_i |\tilde{\psi}_i\rangle \langle \tilde{\psi}_i | \psi_j \rangle = 0$$
  The certainty condition is satisfied. ✅
* **Non-Zero Success:** We need $\langle \psi_i | E_i | \psi_i \rangle > 0$.
  $$\langle \psi_i | E_i | \psi_i \rangle = c_i |\langle \psi_i | \tilde{\psi}_i \rangle|^2$$
  The inner product $\langle \psi_i | \tilde{\psi}_i \rangle$ is the projection of $|\psi_i\rangle$ onto $|\tilde{\psi}_i\rangle$. Since $|\tilde{\psi}_i\rangle$ was constructed from the non-zero part of $|\psi_i\rangle$ orthogonal to $S_i$, this projection is non-zero. As long as we choose $c_i > 0$, this condition is satisfied. ✅

#### **Step 3: Define the "Inconclusive" POVM Element**
The final POVM element, $E_{m+1}$, is the "I don't know" result. It is defined by whatever is left over to satisfy the completeness relation:
$$E_{m+1} \equiv I - \sum_{i=1}^m E_i = I - \sum_{i=1}^m c_i |\tilde{\psi}_i\rangle\langle\tilde{\psi}_i|$$

#### **Step 4: Ensure Validity**
For $\{E_k\}$ to be a valid POVM, the operator $E_{m+1}$ must be positive semi-definite. This means that for any state $|\phi\rangle$, we must have $\langle \phi | E_{m+1} | \phi \rangle \ge 0$. This imposes a constraint on our choice of the constants $c_i$:
$$\left\langle \phi \left| I - \sum_{i=1}^m c_i |\tilde{\psi}_i\rangle\langle\tilde{\psi}_i| \right| \phi \right\rangle \ge 0$$
$$\implies \sum_{i=1}^m c_i |\langle \phi | \tilde{\psi}_i \rangle|^2 \le 1$$
This condition means that the operator $\sum_{i=1}^m E_i$ must have all its eigenvalues less than or equal to 1. We can always satisfy this by choosing the positive constants $c_i$ to be sufficiently small.

**Conclusion:** The constructed set of operators $\{E_1, \dots, E_{m+1}\}$ forms a valid POVM that allows for the unambiguous discrimination of the linearly independent states $\{|\psi_i\rangle\}$, at the cost of having a non-zero probability of an inconclusive result. 🤔
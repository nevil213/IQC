No, Eve cannot infer anything about Alice's message. Because the four Bell states are maximally entangled, the state of the single qubit Eve intercepts is the **maximally mixed state** ($I/2$) regardless of which message Alice encoded. This state contains no information, making it impossible for Eve to distinguish between the four possibilities.

-----

### **Question 12: Suppose $E$ is any positive operator acting on Alice's qubit. Show that $\\langle \\psi | E \\otimes I | \\psi \\rangle$ takes the same value when $|\\psi\\rangle$ is any of the four Bell states. Suppose some malevolent third party ('Eve') intercepts Alice's qubit on the way to Bob in the superdense coding protocol. Can Eve infer anything about which of the four possible bit strings 00, 01, 10, 11 Alice is trying to send?**

-----

## **Part 1: Expectation Value on Bell States**

We need to show that the expectation value of the operator $E \\otimes I$ is the same for all four Bell states. We can prove this using two methods.

### **Solution 1.1: Direct Calculation**

Let $E$ be a general operator on a single qubit, represented by the matrix $E = \\begin{pmatrix} e\_{00} & e\_{01} \\ e\_{10} & e\_{11} \\end{pmatrix}$. The operator on the two-qubit space is:

$$
E \otimes I = \begin{pmatrix}
e_{00} & 0 & e_{01} & 0 \\\\
0 & e_{00} & 0 & e_{01} \\\\
e_{10} & 0 & e_{11} & 0 \\\\
0 & e_{10} & 0 & e_{11}
\end{pmatrix}
$$Let's calculate the expectation value $\\langle \\psi | E \\otimes I | \\psi \\rangle$ for two representative Bell states.

* **For $|\\Phi^+\\rangle = \\frac{1}{\\sqrt{2}}(|00\\rangle + |11\\rangle)$**:
$$

```
$$\\langle \\Phi^+ | E \\otimes I | \\Phi^+ \\rangle = \\frac{1}{2} \\begin{pmatrix} 1 & 0 & 0 & 1 \\end{pmatrix} \\begin{pmatrix}
e\_{00} & 0 & e\_{01} & 0 \\\\
0 & e\_{00} & 0 & e\_{01} \\\\
e\_{10} & 0 & e\_{11} & 0 \\\\
0 & e\_{10} & 0 & e\_{11}
\\end{pmatrix} \\begin{pmatrix} 1 \\\\ 0 \\\\ 0 \\\\ 1 \\end{pmatrix} = \\frac{1}{2}(e\_{00} + e\_{11})
$$
$$
```

  * **For $|\\Psi^+\\rangle = \\frac{1}{\\sqrt{2}}(|01\\rangle + |10\\rangle)$**:
    $$
    $$$$\\langle \\Psi^+ | E \\otimes I | \\Psi^+ \\rangle = \\frac{1}{2} \\begin{pmatrix} 0 & 1 & 1 & 0 \\end{pmatrix} \\begin{pmatrix}
    e\_{00} & 0 & e\_{01} & 0 \\\\
    0 & e\_{00} & 0 & e\_{01} \\\\
    e\_{10} & 0 & e\_{11} & 0 \\\\
    0 & e\_{10} & 0 & e\_{11}
    \\end{pmatrix} \\begin{pmatrix} 0 \\\\ 1 \\\\ 1 \\\\ 0 \\end{pmatrix} = \\frac{1}{2}(e\_{00} + e\_{11})
    $$
    $$$$
    $$Similar calculations for $|\\Phi^-\\rangle$ and $|\\Psi^-\\rangle$ also yield the same result. The expectation value for any of the four Bell states is:

$$\langle \psi | E \otimes I | \psi \rangle = \frac{e_{00} + e_{11}}{2} = \frac{\text{Tr}(E)}{2}$$

Since the result only depends on the trace of $E$, it is the same for all four Bell states.

### **Solution 1.2: Using the Reduced Density Matrix**

A more elegant proof uses the density matrix formalism. The expectation value of an observable $A$ on a system with density matrix $\\rho$ is $\\text{Tr}(A\\rho)$.
For an operator like $E \\otimes I$ that acts only on a subsystem (Alice's qubit A), the expectation value is given by:

$$\langle E \otimes I \rangle = \text{Tr}_A(E \rho_A)$$

where $\\rho\_A = \\text{Tr}\_B(\\rho)$ is the **reduced density matrix** of Alice's qubit, found by tracing out Bob's qubit (B).

For any of the four Bell states, the reduced density matrix of a single qubit is the **maximally mixed state**:

$$\rho_A = \frac{1}{2}I = \frac{1}{2}\begin{pmatrix} 1 & 0 \\\\ 0 & 1 \end{pmatrix}$$

Since $\\rho\_A$ is identical for all four Bell states, the expectation value of any operator $E$ acting on that qubit must also be identical:

$$\langle E \otimes I \rangle = \text{Tr}(E \rho_A) = \text{Tr}\left(E \frac{I}{2}\right) = \frac{1}{2}\text{Tr}(E)$$

This confirms that the expectation value is the same regardless of which Bell state the system is in.

-----

## **Part 2: Superdense Coding and Eavesdropping**

In the **superdense coding protocol**, Alice encodes one of four possible messages (00, 01, 10, 11) by applying a corresponding Pauli gate (I, X, Z, or Y) to her half of a shared Bell pair, transforming it into one of the four Bell states. She then sends her qubit to Bob.

**The Eavesdropper's Dilemma**
Eve intercepts Alice's qubit *after* Alice has performed her operation. To learn the message, Eve must distinguish which of the four Bell states the pair is in by only measuring the single qubit she holds.

**Why Eve Cannot Infer the Message**
As we proved in Part 1, the state of Alice's single qubit is described by the **exact same reduced density matrix, $\\rho\_A = I/2$, for all four Bell states**.

  * The maximally mixed state $\\rho\_A = I/2$ represents a state of complete randomness—it has a 50% chance of being measured as $|0\\rangle$ and a 50% chance of being measured as $|1\\rangle$, regardless of the measurement basis.
  * Since the state of the qubit Eve possesses is **identical** for all four possible messages, there are no physical differences for her to measure. Any measurement she performs will yield a random outcome that is uncorrelated with Alice's message.

The two bits of information are not encoded in Alice's qubit alone; they are encoded **non-locally** in the correlations *between* Alice's and Bob's qubits. Without access to Bob's qubit, the information is completely inaccessible to Eve. 🔒
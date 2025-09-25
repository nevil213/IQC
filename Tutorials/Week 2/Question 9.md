<!-- 9. Let |ψ⟩ = (|0⟩+ |1⟩)/√2. Write out |ψ⟩⊗2and |ψ⟩⊗3explicitly, both in terms of
tensor products like |0⟩|1⟩, and using the Kronecker product. -->

## Solution

The state is defined as:

$$
|\psi\rangle = \frac{1}{\sqrt{2}} (|0\rangle + |1\rangle)
$$

### |ψ⟩⊗2

In terms of tensor products:

$$
|\psi\rangle \otimes |\psi\rangle = \frac{1}{\sqrt{2}} (|0\rangle + |1\rangle) \otimes \frac{1}{\sqrt{2}} (|0\rangle + |1\rangle) = \frac{1}{2} \left( |0\rangle|0\rangle + |0\rangle|1\rangle + |1\rangle|0\rangle + |1\rangle|1\rangle \right) = \frac{1}{2} \left( |00\rangle + |01\rangle + |10\rangle + |11\rangle \right)
$$

Using Kronecker product (assuming column vectors $|0\rangle = \begin{pmatrix} 1 \\ 0 \end{pmatrix}$, $|1\rangle = \begin{pmatrix} 0 \\ 1 \end{pmatrix}$):

$$
|\psi\rangle = \frac{1}{\sqrt{2}} \begin{pmatrix}
1 \\\\
1
\end{pmatrix}
$$

$$
|\psi\rangle \otimes |\psi\rangle = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\ 1 \end{pmatrix} \otimes \frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\ 1 \end{pmatrix} = \frac{1}{2} \begin{pmatrix}
1 \\\\
1 \\\\
1 \\\\
1
\end{pmatrix}
$$

### |ψ⟩⊗3

In terms of tensor products:

$$
|\psi\rangle \otimes |\psi\rangle \otimes |\psi\rangle = \frac{1}{2} \left( |00\rangle + |01\rangle + |10\rangle + |11\rangle \right) \otimes |\psi\rangle = \frac{1}{2} \cdot \frac{1}{\sqrt{2}} \left( |00\rangle \otimes (|0\rangle + |1\rangle) + |01\rangle \otimes (|0\rangle + |1\rangle) + |10\rangle \otimes (|0\rangle + |1\rangle) + |11\rangle \otimes (|0\rangle + |1\rangle) \right)
$$

$$
= \frac{1}{2\sqrt{2}} \left( |000\rangle + |001\rangle + |010\rangle + |011\rangle + |100\rangle + |101\rangle + |110\rangle + |111\rangle \right)
$$

Using Kronecker product:

$$
|\psi\rangle \otimes |\psi\rangle \otimes |\psi\rangle = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\ 1 \end{pmatrix} \otimes \frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\ 1 \end{pmatrix} \otimes \frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\ 1 \end{pmatrix} = \frac{1}{2\sqrt{2}} \begin{pmatrix}
1 \\\\
1 \\\\
1 \\\\
1 \\\\
1 \\\\
1 \\\\
1 \\\\
1
\end{pmatrix}
$$

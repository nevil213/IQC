Here's the truth table for the CNOT gate.

The **Controlled-NOT (CNOT)** gate is a fundamental two-qubit quantum gate that performs a NOT (or bit-flip) operation on one qubit (the **target**) only when a second qubit (the **control**) is in the state $|1\rangle$. If the control qubit is $|0\rangle$, the target qubit is left unchanged.

### **Question 1: Give the truth table of the Controlled-NOT (CNOT) gate when applied to the two-qubit computational basis {$|00\rangle,|01\rangle,|10\rangle,|11\rangle$}.

***

### **Solution 1: The Logical Rule-Based Method**

This method determines the output by applying the simple logical rule of the CNOT gate. By convention, the first qubit in the ket notation $|ct\rangle$ is the **control qubit**, and the second is the **target qubit**. 

The rule is:
* If the control qubit is **0**, do nothing to the target qubit.
* If the control qubit is **1**, flip the target qubit (apply a NOT or X gate).

Let's apply this to each basis state:

1.  **Input $|00\rangle$**: The control qubit is $|0\rangle$. The rule says to do nothing to the target. The output is **$|00\rangle$**.
2.  **Input $|01\rangle$**: The control qubit is $|0\rangle$. The rule says to do nothing to the target. The output is **$|01\rangle$**.
3.  **Input $|10\rangle$**: The control qubit is $|1\rangle$. The rule says to flip the target. The target $|0\rangle$ flips to $|1\rangle$. The output is **$|11\rangle$**.
4.  **Input $|11\rangle$**: The control qubit is $|1\rangle$. The rule says to flip the target. The target $|1\rangle$ flips to $|0\rangle$. The output is **$|10\rangle$**.

#### **Truth Table**

This logic can be summarized in the following truth table:

| Input State | Input (Control, Target) | Output (Control, Target) | Output State |
| :---------: | :---------------------: | :----------------------: | :----------: |
| $|00\rangle$ |          (0, 0)           |          (0, 0)          | $|00\rangle$ |
| $|01\rangle$ |          (0, 1)           |          (0, 1)          | $|01\rangle$ |
| $|10\rangle$ |          (1, 0)           |          (1, 1)          | $|11\rangle$ |
| $|11\rangle$ |          (1, 1)           |          (1, 0)          | $|10\rangle$ |

***

### **Solution 2: The Matrix Multiplication Method**

This method uses the matrix representation of the CNOT gate to calculate the output state for each basis vector. In the computational basis ordered as $\{|00\rangle, |01\rangle, |10\rangle, |11\rangle\}$, the CNOT matrix is:

$$
\text{CNOT} = \begin{pmatrix}
1 & 0 & 0 & 0 \\\\
0 & 1 & 0 & 0 \\\\
0 & 0 & 0 & 1 \\\\
0 & 0 & 1 & 0
\end{pmatrix}
$$

The basis states are represented by the following column vectors:
$$
|00\rangle = \begin{pmatrix} 1 \\\\ 0 \\\\ 0 \\\\ 0 \end{pmatrix} \quad
|01\rangle = \begin{pmatrix} 0 \\\\ 1 \\\\ 0 \\\\ 0 \end{pmatrix} \quad
|10\rangle = \begin{pmatrix} 0 \\\\ 0 \\\\ 1 \\\\ 0 \end{pmatrix} \quad
|11\rangle = \begin{pmatrix} 0 \\\\ 0 \\\\ 0 \\\\ 1 \end{pmatrix}
$$

Now, we apply the CNOT matrix to each basis vector:

1.  **Input $|00\rangle$**:
    $$
    \begin{pmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{pmatrix} \begin{pmatrix} 1 \\\\ 0 \\\\ 0 \\\\ 0 \end{pmatrix} = \begin{pmatrix} 1 \\\\ 0 \\\\ 0 \\\\ 0 \end{pmatrix} \implies |00\rangle
    $$
2.  **Input $|01\rangle$**:
    $$
    \begin{pmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{pmatrix} \begin{pmatrix} 0 \\\\ 1 \\\\ 0 \\\\ 0 \end{pmatrix} = \begin{pmatrix} 0 \\\\ 1 \\\\ 0 \\\\ 0 \end{pmatrix} \implies |01\rangle
    $$
3.  **Input $|10\rangle$**:
    $$
    \begin{pmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{pmatrix} \begin{pmatrix} 0 \\\\ 0 \\\\ 1 \\\\ 0 \end{pmatrix} = \begin{pmatrix} 0 \\\\ 0 \\\\ 0 \\\\ 1 \end{pmatrix} \implies |11\rangle
    $$
4.  **Input $|11\rangle$**:
    $$
    \begin{pmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{pmatrix} \begin{pmatrix} 0 \\\\ 0 \\\\ 0 \\\\ 1 \end{pmatrix} = \begin{pmatrix} 0 \\\\ 0 \\\\ 1 \\\\ 0 \end{pmatrix} \implies |10\rangle
    $$

The results from the matrix multiplication perfectly match the truth table derived from the logical rule. Both methods show how the CNOT gate permutes the computational basis states. 🔢
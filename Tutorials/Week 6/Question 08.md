Yes, just as any single-qubit unitary can be decomposed using Z-Y-Z rotations, it can also be decomposed using an X-Y-X sequence. This is because any arbitrary 3D rotation can be described by applying three successive rotations around different axes. Here is the explicit derivation of that form.

***

### **Question 8: Give a decomposition analogous to Theorem 0.1 but using $R_x$ instead of $R_z$, i.e. express a general unitary as $U = e^{i\alpha} R_x(\beta) R_y(\gamma) R_x(\delta)$.**

Our goal is to find the explicit matrix form that results from the product $U = e^{i\alpha} R_x(\beta) R_y(\gamma) R_x(\delta)$. This requires performing the matrix multiplication of the constituent rotation operators.

#### **Step 1: Define the Rotation Matrices**

First, let's write down the necessary rotation matrices.
$$
R_x(\theta) = \begin{pmatrix}
\cos(\theta/2) & -i\sin(\theta/2) \\\\
-i\sin(\theta/2) & \cos(\theta/2)
\end{pmatrix}
\quad , \quad
R_y(\theta) = \begin{pmatrix}
\cos(\theta/2) & -\sin(\theta/2) \\\\
\sin(\theta/2) & \cos(\theta/2)
\end{pmatrix}
$$

#### **Step 2: Compute the Product of Rotations**

We'll compute the product from right to left, starting with $R_y(\gamma)R_x(\delta)$.

$$
R_y(\gamma)R_x(\delta) = \begin{pmatrix}
\cos(\gamma/2) & -\sin(\gamma/2) \\\\
\sin(\gamma/2) & \cos(\gamma/2)
\end{pmatrix}
\begin{pmatrix}
\cos(\delta/2) & -i\sin(\delta/2) \\\\
-i\sin(\delta/2) & \cos(\delta/2)
\end{pmatrix}
$$

$$
= \begin{pmatrix}
\cos(\frac{\gamma}{2})\cos(\frac{\delta}{2}) + i\sin(\frac{\gamma}{2})\sin(\frac{\delta}{2}) & -i\cos(\frac{\gamma}{2})\sin(\frac{\delta}{2}) - \sin(\frac{\gamma}{2})\cos(\frac{\delta}{2}) \\\\
\sin(\frac{\gamma}{2})\cos(\frac{\delta}{2}) - i\cos(\frac{\gamma}{2})\sin(\frac{\delta}{2}) & -i\sin(\frac{\gamma}{2})\sin(\frac{\delta}{2}) + \cos(\frac{\gamma}{2})\cos(\frac{\delta}{2})
\end{pmatrix}
$$

Next, we pre-multiply this result by $R_x(\beta)$:

$$
R_x(\beta)[R_y(\gamma)R_x(\delta)] = \begin{pmatrix}
\cos(\beta/2) & -i\sin(\beta/2) \\\\
-i\sin(\beta/2) & \cos(\beta/2)
\end{pmatrix}
\begin{pmatrix}
\dots & \dots \\\\
\dots & \dots
\end{pmatrix}
$$

Performing this final multiplication and simplifying with trigonometric sum/difference identities yields the matrix for the special unitary part of the decomposition:

$$
R_x(\beta)R_y(\gamma)R_x(\delta) =
\begin{pmatrix}
\cos(\frac{\gamma}{2})\cos(\frac{\beta+\delta}{2}) + i\sin(\frac{\gamma}{2})\sin(\frac{\beta-\delta}{2}) & -\sin(\frac{\gamma}{2})\cos(\frac{\beta-\delta}{2}) -i\cos(\frac{\gamma}{2})\sin(\frac{\beta+\delta}{2}) \\\\
\sin(\frac{\gamma}{2})\cos(\frac{\beta-\delta}{2}) -i\cos(\frac{\gamma}{2})\sin(\frac{\beta+\delta}{2}) & \cos(\frac{\gamma}{2})\cos(\frac{\beta+\delta}{2}) -i\sin(\frac{\gamma}{2})\sin(\frac{\beta-\delta}{2})
\end{pmatrix}
$$

#### **Step 3: Apply the Global Phase**

The final step is to multiply by the global phase factor $e^{i\alpha}$. This phase simply multiplies every element in the matrix above.

### **The Final Decomposition**

The general form of a single-qubit unitary $U$ expressed as an **X-Y-X decomposition** is:

$$
U = e^{i\alpha}
\begin{pmatrix}
\cos(\frac{\gamma}{2})\cos(\frac{\beta+\delta}{2}) + i\sin(\frac{\gamma}{2})\sin(\frac{\beta-\delta}{2}) & -\sin(\frac{\gamma}{2})\cos(\frac{\beta-\delta}{2}) -i\cos(\frac{\gamma}{2})\sin(\frac{\beta+\delta}{2}) \\\\
\sin(\frac{\gamma}{2})\cos(\frac{\beta-\delta}{2}) -i\cos(\frac{\gamma}{2})\sin(\frac{\beta+\delta}{2}) & \cos(\frac{\gamma}{2})\cos(\frac{\beta+\delta}{2}) -i\sin(\frac{\gamma}{2})\sin(\frac{\beta-\delta}{2})
\end{pmatrix}
$$

This form is analogous to the Z-Y-Z decomposition. It looks more complicated because the $R_x$ matrix is not diagonal, leading to more complex combinations of real and imaginary terms in the final expression. However, it is an equally valid and universal representation for any single-qubit quantum gate. 🌀
This specific form for a single-qubit unitary matrix comes from a fundamental concept in physics and mathematics known as **Euler angle decomposition**. Just as any rotation in 3D space can be broken down into a sequence of three simpler rotations (e.g., around the Z, then Y, then Z axes again), any operation on a single qubit (which can be visualized as a rotation on the Bloch sphere) can be decomposed in the same way. The given matrix is the explicit result of such a decomposition.

***

### **Question 7: Explain why any single-qubit unitary may be written in the following form:**
$$U = \begin{pmatrix} e^{i(\alpha - \beta/2 - \delta/2)} \cos \gamma/2 & -e^{i(\alpha - \beta/2 + \delta/2)} \sin \gamma/2 \\ e^{i(\alpha + \beta/2 - \delta/2)} \sin \gamma/2 & e^{i(\alpha + \beta/2 + \delta/2)} \cos \gamma/2 \end{pmatrix}$$

---

### **Solution 1: The Constructive Proof (via Gate Decomposition)**

This explanation shows that a known, general decomposition of a unitary matrix results in the exact form given in the question. We will construct the matrix from its building blocks. It is a known theorem that any single-qubit unitary $U$ can be decomposed into the product of a global phase and three rotation matrices, a common choice being the **Z-Y-Z decomposition**:

$$U = e^{i\alpha} R_z(\beta) R_y(\gamma) R_z(\delta)$$

Let's prove this by performing the matrix multiplication.

#### **Step 1: Define the Rotation Matrices**

The required rotation matrices are:
$$
R_y(\gamma) = \begin{pmatrix}
\cos(\gamma/2) & -\sin(\gamma/2) \\\\
\sin(\gamma/2) & \cos(\gamma/2)
\end{pmatrix}
\quad , \quad
R_z(\theta) = \begin{pmatrix}
e^{-i\theta/2} & 0 \\\\
0 & e^{i\theta/2}
\end{pmatrix}
$$

#### **Step 2: Compute the Product of Rotations**

First, we compute the product $R_y(\gamma) R_z(\delta)$:
$$
R_y(\gamma) R_z(\delta) =
\begin{pmatrix}
\cos(\gamma/2) & -\sin(\gamma/2) \\\\
\sin(\gamma/2) & \cos(\gamma/2)
\end{pmatrix}
\begin{pmatrix}
e^{-i\delta/2} & 0 \\\\
0 & e^{i\delta/2}
\end{pmatrix}
=
\begin{pmatrix}
\cos(\gamma/2)e^{-i\delta/2} & -\sin(\gamma/2)e^{i\delta/2} \\\\
\sin(\gamma/2)e^{-i\delta/2} & \cos(\gamma/2)e^{i\delta/2}
\end{pmatrix}
$$

Next, we multiply this result by $R_z(\beta)$ from the left:
$$
R_z(\beta) [R_y(\gamma) R_z(\delta)] =
\begin{pmatrix}
e^{-i\beta/2} & 0 \\\\
0 & e^{i\beta/2}
\end{pmatrix}
\begin{pmatrix}
\cos(\gamma/2)e^{-i\delta/2} & -\sin(\gamma/2)e^{i\delta/2} \\\\
\sin(\gamma/2)e^{-i\delta/2} & \cos(\gamma/2)e^{i\delta/2}
\end{pmatrix}
$$
$$
=
\begin{pmatrix}
e^{-i\beta/2} \cos(\gamma/2)e^{-i\delta/2} & -e^{-i\beta/2} \sin(\gamma/2)e^{i\delta/2} \\\\
e^{i\beta/2} \sin(\gamma/2)e^{-i\delta/2} & e^{i\beta/2} \cos(\gamma/2)e^{i\delta/2}
\end{pmatrix}
$$

#### **Step 3: Apply the Global Phase**

Finally, we multiply the entire result by the global phase factor $e^{i\alpha}$ and combine the exponents:
$$
U = e^{i\alpha}
\begin{pmatrix}
e^{-i(\beta/2 + \delta/2)}\cos(\gamma/2) & -e^{-i(\beta/2 - \delta/2)}\sin(\gamma/2) \\\\
e^{i(\beta/2 - \delta/2)}\sin(\gamma/2) & e^{i(\beta/2 + \delta/2)}\cos(\gamma/2)
\end{pmatrix}
$$
$$
=
\begin{pmatrix}
e^{i(\alpha - \beta/2 - \delta/2)}\cos(\gamma/2) & -e^{i(\alpha - \beta/2 + \delta/2)}\sin(\gamma/2) \\\\
e^{i(\alpha + \beta/2 - \delta/2)}\sin(\gamma/2) & e^{i(\alpha + \beta/2 + \delta/2)}\cos(\gamma/2)
\end{pmatrix}
$$
This is exactly the form given in the question. Since it's known that any unitary can be decomposed into this product of rotations (a universal gate set), this form is completely general. ✨

---

### **Solution 2: The Analytic Proof (via Parameter Matching)**

This explanation shows that for any arbitrary single-qubit unitary $U$, we can always find the four real parameters $(\alpha, \beta, \gamma, \delta)$ that make the equation true. This confirms the generality of the form.

#### **Step 1: Equate a General Unitary to the Target Form**

Let an arbitrary single-qubit unitary be $U = \begin{pmatrix} u_{11} & u_{12} \\ u_{21} & u_{22} \end{pmatrix}$. We equate this to the given form.

#### **Step 2: Solve for the Parameters**

We can extract the parameters systematically.
1.  **Find $\gamma$ from magnitudes:** The magnitudes of the matrix elements give us:
    $|u_{11}| = |u_{22}| = |\cos(\gamma/2)|$
    $|u_{12}| = |u_{21}| = |\sin(\gamma/2)|$
    From unitarity, we know $|u_{11}|^2 + |u_{12}|^2 = 1$, which is consistent with $\cos^2(\gamma/2) + \sin^2(\gamma/2) = 1$. We can determine $\gamma$ unambiguously (within a certain range, e.g., $[0, \pi]$) from these relations, for example, using $\gamma = 2 \arccos(|u_{11}|)$.

2.  **Find $\beta$ and $\delta$ from phase differences:** Let's look at the phases (arguments) of the four matrix elements. Let $\phi_{jk} = \arg(u_{jk})$.
    * $\phi_{11} = \alpha - \beta/2 - \delta/2$
    * $\phi_{12} = \alpha - \beta/2 + \delta/2 + \pi$ (the minus sign adds $\pi$ to the phase)
    * $\phi_{21} = \alpha + \beta/2 - \delta/2$
    * $\phi_{22} = \alpha + \beta/2 + \delta/2$

    We can solve for $\beta$ and $\delta$ by taking differences of these phases to eliminate $\alpha$:
    * $\phi_{21} - \phi_{11} = (\alpha + \beta/2 - \delta/2) - (\alpha - \beta/2 - \delta/2) = \beta$
    * $\phi_{22} - \phi_{12} = (\alpha + \beta/2 + \delta/2) - (\alpha - \beta/2 + \delta/2 + \pi) = \beta - \pi$
    * $\phi_{12} - \phi_{11} = (\alpha - \beta/2 + \delta/2 + \pi) - (\alpha - \beta/2 - \delta/2) = \delta + \pi$
    * $\phi_{22} - \phi_{21} = (\alpha + \beta/2 + \delta/2) - (\alpha + \beta/2 - \delta/2) = \delta$

    So, we can find $\beta = \phi_{21} - \phi_{11}$ and $\delta = \phi_{22} - \phi_{21}$.

3.  **Find $\alpha$:** With $\beta, \gamma, \delta$ known, we can find $\alpha$ from any of the four phase equations. For example, using the last one:
    $\alpha = \phi_{22} - (\beta/2 + \delta/2)$

Since we have shown a procedure that can always find a valid set of real parameters $(\alpha, \beta, \gamma, \delta)$ for any given unitary $U$, the parametrization is completely general.
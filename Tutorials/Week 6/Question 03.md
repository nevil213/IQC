### **Question 3: Express the Hadamard gate H = $\frac{1}{\sqrt{2}} \begin{pmatrix} 1 & 1 \\ 1 & -1 \end{pmatrix}$ as a product of rotations using only Rx and Rz gates and a global phase $e^{i\phi}$ for some real $\phi$.**

Any single-qubit quantum gate (i.e., any $2 \times 2$ unitary matrix) can be decomposed into a sequence of rotations around fundamental axes. A common form for this is the Z-X-Z Euler angle decomposition, which states that any unitary gate $U$ can be written as:

$$U = e^{i\phi} R_z(\alpha) R_x(\beta) R_z(\gamma)$$

Our goal is to find the angles $\alpha, \beta, \gamma$ and the global phase $\phi$ that produce the Hadamard gate $H$.

---

### **Definitions**

First, let's define the matrices we'll be working with.

**Hadamard Gate (H):**

$$
H = \frac{1}{\sqrt{2}} \begin{pmatrix}
1 & 1 \\\\
1 & -1
\end{pmatrix}
$$

**Rotation about X-axis ($R_x$):**

$$
R_x(\theta) = \begin{pmatrix}
\cos(\theta/2) & -i\sin(\theta/2) \\\\
-i\sin(\theta/2) & \cos(\theta/2)
\end{pmatrix}
$$

**Rotation about Z-axis ($R_z$):**

$$
R_z(\theta) = \begin{pmatrix}
e^{-i\theta/2} & 0 \\\\
0 & e^{i\theta/2}
\end{pmatrix}
$$

---

## **Solution 1: A Standard Decomposition**

We'll solve for the parameters by first constructing the matrix for the rotation product and then equating it to the Hadamard gate.

### **Step 1: Construct the Rotation Product Matrix**

Let's compute the product $R_z(\alpha) R_x(\beta) R_z(\gamma)$. For simplicity, let $c_\beta = \cos(\beta/2)$ and $s_\beta = \sin(\beta/2)$.

First, $R_x(\beta) R_z(\gamma)$:

$$
\begin{pmatrix}
c_\beta & -is_\beta \\\\
-is_\beta & c_\beta
\end{pmatrix}
\begin{pmatrix}
e^{-i\gamma/2} & 0 \\\\
0 & e^{i\gamma/2}
\end{pmatrix}
=
\begin{pmatrix}
c_\beta e^{-i\gamma/2} & -is_\beta e^{i\gamma/2} \\\\
-is_\beta e^{-i\gamma/2} & c_\beta e^{i\gamma/2}
\end{pmatrix}
$$

Now, multiply by $R_z(\alpha)$ on the left:

$$
\begin{pmatrix}
e^{-i\alpha/2} & 0 \\\\
0 & e^{i\alpha/2}
\end{pmatrix}
\begin{pmatrix}
c_\beta e^{-i\gamma/2} & -is_\beta e^{i\gamma/2} \\\\
-is_\beta e^{-i\gamma/2} & c_\beta e^{i\gamma/2}
\end{pmatrix}
=
\begin{pmatrix}
c_\beta e^{-i(\alpha+\gamma)/2} & -is_\beta e^{-i(\alpha-\gamma)/2} \\\\
-is_\beta e^{i(\alpha-\gamma)/2} & c_\beta e^{i(\alpha+\gamma)/2}
\end{pmatrix}
$$

### **Step 2: Equate with the Hadamard Gate**

We need to solve the following equation:

$$
\begin{pmatrix}
c_\beta e^{-i(\alpha+\gamma)/2} & -is_\beta e^{-i(\alpha-\gamma)/2} \\\\
-is_\beta e^{i(\alpha-\gamma)/2} & c_\beta e^{i(\alpha+\gamma)/2}
\end{pmatrix}
=
e^{-i\phi} H = \frac{e^{-i\phi}}{\sqrt{2}}
\begin{pmatrix}
1 & 1 \\\\
1 & -1
\end{pmatrix}
$$

By comparing the magnitudes of the matrix elements:
* $|c_\beta| = |\cos(\beta/2)| = 1/\sqrt{2}$
* $|s_\beta| = |\sin(\beta/2)| = 1/\sqrt{2}$

A simple solution for this is $\beta/2 = \pi/4$, which gives $\beta = \pi/2$. This choice makes $c_\beta = s_\beta = 1/\sqrt{2}$.

Substituting these values in, we get:

$$
\frac{1}{\sqrt{2}}
\begin{pmatrix}
e^{-i(\alpha+\gamma)/2} & -i e^{-i(\alpha-\gamma)/2} \\\\
-i e^{i(\alpha-\gamma)/2} & e^{i(\alpha+\gamma)/2}
\end{pmatrix}
=
\frac{e^{-i\phi}}{\sqrt{2}}
\begin{pmatrix}
1 & 1 \\\\
1 & -1
\end{pmatrix}
$$

### **Step 3: Solve for Angles and Phase**

Now we compare the elements inside the matrices:
1.  **Top-right elements**: $-i e^{-i(\alpha-\gamma)/2} = e^{-i\phi}$
2.  **Bottom-left elements**: $-i e^{i(\alpha-\gamma)/2} = e^{-i\phi}$

From (1) and (2), we must have $e^{-i(\alpha-\gamma)/2} = e^{i(\alpha-\gamma)/2}$. This implies that the imaginary part is zero, so $\sin((\alpha-\gamma)/2) = 0$. The simplest solution is $(\alpha-\gamma)/2 = 0$, which means $\alpha = \gamma$.

Now the equations simplify. From (1), with $\alpha=\gamma$:
$$-i e^{0} = e^{-i\phi} \implies e^{-i\phi} = -i$$
This gives us the global phase. Taking the complex conjugate, $e^{i\phi} = i$, so one solution is $\phi = \pi/2$.

Next, let's use the diagonal elements.
3.  **Top-left elements**: $e^{-i(\alpha+\gamma)/2} = e^{-i\phi}$. Since $\alpha=\gamma$, this is $e^{-i\alpha} = e^{-i\phi}$.
4.  **Bottom-right elements**: $e^{i(\alpha+\gamma)/2} = -e^{-i\phi}$. Since $\alpha=\gamma$, this is $e^{i\alpha} = -e^{-i\phi}$.

Using $e^{-i\phi} = -i$ in equation (4):
$$e^{i\alpha} = -(-i) = i$$
A solution for this is $\alpha = \pi/2$. Since $\alpha=\gamma$, we also have $\gamma = \pi/2$. This is consistent with equation (3), as $e^{-i\pi/2} = -i$.

We have found a complete set of parameters:
* $\alpha = \pi/2$
* $\beta = \pi/2$
* $\gamma = \pi/2$
* $\phi = \pi/2$

The resulting decomposition is:

$$H = e^{i\pi/2} R_z(\pi/2) R_x(\pi/2) R_z(\pi/2)$$

---

## **Solution 2: An Alternative Decomposition**

We can find a different solution by making a different choice for $\beta$ back in Step 2.

### **Step 1: Revisit the Choice of $\beta$**

We had $|\cos(\beta/2)| = 1/\sqrt{2}$. Instead of $\beta/2 = \pi/4$, let's choose $\beta/2 = 3\pi/4$, which gives $\beta = 3\pi/2$.
This choice makes $c_\beta = \cos(3\pi/4) = -1/\sqrt{2}$ and $s_\beta = \sin(3\pi/4) = 1/\sqrt{2}$.

### **Step 2: Set up the New Matrix Equation**

Substituting these new values, our matrix equation becomes:

$$
\frac{1}{\sqrt{2}}
\begin{pmatrix}
-e^{-i(\alpha+\gamma)/2} & -i e^{-i(\alpha-\gamma)/2} \\\\
-i e^{i(\alpha-\gamma)/2} & -e^{i(\alpha+\gamma)/2}
\end{pmatrix}
=
\frac{e^{-i\phi}}{\sqrt{2}}
\begin{pmatrix}
1 & 1 \\\\
1 & -1
\end{pmatrix}
$$

### **Step 3: Solve for the New Parameters**

The off-diagonal elements are the same as before, which again leads us to conclude that $\alpha = \gamma$ and $e^{-i\phi} = -i$ (so $\phi = \pi/2$).

Now we look at the diagonal elements with these new conditions:
1.  **Top-left**: $-e^{-i(\alpha+\gamma)/2} = e^{-i\phi} \implies -e^{-i\alpha} = -i \implies e^{-i\alpha} = i$.
2.  **Bottom-right**: $-e^{i(\alpha+\gamma)/2} = -e^{-i\phi} \implies e^{i\alpha} = e^{-i\phi} \implies e^{i\alpha} = -i$.

From $e^{i\alpha} = -i$, a valid solution is $\alpha = -\pi/2$ (or $3\pi/2$). Since $\alpha=\gamma$, we also have $\gamma = -\pi/2$. This is consistent with the top-left equation, as $e^{-i(-\pi/2)} = e^{i\pi/2} = i$.

This gives us a second, distinct set of parameters:
* $\alpha = -\pi/2$
* $\beta = 3\pi/2$
* $\gamma = -\pi/2$
* $\phi = \pi/2$

The alternative decomposition is:

$$H = e^{i\pi/2} R_z(-\pi/2) R_x(3\pi/2) R_z(-\pi/2)$$
The Hadamard gate is both **unitary** and **Hermitian**, and it is its own inverse ($H^2 = I$). Its **eigenvalues** are $+1$ and $-1$, and its eigenvectors represent the axis of rotation for the Hadamard operation on the Bloch sphere.

-----

### **Q11. The Hadamard gate is given by $H = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 & 1 \\\\ 1 & -1 \end{pmatrix}$. Verify that $H^2 = I$ and that $H$ is unitary. Find the eigenvalues and eigenvectors of $H$.**

-----

## **Verifying $H^2 = I$ and Unitarity**

An operator $U$ is **unitary** if its conjugate transpose is its inverse, $U^\dagger U = I$. We can verify these properties for the Hadamard gate in two ways.

### **Solution 1.1: Direct Matrix Multiplication**

This method is a straightforward calculation.

**1. Verifying $H^2 = I$**
We multiply the Hadamard matrix by itself:

$$
H^2 = \left(\frac{1}{\sqrt{2}}\right)^2 \begin{pmatrix}
1 & 1 \\\\
1 & -1
\end{pmatrix} \begin{pmatrix}
1 & 1 \\\\
1 & -1
\end{pmatrix} = \frac{1}{2} \begin{pmatrix}
1\cdot1 + 1\cdot1 & 1\cdot1 + 1\cdot(-1) \\\\
1\cdot1 + (-1)\cdot1 & 1\cdot1 + (-1)\cdot(-1)
\end{pmatrix}
$$
= \frac{1}{2} \begin{pmatrix}
2 & 0 \\\\
0 & 2
\end{pmatrix} = \begin{pmatrix}
1 & 0 \\\\
0 & 1
\end{pmatrix} = I
This shows that $H$ is its own inverse, $H^{-1} = H$.

**2. Verifying Unitarity**
We first find the conjugate transpose, $H^\dagger$. Since all elements of $H$ are real, the conjugate does nothing. Since the matrix is symmetric, the transpose does nothing. Therefore, $H$ is Hermitian:
$$H^\dagger = H$$
Now we check the condition for unitarity:
$$H^\dagger H = H \cdot H = H^2$$
From our previous result, we know $H^2 = I$. Thus, $H^\dagger H = I$, and the Hadamard gate is unitary. ✅

### **Solution 1.2: Action on Basis States**

This method confirms the properties by observing the gate's effect.

The Hadamard gate maps the computational basis states to the Hadamard basis states:

* $H|0\rangle = \frac{1}{\sqrt{2}}(|0\rangle + |1\rangle) = |+\rangle$
* $H|1\rangle = \frac{1}{\sqrt{2}}(|0\rangle - |1\rangle) = |-\rangle$

Applying the gate a second time:

* $H^2|0\rangle = H|+\rangle = H\left(\frac{1}{\sqrt{2}}(|0\rangle+|1\rangle)\right) = \frac{1}{\sqrt{2}}(H|0\rangle+H|1\rangle) = \frac{1}{2}(|0\rangle+|1\rangle+|0\rangle-|1\rangle) = |0\rangle$
* $H^2|1\rangle = H|-\rangle = H\left(\frac{1}{\sqrt{2}}(|0\rangle-|1\rangle)\right) = \frac{1}{\sqrt{2}}(H|0\rangle-H|1\rangle) = \frac{1}{2}(|0\rangle+|1\rangle-|0\rangle+|1\rangle) = |1\rangle$

Since applying $H^2$ leaves the basis states unchanged, it must be the identity operator. Furthermore, since $H$ maps one orthonormal basis ($\{|0\rangle, |1\rangle\}$) to another orthonormal basis ($\{|+\rangle, |-\rangle\}$), it is, by definition, a unitary transformation.

-----

## **Finding Eigenvalues and Eigenvectors**

We need to solve the eigenvalue equation $H|\psi\rangle = \lambda|\psi\rangle$.

### **Step 1: Finding Eigenvalues**

The eigenvalues $\lambda$ are the roots of the characteristic equation $\det(H - \lambda I) = 0$.
$$\det\begin{pmatrix} \frac{1}{\sqrt{2}}-\lambda & \frac{1}{\sqrt{2}} \\\\ \frac{1}{\sqrt{2}} & -\frac{1}{\sqrt{2}}-\lambda \end{pmatrix} = 0$$
$$\left(\frac{1}{\sqrt{2}}-\lambda\right)\left(-\frac{1}{\sqrt{2}}-\lambda\right) - \left(\frac{1}{\sqrt{2}}\right)\left(\frac{1}{\sqrt{2}}\right) = 0$$
$$-\left(\frac{1}{2} - \lambda^2\right) - \frac{1}{2} = 0 \implies \lambda^2 - 1 = 0$$
The eigenvalues are $\lambda_1 = +1$ and $\lambda_2 = -1$.

### **Step 2: Finding Eigenvectors**

We now find the eigenvector for each eigenvalue.

* **For $\lambda = +1$**: We solve $H|\psi\rangle = |\psi\rangle$. Let $|\psi_1\rangle = \begin{pmatrix} a \\\\ b \end{pmatrix}$.
$$
\frac{1}{\sqrt{2}}\begin{pmatrix} 1 & 1 \\\\ 1 & -1 \end{pmatrix} \begin{pmatrix} a \\\\ b \end{pmatrix} = \begin{pmatrix} a \\\\ b \end{pmatrix} \implies a+b = \sqrt{2}a
$$
This gives the condition $b = (\sqrt{2}-1)a$. The unnormalized eigenvector is $\begin{pmatrix} 1 \\\\ \sqrt{2}-1 \end{pmatrix}$. Normalizing this vector gives the eigenvector for $\lambda=1$:
$$
|\psi_1\rangle = \frac{1}{\sqrt{4-2\sqrt{2}}} \begin{pmatrix} 1 \\\\ \sqrt{2}-1 \end{pmatrix} \approx 0.92|0\rangle + 0.38|1\rangle
$$

* **For $\lambda = -1$**: We solve $H|\psi\rangle = -|\psi\rangle$. Let $|\psi_2\rangle = \begin{pmatrix} a \\\\ b \end{pmatrix}$.
$$
\frac{1}{\sqrt{2}}\begin{pmatrix} 1 & 1 \\\\ 1 & -1 \end{pmatrix} \begin{pmatrix} a \\\\ b \end{pmatrix} = -\begin{pmatrix} a \\\\ b \end{pmatrix} \implies a+b = -\sqrt{2}a
$$
This gives the condition $b = -(\sqrt{2}+1)a$. The unnormalized eigenvector is $\begin{pmatrix} 1 \\\\ -(\sqrt{2}+1) \end{pmatrix}$. Normalizing gives the eigenvector for $\lambda=-1$:
$$
|\psi_2\rangle = \frac{1}{\sqrt{4+2\sqrt{2}}} \begin{pmatrix} 1 \\\\ -(\sqrt{2}+1) \end{pmatrix} \approx 0.38|0\rangle - 0.92|1\rangle
$$
Geometrically, these eigenvectors represent the axis on the Bloch sphere (an axis lying in the x-z plane) about which the Hadamard gate performs a rotation of $\pi$ radians.
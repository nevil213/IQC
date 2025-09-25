Any single-qubit unitary operation can be represented as a rotation on the Bloch sphere, possibly with an overall global phase. The operator $R_{\hat{n}}(\theta)$ represents a rotation by angle $\theta$ around the axis $\hat{n}$, and $e^{i\alpha}$ is a global phase factor.

### **Question 6: Show that any single-qubit unitary can be written as $U = e^{i\alpha} R_{\hat{n}}(\theta)$ for some real numbers $\alpha, \theta$ and a real unit vector $\hat{n}$. Then: (a) Find $(\alpha,\theta, \hat{n})$ that realize the Hadamard gate H. (b) Find $(\alpha,\theta, \hat{n})$ that realize the phase gate S.**

***

### **Part 1: The General Proof**

A general single-qubit unitary matrix $U$ is an element of the group $U(2)$. The rotation operator $R_{\hat{n}}(\theta) = \exp(-i\frac{\theta}{2}\hat{n}\cdot\vec{\sigma})$ has a determinant of 1, making it an element of the special unitary group $SU(2)$.

Any matrix $U \in U(2)$ can be written as a product of a phase factor and a matrix $U' \in SU(2)$. Let $\det(U) = d$. We can write:

$$U = (\sqrt[2]{d}) \cdot \frac{U}{\sqrt[2]{d}}$$

Let $e^{i\alpha} = \sqrt[2]{d}$ and $U' = U/\sqrt[2]{d}$. The determinant of $U'$ is $\det(U') = \det(U)/(\sqrt[2]{d})^2 = d/d = 1$, so $U' \in SU(2)$.

The task is now to show that any special unitary matrix $U'$ can be written as $R_{\hat{n}}(\theta)$. The general form of $R_{\hat{n}}(\theta)$ is:

$$
R_{\hat{n}}(\theta) = \cos(\theta/2)I - i\sin(\theta/2)(\hat{n}\cdot\vec{\sigma}) = \begin{pmatrix}
\cos(\theta/2) - in_z\sin(\theta/2) & (-in_x-n_y)\sin(\theta/2) \\\\
(-in_x+n_y)\sin(\theta/2) & \cos(\theta/2) + in_z\sin(\theta/2)
\end{pmatrix}
$$

Any matrix $U' \in SU(2)$ can be written as $\begin{pmatrix} a & b \\ -b^* & a^* \end{pmatrix}$ where $|a|^2+|b|^2=1$. We can always find a set of real numbers $(\theta, n_x, n_y, n_z)$ that satisfies this form. By equating the corresponding matrix elements, we set $\cos(\theta/2) = \text{Re}(a)$, which defines $\theta$. The remaining elements can then be used to solve for the components of $\hat{n}$:

* $n_z = -\text{Im}(a)/\sin(\theta/2)$
* $n_y = -\text{Re}(b)/\sin(\theta/2)$
* $n_x = \text{Im}(b)/\sin(\theta/2)$

It can be verified that the condition $|a|^2+|b|^2=1$ ensures that the resulting vector $\hat{n}$ is a unit vector ($n_x^2+n_y^2+n_z^2=1$). Thus, any $U$ can be decomposed into the desired form.

***

### **Part 2(a): Decomposition of the Hadamard Gate**

The Hadamard gate is:

$$
H = \frac{1}{\sqrt{2}} \begin{pmatrix}
1 & 1 \\\\
1 & -1
\end{pmatrix}
$$

**1. Find the Global Phase ($\alpha$)**
First, we calculate the determinant: $\det(H) = \frac{1}{2}((1)(-1)-(1)(1)) = -1$.
We set $\det(H) = e^{i2\alpha}$.

$$e^{i2\alpha} = -1 = e^{i\pi} \implies 2\alpha = \pi \implies \alpha = \pi/2$$

**2. Find the Rotation Parameters ($\theta$, $\hat{n}$)**
We now find the corresponding special unitary part, $U' = e^{-i\alpha}H$:

$$
U' = e^{-i\pi/2}H = (-i) \frac{1}{\sqrt{2}} \begin{pmatrix}
1 & 1 \\\\
1 & -1
\end{pmatrix} = \frac{-i}{\sqrt{2}} \begin{pmatrix}
1 & 1 \\\\
1 & -1
\end{pmatrix}
$$

We equate the trace of $U'$ with the trace of $R_{\hat{n}}(\theta)$, which is $2\cos(\theta/2)$:

$$\text{Tr}(U') = \frac{-i}{\sqrt{2}}(1 - 1) = 0$$

$$2\cos(\theta/2) = 0 \implies \cos(\theta/2) = 0 \implies \theta/2 = \pi/2 \implies \theta = \pi$$

For $\theta=\pi$, the rotation operator simplifies to $R_{\hat{n}}(\pi) = -i(\hat{n}\cdot\vec{\sigma})$. We can now solve for $\hat{n}$:

$$
U' = -i(\hat{n}\cdot\vec{\sigma}) = -i \begin{pmatrix}
n_z & n_x - in_y \\\\
n_x + in_y & -n_z
\end{pmatrix} = \frac{-i}{\sqrt{2}} \begin{pmatrix}
1 & 1 \\\\
1 & -1
\end{pmatrix}
$$

Canceling the factor of $-i$ and comparing elements, we find:
* $n_z = 1/\sqrt{2}$
* $n_x - in_y = 1/\sqrt{2} \implies n_x=1/\sqrt{2}, n_y=0$.

The rotation axis is $\hat{n} = (1/\sqrt{2}, 0, 1/\sqrt{2})$.

**Result for H:**
* $\alpha = \pi/2$
* $\theta = \pi$
* $\hat{n} = \frac{1}{\sqrt{2}}(\hat{x} + \hat{z})$

So, $H = e^{i\pi/2} R_{\hat{n}}(\pi)$ where $\hat{n}$ is the vector pointing halfway between the X and Z axes.

***

### **Part 2(b): Decomposition of the Phase Gate**

The Phase gate is:

$$
S = \begin{pmatrix}
1 & 0 \\\\
0 & i
\end{pmatrix}
$$

**1. Find the Global Phase ($\alpha$)**
First, the determinant: $\det(S) = (1)(i) = i$.
We set $\det(S) = e^{i2\alpha}$.

$$e^{i2\alpha} = i = e^{i\pi/2} \implies 2\alpha = \pi/2 \implies \alpha = \pi/4$$

**2. Find the Rotation Parameters ($\theta$, $\hat{n}$)**
The corresponding special unitary part is $U' = e^{-i\alpha}S$:

$$
U' = e^{-i\pi/4}S = \begin{pmatrix}
e^{-i\pi/4} & 0 \\\\
0 & i e^{-i\pi/4}
\end{pmatrix} = \begin{pmatrix}
e^{-i\pi/4} & 0 \\\\
0 & e^{i\pi/4}
\end{pmatrix}
$$

This is the standard matrix for a rotation about the Z-axis, $R_z(\theta)$.
We have $R_z(\theta) = \begin{pmatrix} e^{-i\theta/2} & 0 \\ 0 & e^{i\theta/2} \end{pmatrix}$.
By comparing the elements, we see:

$$\theta/2 = \pi/4 \implies \theta = \pi/2$$

The rotation axis is the Z-axis, $\hat{n} = (0, 0, 1)$.

**Result for S:**
* $\alpha = \pi/4$
* $\theta = \pi/2$
* $\hat{n} = \hat{z}$

So, $S = e^{i\pi/4} R_z(\pi/2)$. This represents a quarter-turn rotation around the Z-axis of the Bloch sphere with a global phase of $\pi/4$. 💖
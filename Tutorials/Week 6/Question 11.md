To show that the set $\{I, X, Y, Z\}$ is a basis for a vector space, we must prove two fundamental properties: that the set is **linearly independent** and that it **spans** the entire space. The vector space in question is the set of all $2 \times 2$ Hermitian matrices, with the scalars being real numbers.

A $2 \times 2$ matrix $M$ is **Hermitian** if it equals its own conjugate transpose ($M = M^\dagger$). A general Hermitian matrix can be written using four real parameters, for example, $a, b, c, d \in \mathbb{R}$:

$$
M = \begin{pmatrix}
a & b-ic \\\\
b+ic & d
\end{pmatrix}
$$

This shows that the vector space of $2 \times 2$ Hermitian matrices is **4-dimensional**. Since our set $\{I, X, Y, Z\}$ contains four matrices, we only need to prove either linear independence or spanning—the other property will follow automatically. However, for completeness, we will demonstrate both.

***

### **Question 11: Show that the set {I, X, Y, Z} is a basis for the vector space of 2×2 Hermitian matrices.**

First, note that the identity matrix $I$ and the Pauli matrices $X, Y, Z$ are all themselves Hermitian, so they belong to the vector space.

$$I = \begin{pmatrix} 1 & 0 \\\\ 0 & 1 \end{pmatrix} \quad X = \begin{pmatrix} 0 & 1 \\\\ 1 & 0 \end{pmatrix} \quad Y = \begin{pmatrix} 0 & -i \\\\ i & 0 \end{pmatrix} \quad Z = \begin{pmatrix} 1 & 0 \\\\ 0 & -1 \end{pmatrix}$$

---

### **Solution 1: Direct Algebraic Proof**

This method directly demonstrates both the spanning and linear independence properties by solving a system of linear equations.

#### **1. Spanning Proof**
We must show that any arbitrary Hermitian matrix $M$ can be written as a linear combination of our basis matrices with **real** coefficients $c_0, c_1, c_2, c_3$.

$$M = c_0 I + c_1 X + c_2 Y + c_3 Z$$

Let's write out the right-hand side explicitly:
$$c_0 \begin{pmatrix} 1 & 0 \\\\ 0 & 1 \end{pmatrix} + c_1 \begin{pmatrix} 0 & 1 \\\\ 1 & 0 \end{pmatrix} + c_2 \begin{pmatrix} 0 & -i \\\\ i & 0 \end{pmatrix} + c_3 \begin{pmatrix} 1 & 0 \\\\ 0 & -1 \end{pmatrix} = \begin{pmatrix} c_0+c_3 & c_1-ic_2 \\\\ c_1+ic_2 & c_0-c_3 \end{pmatrix}$$

Now, we equate this with our general Hermitian matrix $M = \begin{pmatrix} a & b-ic \\ b+ic & d \end{pmatrix}$:
$$\begin{pmatrix} c_0+c_3 & c_1-ic_2 \\\\ c_1+ic_2 & c_0-c_3 \end{pmatrix} = \begin{pmatrix} a & b-ic \\\\ b+ic & d \end{pmatrix}$$
This gives us a system of equations by comparing the elements:
* $c_0 + c_3 = a$
* $c_0 - c_3 = d$
* $c_1 - ic_2 = b - ic \implies c_1 = b, \quad c_2 = c$

From the first two equations, we can solve for $c_0$ and $c_3$:
* Adding them gives $2c_0 = a+d \implies c_0 = (a+d)/2$.
* Subtracting them gives $2c_3 = a-d \implies c_3 = (a-d)/2$.

Since we found a unique set of real coefficients $(c_0, c_1, c_2, c_3)$ for any given real parameters $(a, b, c, d)$, the set $\{I, X, Y, Z\}$ spans the entire space of $2 \times 2$ Hermitian matrices.

#### **2. Linear Independence Proof**
We must show that the only way to form the zero matrix is by setting all coefficients to zero.
$$c_0 I + c_1 X + c_2 Y + c_3 Z = \mathbf{0} = \begin{pmatrix} 0 & 0 \\\\ 0 & 0 \end{pmatrix}$$This corresponds to setting $a=b=c=d=0$ in the equations above, which immediately gives:$$c_0 = 0, \quad c_1 = 0, \quad c_2 = 0, \quad c_3 = 0$$
Since this is the only solution, the set is linearly independent. Because the set is linearly independent and spans the space, it is a basis. ✅

---

### **Solution 2: Proof using Orthogonality**

This is a more elegant method that uses the concept of an inner product space. The set of matrices forms a vector space, and we can define an inner product on it.

#### **1. Define an Inner Product**
A standard inner product for matrices is the **Hilbert-Schmidt inner product**, defined as $\langle A, B \rangle \equiv \frac{1}{2}\text{Tr}(A^\dagger B)$. Since our matrices are Hermitian ($A^\dagger = A$), this simplifies to:
$$\langle A, B \rangle = \frac{1}{2}\text{Tr}(AB)$$
Two matrices are "orthogonal" if their inner product is zero.

#### **2. Show Orthogonality**
We will show that the set $\{I, X, Y, Z\}$ is an orthogonal set.
* **Pauli matrices are traceless:** $\text{Tr}(X)=\text{Tr}(Y)=\text{Tr}(Z)=0$.
* **Orthogonality with the Identity:**
    $\langle I, X \rangle = \frac{1}{2}\text{Tr}(IX) = \frac{1}{2}\text{Tr}(X) = 0$. Similarly, $I$ is orthogonal to $Y$ and $Z$.
* **Orthogonality between Pauli Matrices:** The Pauli matrices anti-commute ($XY = -YX$). Using this and the cyclic property of the trace ($\text{Tr}(AB)=\text{Tr}(BA)$):
    $\text{Tr}(XY) = \text{Tr}(-YX) = -\text{Tr}(YX) = -\text{Tr}(XY)$.
    The only number equal to its own negative is zero, so $\text{Tr}(XY)=0$. This holds for any distinct pair of Pauli matrices. Therefore, $\langle X, Y \rangle = \langle X, Z \rangle = \langle Y, Z \rangle = 0$.

#### **3. Orthogonality Implies Linear Independence**
An orthogonal set of non-zero vectors is always linearly independent. To see this, assume a linear combination equals zero:
$$c_0 I + c_1 X + c_2 Y + c_3 Z = \mathbf{0}$$If we take the inner product of the whole equation with $I$:$$\langle I, c_0 I + c_1 X + c_2 Y + c_3 Z \rangle = c_0\langle I,I \rangle + c_1\langle I,X \rangle + c_2\langle I,Y \rangle + c_3\langle I,Z \rangle = 0$$
Due to orthogonality, all terms except the first are zero. Since $\langle I,I \rangle = \frac{1}{2}\text{Tr}(I) = 1 \neq 0$, we must have $c_0=0$. Similarly, taking the inner product with $X, Y,$ and $Z$ in turn shows that $c_1, c_2,$ and $c_3$ must also be zero.

Since we have a set of 4 linearly independent vectors in a 4-dimensional vector space, this set must be a basis. 🎓
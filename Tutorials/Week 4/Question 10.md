To express the states in a basis where their components don't just differ by a phase, we need to find a basis where the **magnitudes** of their corresponding components are different. The simplest way to achieve this is to choose the basis to be the states themselves.

***

### **Question 10: Express the states $\frac{|0\rangle + |1\rangle}{\sqrt{2}}$ and $\frac{|0\rangle - |1\rangle}{\sqrt{2}}$ in a basis in which they are not the same up to a relative phase shift.**

The two states are the Hadamard basis states, commonly known as $|+\rangle$ and $|-\rangle$.

$$|+\rangle = \frac{|0\rangle + |1\rangle}{\sqrt{2}} \quad , \quad |-\rangle = \frac{|0\rangle - |1\rangle}{\sqrt{2}}$$

In the standard **computational basis** $\{|0\rangle, |1\rangle\}$, their vector representations are:

$$|+\rangle = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\\\ 1 \end{pmatrix} \quad , \quad |-\rangle = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\\\ -1 \end{pmatrix}$$

The magnitudes of the components for $|+\rangle$ are $(1/\sqrt{2}, 1/\sqrt{2})$, and for $|-\rangle$ they are $(1/\sqrt{2}, |-1|/\sqrt{2}) = (1/\sqrt{2}, 1/\sqrt{2})$. Since the corresponding magnitudes are identical, they are the same up to a relative phase in this basis. We need a different basis.

---

### **Solution 1: Using the Hadamard Basis**

The most straightforward solution is to use the Hadamard basis, $\{|+\rangle, |-\rangle\}$, as our new basis. This is a valid orthonormal basis.

**1. Expressing the States**
To express a state in a new basis, we find its components along the new basis vectors.
* **For the state $|+\rangle$**: We want to write it as $|\psi\rangle = c_1|+\rangle + c_2|-\rangle$.
    * The first component is $c_1 = \langle+|+\rangle = 1$.
    * The second component is $c_2 = \langle-|+\rangle = 0$.
    So, the state $|+\rangle$ is simply $1 \cdot |+\rangle + 0 \cdot |-\rangle$.

* **For the state $|-\rangle$**: We want to write it as $|\phi\rangle = d_1|+\rangle + d_2|-\rangle$.
    * The first component is $d_1 = \langle+|-\rangle = 0$.
    * The second component is $d_2 = \langle-|-\rangle = 1$.
    So, the state $|-\rangle$ is simply $0 \cdot |+\rangle + 1 \cdot |-\rangle$.

**2. Vector Representation and Comparison**
In the Hadamard basis, the vector representations are:
$$|+\rangle_H = \begin{pmatrix} 1 \\\\ 0 \end{pmatrix} \quad , \quad |-\rangle_H = \begin{pmatrix} 0 \\\\ 1 \end{pmatrix}$$

Now we compare the magnitudes of the components:
* For $|+\rangle_H$: The component magnitudes are $(|1|, |0|) = (1, 0)$.
* For $|-\rangle_H$: The component magnitudes are $(|0|, |1|) = (0, 1)$.

Since the set of magnitudes $(1, 0)$ is different from $(0, 1)$, the states are not the same up to a relative phase shift in this basis.

---

### **Solution 2: Using a Rotated Basis**

We can choose any other orthonormal basis that is not aligned with the computational or Hadamard axes. For example, let's create a basis $\{|b_1\rangle, |b_2\rangle\}$ by rotating the computational basis by an angle of $\theta = \pi/4$ around the Y-axis.

**1. Defining the New Basis**
* $|b_1\rangle = R_y(\pi/4)|0\rangle = \cos(\pi/8)|0\rangle + \sin(\pi/8)|1\rangle$
* $|b_2\rangle = R_y(\pi/4)|1\rangle = -\sin(\pi/8)|0\rangle + \cos(\pi/8)|1\rangle$

**2. Expressing the States**
We find the new components by projecting $|+\rangle$ and $|-\rangle$ onto the new basis vectors.
* **For the state $|+\rangle$**:
    * $c_1 = \langle b_1|+\rangle = \frac{1}{\sqrt{2}}(\cos(\pi/8) + \sin(\pi/8))$
    * $c_2 = \langle b_2|+\rangle = \frac{1}{\sqrt{2}}(\cos(\pi/8) - \sin(\pi/8))$
    The vector is $|+\rangle_b = \frac{1}{\sqrt{2}}\begin{pmatrix} \cos(\pi/8) + \sin(\pi/8) \\\\ \cos(\pi/8) - \sin(\pi/8) \end{pmatrix}$.

* **For the state $|-\rangle$**:
    * $d_1 = \langle b_1|-\rangle = \frac{1}{\sqrt{2}}(\cos(\pi/8) - \sin(\pi/8))$
    * $d_2 = \langle b_2|-\rangle = -\frac{1}{\sqrt{2}}(\cos(\pi/8) + \sin(\pi/8))$
    The vector is $|-\rangle_b = \frac{1}{\sqrt{2}}\begin{pmatrix} \cos(\pi/8) - \sin(\pi/8) \\\\ -(\cos(\pi/8) + \sin(\pi/8)) \end{pmatrix}$.

**3. Comparison**
Let's compare the magnitudes of the first components, $|c_1|$ and $|d_1|$.
* $|c_1| = \frac{1}{\sqrt{2}}(\cos(\pi/8) + \sin(\pi/8))$
* $|d_1| = \frac{1}{\sqrt{2}}(\cos(\pi/8) - \sin(\pi/8))$

Since $\cos(\pi/8) \neq 0$ and $\sin(\pi/8) \neq 0$, it is clear that $|c_1| \neq |d_1|$. Because the magnitudes of their corresponding components are different, the states are not the same up to a relative phase shift in this basis either. 🎨
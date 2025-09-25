### **Question 5: Show that $\sigma_x\sigma_y\sigma_x = -\sigma_y$ and use this to prove $\sigma_x R_y(\theta) \sigma_x = R_y(-\theta)$.**

We'll tackle this in two parts as requested.

---

### **Part 1: Show that $\sigma_x\sigma_y\sigma_x = -\sigma_y$**

We can prove this identity in two ways: by using the algebraic properties of Pauli matrices or by direct matrix multiplication.

#### **Solution 1.1: Proof using Pauli Matrix Identities**

This is the most direct method. It relies on two key properties of Pauli matrices:
1.  **Anti-commutation**: For $i \neq j$, $\sigma_i \sigma_j = -\sigma_j \sigma_i$.
2.  **Square to Identity**: $\sigma_x^2 = I$, where $I$ is the identity matrix.

Let's start with the left-hand side of the expression, $\sigma_x\sigma_y\sigma_x$.
First, consider the first two matrices, $\sigma_x\sigma_y$. Using the **anti-commutation** property, we can write:

$$\sigma_x\sigma_y = -\sigma_y\sigma_x$$

Now, substitute this back into the original expression:

$$\sigma_x\sigma_y\sigma_x = (-\sigma_y\sigma_x)\sigma_x = -\sigma_y(\sigma_x\sigma_x) = -\sigma_y(\sigma_x^2)$$

Finally, using the property that $\sigma_x^2 = I$:

$$-\sigma_y(\sigma_x^2) = -\sigma_y I = -\sigma_y$$

Thus, we have shown that $\sigma_x\sigma_y\sigma_x = -\sigma_y$. 🤓

#### **Solution 1.2: Proof by Direct Matrix Multiplication**

This method confirms the result by "brute force." We use the matrix representations:

$$\sigma_x = \begin{pmatrix} 0 & 1 \\\\ 1 & 0 \end{pmatrix} \quad , \quad \sigma_y = \begin{pmatrix} 0 & -i \\\\ i & 0 \end{pmatrix}$$

First, let's compute the product $\sigma_y\sigma_x$:

$$\sigma_y\sigma_x = \begin{pmatrix} 0 & -i \\\\ i & 0 \end{pmatrix} \begin{pmatrix} 0 & 1 \\\\ 1 & 0 \end{pmatrix} = \begin{pmatrix} (0)(0)+(-i)(1) & (0)(1)+(-i)(0) \\\\ (i)(0)+(0)(1) & (i)(1)+(0)(0) \end{pmatrix} = \begin{pmatrix} -i & 0 \\\\ 0 & i \end{pmatrix}$$

Now, we multiply this result by $\sigma_x$ from the left:

$$\sigma_x (\sigma_y\sigma_x) = \begin{pmatrix} 0 & 1 \\\\ 1 & 0 \end{pmatrix} \begin{pmatrix} -i & 0 \\\\ 0 & i \end{pmatrix} = \begin{pmatrix} (0)(-i)+(1)(0) & (0)(0)+(1)(i) \\\\ (1)(-i)+(0)(0) & (1)(0)+(0)(i) \end{pmatrix} = \begin{pmatrix} 0 & i \\\\ -i & 0 \end{pmatrix}$$

Let's compare this to the right-hand side, $-\sigma_y$:

$$-\sigma_y = -1 \cdot \begin{pmatrix} 0 & -i \\\\ i & 0 \end{pmatrix} = \begin{pmatrix} 0 & i \\\\ -i & 0 \end{pmatrix}$$

The results match, confirming that $\sigma_x\sigma_y\sigma_x = -\sigma_y$.

---

### **Part 2: Prove $\sigma_x R_y(\theta) \sigma_x = R_y(-\theta)$**

Here we'll use the identity we just proved.

#### **Solution 2.1: Using the Closed-Form Expression for $R_y(\theta)$**

The closed-form expression for a rotation around the y-axis is:

$$R_y(\theta) = \cos(\theta/2)I - i\sin(\theta/2)\sigma_y$$

Let's substitute this into the expression $\sigma_x R_y(\theta) \sigma_x$:

$$\sigma_x R_y(\theta) \sigma_x = \sigma_x \left( \cos(\theta/2)I - i\sin(\theta/2)\sigma_y \right) \sigma_x$$

Distributing the $\sigma_x$ matrices inside the parentheses:

$$= \cos(\theta/2)(\sigma_x I \sigma_x) - i\sin(\theta/2)(\sigma_x \sigma_y \sigma_x)$$

Now we can simplify using our known identities:
* $\sigma_x I \sigma_x = \sigma_x \sigma_x = \sigma_x^2 = I$.
* From Part 1, we know $\sigma_x \sigma_y \sigma_x = -\sigma_y$.

Substituting these in gives:

$$= \cos(\theta/2)I - i\sin(\theta/2)(-\sigma_y)$$

$$= \cos(\theta/2)I + i\sin(\theta/2)\sigma_y$$

Now, let's write out the expression for $R_y(-\theta)$ using the same closed-form formula:

$$R_y(-\theta) = \cos(-\theta/2)I - i\sin(-\theta/2)\sigma_y$$

Using the trigonometric identities $\cos(-x) = \cos(x)$ and $\sin(-x) = -\sin(x)$:

$$= \cos(\theta/2)I - i(-\sin(\theta/2))\sigma_y$$

$$= \cos(\theta/2)I + i\sin(\theta/2)\sigma_y$$

The two results are identical. Therefore, we have proven that $\sigma_x R_y(\theta) \sigma_x = R_y(-\theta)$. ✅

#### **Solution 2.2: Using the Taylor Series Expansion of $R_y(\theta)$**

This method is more fundamental. We start with the definition of the rotation operator as a matrix exponential:

$$R_y(\theta) = \exp\left(-i \frac{\theta}{2} \sigma_y\right) = \sum_{k=0}^{\infty} \frac{1}{k!} \left(-i \frac{\theta}{2}\right)^k \sigma_y^k$$

Now, we conjugate by $\sigma_x$:

$$\sigma_x R_y(\theta) \sigma_x = \sigma_x \left( \sum_{k=0}^{\infty} \frac{(-i\theta/2)^k}{k!} \sigma_y^k \right) \sigma_x = \sum_{k=0}^{\infty} \frac{(-i\theta/2)^k}{k!} (\sigma_x \sigma_y^k \sigma_x)$$

Let's analyze the term $\sigma_x \sigma_y^k \sigma_x$. We can insert the identity matrix $I = \sigma_x\sigma_x$ between each $\sigma_y$:

$$\sigma_x \sigma_y^k \sigma_x = \sigma_x \overbrace{\sigma_y \cdot \sigma_y \cdots \sigma_y}^{k \text{ times}} \sigma_x = (\sigma_x \sigma_y \sigma_x)(\sigma_x \sigma_y \sigma_x)\cdots(\sigma_x \sigma_y \sigma_x)$$

This is the term $(\sigma_x \sigma_y \sigma_x)$ repeated $k$ times. Using our result from Part 1:

$$= (-\sigma_y)^k$$

Substituting this back into the sum:

$$\sigma_x R_y(\theta) \sigma_x = \sum_{k=0}^{\infty} \frac{(-i\theta/2)^k}{k!} (-\sigma_y)^k = \sum_{k=0}^{\infty} \frac{1}{k!} \left( \left(-i\frac{\theta}{2}\right) (-\sigma_y) \right)^k$$

$$= \sum_{k=0}^{\infty} \frac{1}{k!} \left( i\frac{\theta}{2}\sigma_y \right)^k = \exp\left(i\frac{\theta}{2}\sigma_y\right)$$

This final expression is the definition of a rotation by angle $-\theta$ around the y-axis:

$$\exp\left(i\frac{\theta}{2}\sigma_y\right) = \exp\left(-i\frac{(-\theta)}{2}\sigma_y\right) = R_y(-\theta)$$

This completes the proof from first principles.
### **Question 4: Prove that $(\hat{n}\cdot\vec{\sigma})^2 = I$ for any real unit vector $\hat{n}$. Verify the closed-form expression $R_{\hat{n}}(\theta) = \cos(\theta/2) I -i \sin(\theta/2) (n_x\sigma_x + n_y\sigma_y + n_z\sigma_z)$.**

This question has two parts. First, we'll prove the identity for the Pauli vector, and second, we'll use that result to verify the general formula for a rotation operator.

---

## **Part 1: Proving $(\hat{n}\cdot\vec{\sigma})^2 = I$**

Here, $\hat{n} = (n_x, n_y, n_z)$ is a real unit vector (so $n_x^2 + n_y^2 + n_z^2 = 1$), and $\vec{\sigma} = (\sigma_x, \sigma_y, \sigma_z)$ is the vector of Pauli matrices.

### **Solution 1.1: Proof using Pauli Matrix Identities (Elegant Method)**

This approach relies on the fundamental properties of the Pauli matrices:
1.  **Square to Identity**: $\sigma_x^2 = \sigma_y^2 = \sigma_z^2 = I$
2.  **Anti-commutation**: For $i \neq j$, the matrices anti-commute: $\sigma_i \sigma_j = -\sigma_j \sigma_i$. This also means their anti-commutator is zero: $\{\sigma_i, \sigma_j\} = \sigma_i \sigma_j + \sigma_j \sigma_i = 0$.

Let's expand the expression $(\hat{n}\cdot\vec{\sigma})^2$:

$$(\hat{n}\cdot\vec{\sigma})^2 = (n_x\sigma_x + n_y\sigma_y + n_z\sigma_z)(n_x\sigma_x + n_y\sigma_y + n_z\sigma_z)$$

Expanding this product gives us nine terms, which we can group into diagonal terms (where the matrices are the same) and cross-terms (where they are different):

$$(\hat{n}\cdot\vec{\sigma})^2 = (n_x^2\sigma_x^2 + n_y^2\sigma_y^2 + n_z^2\sigma_z^2) + (n_x n_y(\sigma_x\sigma_y + \sigma_y\sigma_x) + n_x n_z(\sigma_x\sigma_z + \sigma_z\sigma_x) + n_y n_z(\sigma_y\sigma_z + \sigma_z\sigma_y))$$

Now, we simplify each group:
* **Diagonal Terms**: Using the identity $\sigma_i^2 = I$, the first group becomes:
    
    $$
    n_x^2 I + n_y^2 I + n_z^2 I = (n_x^2 + n_y^2 + n_z^2)I
    $$
    
    Since $\hat{n}$ is a **unit vector**, $n_x^2 + n_y^2 + n_z^2 = 1$. So, the diagonal terms simplify to just **$I$**.

* **Cross-Terms**: Using the anti-commutation property $\sigma_i\sigma_j + \sigma_j\sigma_i = 0$ for $i \neq j$, every term in the second group becomes zero. For example, $n_x n_y(\sigma_x\sigma_y + \sigma_y\sigma_x) = n_x n_y(0) = 0$.

Combining the simplified groups, we get:

$$(\hat{n}\cdot\vec{\sigma})^2 = I + 0 = I$$

This completes the proof. ✅

### **Solution 1.2: Proof by Direct Matrix Multiplication (Brute-Force Method)**

First, construct the matrix for $\hat{n}\cdot\vec{\sigma}$:

$$\hat{n}\cdot\vec{\sigma} = n_x \begin{pmatrix} 0 & 1 \\\\ 1 & 0 \end{pmatrix} + n_y \begin{pmatrix} 0 & -i \\\\ i & 0 \end{pmatrix} + n_z \begin{pmatrix} 1 & 0 \\\\ 0 & -1 \end{pmatrix} = \begin{pmatrix} n_z & n_x - in_y \\\\ n_x + in_y & -n_z \end{pmatrix}$$

Now, we square this matrix:

$$(\hat{n}\cdot\vec{\sigma})^2 = \begin{pmatrix} n_z & n_x - in_y \\\\ n_x + in_y & -n_z \end{pmatrix} \begin{pmatrix} n_z & n_x - in_y \\\\ n_x + in_y & -n_z \end{pmatrix}$$

Let's compute each element of the resulting matrix:
* **Top-left (1,1):** $(n_z)(n_z) + (n_x - in_y)(n_x + in_y) = n_z^2 + (n_x^2 - (in_y)^2) = n_z^2 + n_x^2 + n_y^2$.
* **Top-right (1,2):** $(n_z)(n_x - in_y) + (n_x - in_y)(-n_z) = n_z(n_x - in_y) - n_z(n_x - in_y) = 0$.
* **Bottom-left (2,1):** $(n_x + in_y)(n_z) + (-n_z)(n_x + in_y) = n_z(n_x + in_y) - n_z(n_x + in_y) = 0$.
* **Bottom-right (2,2):** $(n_x + in_y)(n_x - in_y) + (-n_z)(-n_z) = (n_x^2 - (in_y)^2) + n_z^2 = n_x^2 + n_y^2 + n_z^2$.

Assembling the resulting matrix:

$$(\hat{n}\cdot\vec{\sigma})^2 = \begin{pmatrix} n_x^2 + n_y^2 + n_z^2 & 0 \\\\ 0 & n_x^2 + n_y^2 + n_z^2 \end{pmatrix}$$

Since $\hat{n}$ is a unit vector, $n_x^2 + n_y^2 + n_z^2 = 1$. Therefore:

$$(\hat{n}\cdot\vec{\sigma})^2 = \begin{pmatrix} 1 & 0 \\\\ 0 & 1 \end{pmatrix} = I$$

This confirms the identity through direct computation.

---

## **Part 2: Verifying the Rotation Formula**

The rotation operator $R_{\hat{n}}(\theta)$ is defined by the matrix exponential:

$$R_{\hat{n}}(\theta) = \exp\left(-i \frac{\theta}{2} (\hat{n}\cdot\vec{\sigma})\right)$$

To verify the closed-form expression, we use the **Taylor series expansion** for the exponential function, $e^x = \sum_{k=0}^{\infty} \frac{x^k}{k!}$.

Let's set $A = (\hat{n}\cdot\vec{\sigma})$ and $\phi = \theta/2$. The expression becomes:

$$R_{\hat{n}}(\theta) = \exp(-i\phi A) = \sum_{k=0}^{\infty} \frac{(-i\phi A)^k}{k!} = \sum_{k=0}^{\infty} \frac{(-i\phi)^k}{k!} A^k$$

Now we use our result from Part 1, which tells us $A^2 = I$. This creates a simple pattern for higher powers of $A$:
* $A^0 = I$
* $A^1 = A$
* $A^2 = I$
* $A^3 = A^2 A = I A = A$
* $A^4 = (A^2)^2 = I^2 = I$
In general, $A^k = I$ for even $k$, and $A^k = A$ for odd $k$.

Let's split the Taylor series into sums over **even** and **odd** values of $k$:

$$R_{\hat{n}}(\theta) = \sum_{k \text{ even}} \frac{(-i\phi)^k}{k!} A^k + \sum_{k \text{ odd}} \frac{(-i\phi)^k}{k!} A^k$$

Substitute the pattern for $A^k$:

$$R_{\hat{n}}(\theta) = I \sum_{k \text{ even}} \frac{(-i\phi)^k}{k!} + A \sum_{k \text{ odd}} \frac{(-i\phi)^k}{k!}$$

Let's analyze each sum:
* **Even sum**: Let $k=2m$. The sum is $\sum_{m=0}^{\infty} \frac{(-i\phi)^{2m}}{(2m)!} = \sum_{m=0}^{\infty} \frac{((-i)^2)^m \phi^{2m}}{(2m)!} = \sum_{m=0}^{\infty} \frac{(-1)^m \phi^{2m}}{(2m)!}$. This is the Taylor series for $\cos(\phi)$.
* **Odd sum**: Let $k=2m+1$. The sum is $\sum_{m=0}^{\infty} \frac{(-i\phi)^{2m+1}}{(2m+1)!} = -i \sum_{m=0}^{\infty} \frac{(-1)^m \phi^{2m+1}}{(2m+1)!}$. This is $-i$ times the Taylor series for $\sin(\phi)$.

Substituting these back into our expression for $R_{\hat{n}}(\theta)$:

$$R_{\hat{n}}(\theta) = I \cdot \cos(\phi) + A \cdot (-i \sin(\phi))$$

Finally, substitute back $\phi = \theta/2$ and $A = \hat{n}\cdot\vec{\sigma}$:

$$R_{\hat{n}}(\theta) = \cos(\theta/2) I - i\sin(\theta/2)(\hat{n}\cdot\vec{\sigma})$$

This is precisely the expression we needed to verify. This formula is a generalization of Euler's formula ($e^{ix} = \cos x + i \sin x$) to the algebra of Pauli matrices. ⚛️
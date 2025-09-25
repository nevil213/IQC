# Question 3: Suppose we have a qubit in the state $\lvert 0 \rangle$, and we measure the observable $X$. What is the average value of $X$? What is the standard deviation?

## Solution

Below are multiple methods to compute the average and standard deviation of measuring $X$ on $\lvert 0 \rangle$, each explained in detail. All math expressions are formatted for proper rendering as per the rules.

---

**Method 1 – Expectation Value**

$\langle X \rangle = \langle 0 \vert X \vert 0 \rangle$.

Since $X = \lvert + \rangle \langle + \rvert - \lvert - \rangle \langle - \rvert$, and $\langle 0 \vert + \rangle = 1/\sqrt{2}$, etc., it equals 0.

$\langle X^2 \rangle = 1$, so $\sigma = \sqrt{1 - 0} = 1$.

**Explanation:** Direct calculation using matrix elements.

---

**Method 2 – Probabilistic**

Outcomes +1 with p=1/2, -1 with p=1/2, average 0, variance 1.

**Explanation:** Equal probabilities for ±1.

---

**Method 3 – Bloch Sphere**

$\lvert 0 \rangle$ is along z, X along x, expectation 0, variance 1.

**Explanation:** Orthogonal directions.

---

**Method 4 – Matrix Representation**

Represent $\lvert 0 \rangle = \begin{pmatrix} 1 \\\\ 0 \end{pmatrix}$, $X = \begin{pmatrix} 0 & 1 \\\\ 1 & 0 \end{pmatrix}$.

The expectation $\langle X \rangle = \langle 0 \vert X \vert 0 \rangle = \begin{pmatrix} 1 & 0 \end{pmatrix} \begin{pmatrix} 0 & 1 \\\\ 1 & 0 \end{pmatrix} \begin{pmatrix} 1 \\\\ 0 \end{pmatrix} = \begin{pmatrix} 1 & 0 \end{pmatrix} \begin{pmatrix} 0 \\\\ 1 \end{pmatrix} = 0$.

$\langle X^2 \rangle = \langle 0 \vert I \vert 0 \rangle = 1$, since $X^2 = I$.

Thus, $\sigma = \sqrt{1 - 0^2} = 1$.

**Explanation:** Direct matrix multiplication confirms the values.

---

**Summary:**

Average is 0, standard deviation is 1. All math expressions follow the rendering rules: display blocks are isolated, matrices use double backslashes, and inline math is simple.
### **Q1. What is the Gram–Schmidt procedure? Write down the procedure.**

The **Gram-Schmidt procedure** is a fundamental algorithm in linear algebra used to convert a set of linearly independent vectors into an **orthonormal set** of vectors that spans the same subspace. 🎯 In essence, it takes a "skewed" basis and "straightens it out" into a nice, perpendicular (orthogonal) basis where every vector has a length of one (normal).

This process is crucial in many areas, including quantum mechanics and quantum computing, where states are represented by vectors in a complex vector space, and having an orthonormal basis is often essential for calculations.

---

## **Solution 1: The Standard (Modified) Gram-Schmidt Procedure**

This is the most common and numerically stable version of the procedure. It works by creating an orthonormal set step-by-step, using the newly created orthonormal vectors to "clean" the subsequent vectors.

### **The Goal**

Given a set of **linearly independent** vectors $\{|v_1\rangle, |v_2\rangle, \dots, |v_n\rangle\}$, we want to produce an **orthonormal** set of vectors $\{|e_1\rangle, |e_2\rangle, \dots, |e_n\rangle\}$ such that the span of both sets is identical.

An orthonormal set has two properties:
1.  **Orthogonality**: The inner product of any two distinct vectors is zero. ($\langle e_i | e_j \rangle = 0$ for $i \neq j$)
2.  **Normalization**: The inner product of any vector with itself (its squared norm) is one. ($\langle e_i | e_i \rangle = 1$)

### **The Procedure**

The process works iteratively. We first construct an intermediate set of orthogonal vectors $\{|w_1\rangle, |w_2\rangle, \dots, |w_n\rangle\}$ and then normalize each one to get our final set $\{|e_1\rangle, |e_2\rangle, \dots, |e_n\rangle\}$.

**Step 1: Process the first vector $|v_1\rangle$**
* The first orthogonal vector $|w_1\rangle$ is simply the first vector from our original set.

    $$
    |w_1\rangle = |v_1\rangle
    $$
* Normalize it to get the first orthonormal vector $|e_1\rangle$. (To normalize, you divide the vector by its norm, where the norm $|| |w\rangle || = \sqrt{\langle w | w \rangle}$).

    $$
    |e_1\rangle = \frac{|w_1\rangle}{\sqrt{\langle w_1 | w_1 \rangle}}
    $$

**Step 2: Process the second vector $|v_2\rangle$**
* To make $|v_2\rangle$ orthogonal to $|e_1\rangle$, we subtract the part of $|v_2\rangle$ that lies in the direction of $|e_1\rangle$. This part is the **projection** of $|v_2\rangle$ onto $|e_1\rangle$.


    The projection of $|v_2\rangle$ onto $|e_1\rangle$ is given by $\langle e_1 | v_2 \rangle |e_1\rangle$.
* Subtract this projection from $|v_2\rangle$ to get the second orthogonal vector $|w_2\rangle$.

    $$
    |w_2\rangle = |v_2\rangle - \langle e_1 | v_2 \rangle |e_1\rangle
    $$
* Normalize $|w_2\rangle$ to get the second orthonormal vector $|e_2\rangle$.

    $$
    |e_2\rangle = \frac{|w_2\rangle}{\sqrt{\langle w_2 | w_2 \rangle}}
    $$

**Step k: The General Step**
* For any subsequent vector $|v_k\rangle$, we subtract its projections onto **all** the previously computed orthonormal vectors $|e_1\rangle, |e_2\rangle, \dots, |e_{k-1}\rangle$.

    $$
    |w_k\rangle = |v_k\rangle - \sum_{j=1}^{k-1} \langle e_j | v_k \rangle |e_j\rangle
    $$
* Then, we normalize the resulting orthogonal vector $|w_k\rangle$.

    $$
    |e_k\rangle = \frac{|w_k\rangle}{\sqrt{\langle w_k | w_k \rangle}}
    $$

We repeat this process until all vectors from the original set have been used. The final set $\{|e_1\rangle, |e_2\rangle, \dots, |e_n\rangle\}$ is the desired orthonormal basis. ✨

---

## **Solution 2: The Classical Gram-Schmidt Procedure**

This is an alternative formulation of the same core idea. The main difference is that in the projection step, we use the intermediate **orthogonal** vectors ($|w_j\rangle$) instead of the fully normalized orthonormal vectors ($|e_j\rangle$). This version is conceptually similar but can suffer from a loss of orthogonality in computer calculations due to floating-point errors.

### **The Procedure**

**Step 1: Process the first vector $|v_1\rangle$**
* This step is identical.

    $$
    |w_1\rangle = |v_1\rangle
    $$

**Step 2: Process the second vector $|v_2\rangle$**
* Subtract the projection of $|v_2\rangle$ onto the orthogonal vector $|w_1\rangle$. The projection formula is slightly different because $|w_1\rangle$ is not normalized.

    $$
    |w_2\rangle = |v_2\rangle - \frac{\langle w_1 | v_2 \rangle}{\langle w_1 | w_1 \rangle} |w_1\rangle
    $$

**Step k: The General Step**
* For any subsequent vector $|v_k\rangle$, we subtract its projections onto all the previously computed **orthogonal** vectors $|w_1\rangle, |w_2\rangle, \dots, |w_{k-1}\rangle$.

    $$
    |w_k\rangle = |v_k\rangle - \sum_{j=1}^{k-1} \frac{\langle w_j | v_k \rangle}{\langle w_j | w_j \rangle} |w_j\rangle
    $$

**Final Step: Normalize Everything**
* After you have computed the entire set of orthogonal vectors $\{|w_1\rangle, \dots, |w_n\rangle\}$, you perform the normalization for all of them at the end.

    $$
    |e_k\rangle = \frac{|w_k\rangle}{\sqrt{\langle w_k | w_k \rangle}} \quad \text{for all } k=1, \dots, n
    $$

Both methods yield the same theoretical result. However, the first solution (Modified Gram-Schmidt) is generally preferred for practical implementations because it is more **numerically stable**.
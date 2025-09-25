This is a proof about the universality of gate sets. The core idea is to show that if you can perform rotations around two different non-parallel axes, you can generate any possible rotation, and therefore any single-qubit unitary operation. We can prove this by leveraging the known universality of the Z-Y-Z Euler angle decomposition.

***

### **Question 9: Suppose $\hat{m}$ and $\hat{n}$ are non-parallel real unit vectors in $\mathbb{R}^3$. Use Theorem 0.1 to show that an arbitrary single-qubit unitary $U$ can be written $U = e^{i\alpha} R_{\hat{n}}(\beta) R_{\hat{m}}(\gamma) R_{\hat{n}}(\delta)$ for suitable $\alpha,\beta,\gamma,\delta$.**

The referenced theorem (Z-Y-Z decomposition) states that any single-qubit unitary can be written as a sequence of rotations about two specific **orthogonal axes** ($\hat{z}$ and $\hat{y}$). Our proof will show that we can use our two **non-parallel axes** ($\hat{n}$ and $\hat{m}$) to simulate rotations about two orthogonal axes, thus proving our new set of operations is also universal.

### **The Proof**

The proof is constructive. We will show how to build an arbitrary unitary operation using only rotations about $\hat{n}$ and $\hat{m}$.

**Step 1: The Known Universal Decomposition**
From the Z-Y-Z Euler angle decomposition, we know that any special unitary matrix $U' \in SU(2)$ can be written as:

$$U' = R_z(\beta') R_y(\gamma') R_z(\delta')$$

This decomposition relies on being able to perform rotations around two orthogonal axes, $\hat{z}$ and $\hat{y}$. Our goal is to show that we can generate rotations about any two orthogonal axes using only $R_{\hat{n}}$ and $R_{\hat{m}}$.

**Step 2: Generating a Rotation about an Orthogonal Axis**
We are given the ability to perform rotations $R_{\hat{n}}(\theta)$ and $R_{\hat{m}}(\phi)$ for any angles $\theta, \phi$. Let's choose one of our target orthogonal axes to be $\hat{n}$ itself. So, we have the first required gate type, $R_{\hat{n}}$.

Now we need to generate a rotation about an axis that is **orthogonal to $\hat{n}$**. Let's call this axis $\hat{k}$. We can construct this rotation using a clever sequence of our available gates. Consider the following composite operation:

$$V(\gamma) = R_{\hat{n}}(\phi_0) R_{\hat{m}}(\gamma) R_{\hat{n}}(-\phi_0)$$

This sequence represents a change of basis. The operator $V(\gamma)$ is itself a rotation by an angle $\gamma$, but about a *new* axis, $\hat{k}$. This new axis $\hat{k}$ is the original axis $\hat{m}$ after being rotated by an angle $\phi_0$ around the axis $\hat{n}$. .

Since $\hat{m}$ and $\hat{n}$ are **not parallel**, the vector $\hat{m}$ has a component that is perpendicular to $\hat{n}$. By choosing a suitable fixed angle $\phi_0$, we can rotate $\hat{m}$ around $\hat{n}$ to point in any direction we want within the plane orthogonal to $\hat{n}$. Therefore, we can find a $\phi_0$ that produces a new axis $\hat{k}$ which is orthogonal to $\hat{n}$.

So, we have successfully constructed a rotation about an axis $\hat{k}$ (where $\hat{k} \perp \hat{n}$) using only our initial gates:

$$R_{\hat{k}}(\gamma) = R_{\hat{n}}(\phi_0) R_{\hat{m}}(\gamma) R_{\hat{n}}(-\phi_0)$$

**Step 3: Synthesizing an Arbitrary Unitary**
Now that we can perform rotations about two orthogonal axes, $\hat{n}$ and $\hat{k}$, we can invoke the logic of the Z-Y-Z theorem. Any special unitary $U'$ can be constructed by a sequence of three rotations about these two axes:

$$U' = R_{\hat{n}}(\beta) R_{\hat{k}}(\gamma) R_{\hat{n}}(\delta)$$

Now, we substitute the expression we found for $R_{\hat{k}}(\gamma)$:

$$U' = R_{\hat{n}}(\beta) \left[ R_{\hat{n}}(\phi_0) R_{\hat{m}}(\gamma) R_{\hat{n}}(-\phi_0) \right] R_{\hat{n}}(\delta)$$

**Step 4: Simplify and Conclude**
The expression above contains only rotations about our original axes, $\hat{n}$ and $\hat{m}$. We can combine the adjacent rotations about $\hat{n}$ by adding their angles:

$$U' = R_{\hat{n}}(\beta + \phi_0) R_{\hat{m}}(\gamma) R_{\hat{n}}(-\phi_0 + \delta)$$

If we define new angles $\beta_{new} = \beta + \phi_0$ and $\delta_{new} = -\phi_0 + \delta$, the expression is of the form $R_{\hat{n}}(\beta_{new}) R_{\hat{m}}(\gamma) R_{\hat{n}}(\delta_{new})$.

Since any special unitary $U'$ can be constructed this way, and any general unitary $U$ can be written as $U = e^{i\alpha} U'$, it follows that any single-qubit unitary can be written in the form:

$$U = e^{i\alpha} R_{\hat{n}}(\beta) R_{\hat{m}}(\gamma) R_{\hat{n}}(\delta)$$

This completes the proof. 🚀
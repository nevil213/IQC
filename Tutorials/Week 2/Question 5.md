<!-- 5. Show that all eigenvalues of a unitary matrix have modulus 1, i.e., they can be
written in the form eiθ for some real θ. -->

## Solution

A unitary matrix \( U \) satisfies \( U^\dagger U = I \), where \( U^\dagger \) is the conjugate transpose.

Let \( \lambda \) be an eigenvalue of \( U \), so there exists a non-zero vector \( |\psi\rangle \) such that \( U |\psi\rangle = \lambda |\psi\rangle \).

Take the inner product: \( \langle \psi | U^\dagger U | \psi \rangle = \langle \psi | I | \psi \rangle = \langle \psi | \psi \rangle = 1 \) (assuming normalized).

Left side: \( \langle U \psi | U \psi \rangle = |\lambda|^2 \langle \psi | \psi \rangle = |\lambda|^2 \).

Thus, \( |\lambda|^2 = 1 \), so \( |\lambda| = 1 \).

Any complex number with modulus 1 can be written as \( e^{i\theta} \) for some real \( \theta \).

Therefore, eigenvalues are of the form \( e^{i\theta} \).

### Alternative Proof

From \( U |\psi\rangle = \lambda |\psi\rangle \), apply \( U^\dagger \): \( |\psi\rangle = \lambda U^\dagger |\psi\rangle \).

But \( U^\dagger |\psi\rangle = \bar{\lambda} |\psi\rangle \), since eigenvalues of U^\dagger are conjugates.

From U v = λ v, multiply by U^\dagger: v = λ U^\dagger v, so U^\dagger v = (1/λ) v, so 1/λ is eigenvalue of U^\dagger, so conjugate.

Thus λ conjugate = 1/λ, so λ \bar{λ} =1, |λ|^2=1. Same. 
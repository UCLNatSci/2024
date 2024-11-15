# Mathematical Background for Quantum Mechanics

Quantum mechanics relies on a rigorous mathematical framework that blends linear algebra, calculus, and functional analysis. Understanding the core concepts requires familiarity with several key mathematical tools, including vector spaces, bra-ket notation, operators, commutators, and integral methods.

---
# Useful Mathematics for Quantum Mechanics

Quantum mechanics relies heavily on the mathematical framework of linear algebra, vector spaces, and tensor products. These tools are essential for describing quantum states, operators, and measurements.

---

## Linear Algebra and Vector Spaces

Quantum states are represented as vectors in a **Hilbert space**, a complete, infinite-dimensional vector space equipped with an inner product.

### Key Concepts

- **Hilbert Space**: Denoted as $ \mathcal{H} $, a Hilbert space is a vector space with the following properties:
  - It is complete with respect to the norm induced by the inner product.
  - It includes functions or vectors that satisfy normalisability conditions.

- **Inner Product**: For two vectors $ |\psi\rangle, |\phi\rangle \in \mathcal{H} $, the inner product $ \langle\phi | \psi \rangle $ satisfies:
  ```{math}
  \langle\phi | \psi \rangle = \int \phi^*(x) \psi(x) \, \mathrm{d}x,
  ```
  where $ \phi^*(x) $ is the complex conjugate of $ \phi(x) $.

- **Basis States**: A set of basis vectors $ \{|i\rangle\} $ spans the space, allowing any state $ |\psi\rangle $ to be written as:
  ```{math}
  |\psi\rangle = \sum_i c_i |i\rangle \quad \text{or} \quad |\psi\rangle = \int c(x) |x\rangle \, \mathrm{d}x,
  ```
  where $ c_i $ or $ c(x) $ are expansion coefficients.

### Bra-Ket Notation

- Introduced by Paul Dirac, **bra-ket notation** provides a compact way to express quantum states and their operations:
  - **Ket**: A vector $ |\psi\rangle $ represents a quantum state.
  - **Bra**: The dual vector $ \langle\psi| $ represents the conjugate transpose of $ |\psi\rangle $.
  - **Inner Product**: $ \langle\phi | \psi \rangle $ is the overlap between states.
  - **Outer Product**: $ |\psi\rangle \langle\phi| $ is an operator that acts on vectors.

---

## Tensor Products in Quantum Mechanics

The tensor product ($ \otimes $) is fundamental for describing composite systems, entangled states, and multi-qubit operations in quantum mechanics.

### Combining Quantum States

The state of a composite quantum system is represented using the tensor product of the states of its subsystems:
```{math}
|\psi_{\text{composite}}\rangle = |\psi_1\rangle \otimes |\psi_2\rangle
```

For example, if $ |\psi_1\rangle = \begin{pmatrix} 1 \\ 0 \end{pmatrix} $ (state $ |0\rangle $) and $ |\psi_2\rangle = \begin{pmatrix} 0 \\ 1 \end{pmatrix} $ (state $ |1\rangle $), their combined state is:
```{math}
|\psi_{\text{composite}}\rangle = \begin{pmatrix} 1 \\ 0 \end{pmatrix} \otimes \begin{pmatrix} 0 \\ 1 \end{pmatrix} = \begin{pmatrix} 0 \\ 1 \\ 0 \\ 0 \end{pmatrix}
```

### Describing Entanglement

Entangled states cannot be written as a simple tensor product of individual states. For example:
```{math}
|\psi_{\text{entangled}}\rangle = \frac{1}{\sqrt{2}} (|0\rangle \otimes |1\rangle + |1\rangle \otimes |0\rangle)
```

Using the basis vectors $ |0\rangle = \begin{pmatrix} 1 \\ 0 \end{pmatrix} $ and $ |1\rangle = \begin{pmatrix} 0 \\ 1 \end{pmatrix} $:
```{math}
|\psi_{\text{entangled}}\rangle = \frac{1}{\sqrt{2}} \begin{pmatrix} 0 \\ 1 \\ 0 \\ 0 \end{pmatrix} + \frac{1}{\sqrt{2}} \begin{pmatrix} 0 \\ 0 \\ 1 \\ 0 \end{pmatrix} = \frac{1}{\sqrt{2}} \begin{pmatrix} 0 \\ 1 \\ 1 \\ 0 \end{pmatrix}
```

### Operators on Composite Systems

Tensor products extend operators from individual subsystems to the entire system. For example, the Pauli-X operator acting on a single qubit is:
```{math}
\hat{\sigma}_x = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}
```

For a two-qubit system, $ \hat{\sigma}_x \otimes \hat{I} $ represents $ \hat{\sigma}_x $ acting on the first qubit while leaving the second qubit unchanged:
```{math}
\hat{\sigma}_x \otimes \hat{I} = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix} \otimes \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} =
\begin{pmatrix}
0 & 0 & 1 & 0 \\
0 & 0 & 0 & 1 \\
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0
\end{pmatrix}
```

---

## Measurement and Quantum Gates

Measurements and quantum gates are described using the tensor product framework.

### Measurements in Composite Systems

For an entangled state:
```{math}
|\psi\rangle = \frac{1}{\sqrt{2}} (|0\rangle \otimes |1\rangle + |1\rangle \otimes |0\rangle)
```

If we measure the first qubit:
- **Outcome $ |0\rangle $**: The state collapses to $ |0\rangle \otimes |1\rangle $.
- **Outcome $ |1\rangle $**: The state collapses to $ |1\rangle \otimes |0\rangle $.

The probabilities are:
```{math}
P(|0\rangle) = \frac{1}{2}, \quad P(|1\rangle) = \frac{1}{2}
```

### Quantum Gates

Quantum gates on composite systems are represented using tensor products. For example, the CNOT gate flips the second qubit if the first is $ |1\rangle $:
```{math}
\text{CNOT} =
\begin{pmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & 0 & 1 \\
0 & 0 & 1 & 0
\end{pmatrix}
```

Applying it to $ |1\rangle \otimes |0\rangle $:
```{math}
\text{CNOT} \cdot \begin{pmatrix} 0 \\ 1 \\ 0 \\ 0 \end{pmatrix} = \begin{pmatrix} 0 \\ 1 \\ 0 \\ 0 \end{pmatrix}
```

The state remains unchanged because the second qubit is $ |0\rangle $.

---

## Normalisability and Smoothness of Quantum Wavefunctions

A quantum state must be **normalisable** and satisfy specific conditions of smoothness and continuity to ensure physical validity.

### Normalisability

For a wavefunction $ \psi(x) $, normalisability ensures that the total probability of finding a particle is $ 1 $:
```{math}
\int_{-\infty}^\infty |\psi(x)|^2 \, \mathrm{d}x = 1.
```

Non-normalisable states, such as plane waves, can be treated using the **Dirac delta function** to enforce orthogonality.

---

### Dirac Delta Function

The **Dirac delta function** $ \delta(x) $ is a mathematical tool used to represent point-like distributions. It is not a function in the traditional sense but rather a "generalized function" or distribution. The Dirac delta function satisfies:

1. **Sifting Property**:
   ```{math}
   \int_{-\infty}^\infty \delta(x - x_0) f(x) \, \, \mathrm{d}x = f(x_0),
   ```
   where $ f(x) $ is a well-behaved function.

2. **Normalization**:
   ```{math}
   \int_{-\infty}^\infty \delta(x) \, \, \mathrm{d}x = 1.
   ```

3. **Peaked Behavior**:
   The delta function is often represented heuristically as a sharply peaked function that becomes infinitely narrow and infinitely tall, such that its total integral remains 1.

In quantum mechanics, the Dirac delta function is used to describe the orthogonality and completeness of basis states:

- **Position Eigenstates**:
  The position eigenstates $ |x\rangle $ satisfy:
  ```{math}
  \langle x | x' \rangle = \delta(x - x').
  ```

- **Momentum Eigenstates**:
  The momentum eigenstates $ |p\rangle $ satisfy:
  ```{math}
  \langle p | p' \rangle = \delta(p - p').
  ```

- **Completeness Relations**:
  The delta function ensures that the position and momentum bases form a complete set:
  ```{math}
  \int_{-\infty}^\infty |x\rangle \langle x| \, \mathrm{d}x = \mathbb{I}, \quad \int_{-\infty}^\infty |p\rangle \langle p| \, \mathrm{d}p = \mathbb{I}.
  ```

### Application in Plane Waves

Plane waves, represented by $ \psi(x) = e^{ipx/\hbar} $, are not normalisable in the usual sense. Instead, their normalization involves the delta function:
```{math}
\int_{-\infty}^\infty e^{i(px - p'x')/\hbar} \, \mathrm{d}x = 2\pi\hbar \delta(p - p').
```

This formalism allows us to handle non-normalisable states consistently within the quantum framework.

### Continuity and Smoothness

The wavefunction $ \psi(x) $ must satisfy:
1. **Continuity**: $ \psi(x) $ must be continuous for all $ x $. Discontinuities would lead to unphysical predictions.
2. **Smoothness**: The first derivative $ \frac{d\psi(x)}{\, \mathrm{d}x} $ must be continuous, except at points where the potential $ V(x) $ has an infinite discontinuity (e.g., in a delta potential). This ensures that the Schrödinger equation remains valid.

---

## Operators in Quantum Mechanics

Operators act on quantum states and correspond to physical observables, such as position and momentum.

### Position and Momentum Operators

In the **position representation**, quantum states are wavefunctions $ \psi(x) $, and operators act as follows:
- **Position Operator** $ \hat{x} $:
  ```{math}
  \hat{x} \psi(x) = x \psi(x).
  ```

- **Momentum Operator** $ \hat{p} $:
  ```{math}
  \hat{p} \psi(x) = -i\hbar \frac{d}{\, \mathrm{d}x} \psi(x),
  ```
  where $ \hbar $ is the reduced Planck constant.

### Operator Commutation Relations

Position and momentum operators satisfy the canonical commutation relation:
```{math}
[\hat{x}, \hat{p}] = \hat{x}\hat{p} - \hat{p}\hat{x} = i\hbar.
```

This commutator is fundamental to quantum mechanics and underpins the **Heisenberg uncertainty principle**.

---

## Calculating Commutators

A **commutator** $ [\hat{A}, \hat{B}] $ measures the extent to which two operators fail to commute:
```{math}
[\hat{A}, \hat{B}] = \hat{A}\hat{B} - \hat{B}\hat{A}.
```

### Example: Position and Momentum

For $ \hat{x} $ and $ \hat{p} $:
```{math}
[\hat{x}, \hat{p}] = i\hbar.
```

Using this commutator, the **Heisenberg uncertainty principle** is derived:
```{math}
\Delta x \Delta p \geq \frac{\hbar}{2}.
```

---

## Wavefunctions in Position and Momentum Space

Quantum states can be represented in **position space** or **momentum space**, connected via the Fourier transform.

### Position Space

In position space, a state $ |\psi\rangle $ is represented by the wavefunction $ \psi(x) $, where:
```{math}
\psi(x) = \langle x | \psi \rangle.
```
The probability of finding the particle at position $ x $ is:
```{math}
P(x) = |\psi(x)|^2.
```

### Momentum Space

In momentum space, a state is represented by $ \phi(p) $, where:
```{math}
\phi(p) = \langle p | \psi \rangle.
```
The probability of finding the particle with momentum $ p $ is:
```{math}
P(p) = |\phi(p)|^2.
```

### Fourier Transform

The wavefunctions in position and momentum space are related by the Fourier transform:
```{math}
\phi(p) = \frac{1}{\sqrt{2\pi\hbar}} \int_{-\infty}^\infty \psi(x) e^{-ipx/\hbar} \, \mathrm{d}x,
```
```{math}
\psi(x) = \frac{1}{\sqrt{2\pi\hbar}} \int_{-\infty}^\infty \phi(p) e^{ipx/\hbar} \, \mathrm{d}p.
```

---

## Observables and Eigenstates

Observables correspond to **Hermitian operators** $ \hat{O} $, which have real eigenvalues. Measuring an observable $ \hat{O} $ yields one of its eigenvalues $ o $, and the quantum state collapses to the corresponding eigenstate $ |o\rangle $:
```{math}
\hat{O} |o\rangle = o |o\rangle.
```

### Expectation Value

The expectation value of an observable $ \hat{O} $ in a state $ |\psi\rangle $ is:
```{math}
\langle \hat{O} \rangle = \langle \psi | \hat{O} | \psi \rangle.
```

For position and momentum:
- Position expectation value:
  ```{math}
  \langle \hat{x} \rangle = \int_{-\infty}^\infty x |\psi(x)|^2 \, \mathrm{d}x.
  ```

- Momentum expectation value:
  ```{math}
  \langle \hat{p} \rangle = \int_{-\infty}^\infty \phi^*(p) p \phi(p) \, \mathrm{d}p.
  ```

---

## Summary of Key Equations

1. **Normalisation**:
   ```{math}
   \int_{-\infty}^\infty |\psi(x)|^2 \, \mathrm{d}x = 1.
   ```

2. **Dirac Delta Orthogonality**:
   ```{math}
   \langle x | x' \rangle = \delta(x - x'), \quad \langle p | p' \rangle = \delta(p - p').
   ```

3. **Position and Momentum Operators**:
   ```{math}
   \hat{x} \psi(x) = x \psi(x), \quad \hat{p} \psi(x) = -i\hbar \frac{d}{\, \mathrm{d}x} \psi(x).
   ```

4. **Commutation Relation**:
   ```{math}
   [\hat{x}, \hat{p}] = i\hbar.
   ```

5. **Fourier Transform**:
   ```{math}
   \phi(p) = \frac{1}{\sqrt{2\pi\hbar}} \int_{-\infty}^\infty \psi(x) e^{-ipx/\hbar} \, \mathrm{d}x.
   ```

6. **Expectation Value**:
   ```{math}
   \langle \hat{O} \rangle = \langle \psi | \hat{O} | \psi \rangle.
   ```

7. **Uncertainty Principle**:
   ```{math}
   \Delta x \Delta p \geq \frac{\hbar}{2}.
   ```

Understanding these mathematical tools is essential for exploring quantum mechanics, from solving the Schrödinger equation to analyzing quantum operators and interpreting physical measurements.
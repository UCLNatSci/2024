# Mathematical Background for Quantum Mechanics

Quantum mechanics relies on a rigorous mathematical framework that blends linear algebra, calculus, and functional analysis. Understanding the core concepts requires familiarity with several key mathematical tools, including vector spaces, bra-ket notation, operators, commutators, and integral methods.

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
  |\psi\rangle = \sum_i c_i |i\rangle \quad \text{or} \quad |\psi\rangle = \int c(x) |x\rangle \mathrm{d}x,
  ```
  where $ c_i $ or $ c(x) $ are expansion coefficients.

### Bra-Ket Notation

- Introduced by Paul Dirac, **bra-ket notation** provides a compact way to express quantum states and their operations:
  - **Ket**: A vector $ |\psi\rangle $ represents a quantum state.
  - **Bra**: The dual vector $ \langle\psi| $ represents the conjugate transpose of $ |\psi\rangle $.
  - **Inner Product**: $ \langle\phi | \psi \rangle $ is the overlap between states.
  - **Outer Product**: $ |\psi\rangle \langle\phi| $ is an operator that acts on vectors.

---

## Normalisability and Smoothness of Quantum Wavefunctions

A quantum state must be **normalisable** and satisfy specific conditions of smoothness and continuity to ensure physical validity.

### Normalisability

For a wavefunction $ \psi(x) $, normalisability ensures that the total probability of finding a particle is $ 1 $:
```{math}
\int_{-\infty}^\infty |\psi(x)|^2 \mathrm{d}x = 1.
```

Non-normalisable states, such as plane waves, can be treated using the **Dirac delta function** to enforce orthogonality.

---

### Dirac Delta Function

The **Dirac delta function** $ \delta(x) $ is a mathematical tool used to represent point-like distributions. It is not a function in the traditional sense but rather a "generalized function" or distribution. The Dirac delta function satisfies:

1. **Sifting Property**:
   ```{math}
   \int_{-\infty}^\infty \delta(x - x_0) f(x) \, \mathrm{d}x = f(x_0),
   ```
   where $ f(x) $ is a well-behaved function.

2. **Normalization**:
   ```{math}
   \int_{-\infty}^\infty \delta(x) \, \mathrm{d}x = 1.
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
  \int_{-\infty}^\infty |x\rangle \langle x| \mathrm{d}x = \mathbb{I}, \quad \int_{-\infty}^\infty |p\rangle \langle p| \mathrm{d}p = \mathbb{I}.
  ```

### Application in Plane Waves

Plane waves, represented by $ \psi(x) = e^{ipx/\hbar} $, are not normalisable in the usual sense. Instead, their normalization involves the delta function:
```{math}
\int_{-\infty}^\infty e^{i(px - p'x')/\hbar} \mathrm{d}x = 2\pi\hbar \delta(p - p').
```

This formalism allows us to handle non-normalisable states consistently within the quantum framework.

### Continuity and Smoothness

The wavefunction $ \psi(x) $ must satisfy:
1. **Continuity**: $ \psi(x) $ must be continuous for all $ x $. Discontinuities would lead to unphysical predictions.
2. **Smoothness**: The first derivative $ \frac{d\psi(x)}{\mathrm{d}x} $ must be continuous, except at points where the potential $ V(x) $ has an infinite discontinuity (e.g., in a delta potential). This ensures that the Schrödinger equation remains valid.

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
  \hat{p} \psi(x) = -i\hbar \frac{d}{\mathrm{d}x} \psi(x),
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
\phi(p) = \frac{1}{\sqrt{2\pi\hbar}} \int_{-\infty}^\infty \psi(x) e^{-ipx/\hbar} \mathrm{d}x,
```
```{math}
\psi(x) = \frac{1}{\sqrt{2\pi\hbar}} \int_{-\infty}^\infty \phi(p) e^{ipx/\hbar} \mathrm{d}p.
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
  \langle \hat{x} \rangle = \int_{-\infty}^\infty x |\psi(x)|^2 \mathrm{d}x.
  ```

- Momentum expectation value:
  ```{math}
  \langle \hat{p} \rangle = \int_{-\infty}^\infty \phi^*(p) p \phi(p) \mathrm{d}p.
  ```

---

## Summary of Key Equations

1. **Normalisation**:
   ```{math}
   \int_{-\infty}^\infty |\psi(x)|^2 \mathrm{d}x = 1.
   ```

2. **Dirac Delta Orthogonality**:
   ```{math}
   \langle x | x' \rangle = \delta(x - x'), \quad \langle p | p' \rangle = \delta(p - p').
   ```

3. **Position and Momentum Operators**:
   ```{math}
   \hat{x} \psi(x) = x \psi(x), \quad \hat{p} \psi(x) = -i\hbar \frac{d}{\mathrm{d}x} \psi(x).
   ```

4. **Commutation Relation**:
   ```{math}
   [\hat{x}, \hat{p}] = i\hbar.
   ```

5. **Fourier Transform**:
   ```{math}
   \phi(p) = \frac{1}{\sqrt{2\pi\hbar}} \int_{-\infty}^\infty \psi(x) e^{-ipx/\hbar} \mathrm{d}x.
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
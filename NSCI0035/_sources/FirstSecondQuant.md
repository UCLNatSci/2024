# First and Second Quantisation

---

## First Quantisation

First quantisation is the historical framework for quantum mechanics in which the classical physical observables, such as position and momentum, are replaced by operators acting on wavefunctions. It focuses on the quantisation of individual particles.

### Key Features

**Wavefunction:**
  The state of a particle is described by a wavefunction $ \psi(\mathbf{r}, t) $, where $ \mathbf{r} $ is the position vector, and $ t $ is time. The wavefunction encodes the probability amplitude of finding the particle at a specific location and time.

**Operators:**
  Classical quantities like position ($ \mathbf{r} $) and momentum ($ \mathbf{p} $) are promoted to operators:
  ```{math}
  \hat{\mathbf{r}} = \mathbf{r}, \quad \hat{\mathbf{p}} = -i\hbar \nabla
  ```
  The Hamiltonian operator ($ \hat{H} $) governs the time evolution of the wavefunction.

**Schrödinger Equation:**
  The wavefunction evolves according to the time-dependent Schrödinger equation:
  ```{math}
  i\hbar \frac{\partial \psi(\mathbf{r}, t)}{\partial t} = \hat{H} \psi(\mathbf{r}, t)
  ```

**Quantisation of Energy:**
  Solving the Schrödinger equation often leads to discrete energy levels for bound systems, such as the energy levels of the hydrogen atom.

*Example*: Particle in a Box:
  A particle in a one-dimensional box has wavefunctions:
  ```{math}
  \psi_n(x) = \sqrt{\frac{2}{L}} \sin\left(\frac{n\pi x}{L}\right)
  ```
  with quantised energies:
  ```{math}
  E_n = \frac{n^2 \pi^2 \hbar^2}{2mL^2}
  ```

### Limitations of First Quantisation

First quantisation is primarily focused on single-particle systems and cannot inherently describe systems with variable particle numbers, such as fields or many-body interactions.

---

## Second Quantisation

Second quantisation is a more general framework in which the wavefunction itself is treated as an operator. It is the basis for quantum field theory and is particularly suited for systems with many particles or variable particle numbers.

### Key Features

**Field Operators:**
  In second quantisation, field operators replace the wavefunction. These operators act on the quantum state of the system to create or annihilate particles.
  Creation ($ \hat{a}^\dagger $) and annihilation ($ \hat{a} $) operators are defined such that:
  ```{math}
  \hat{a}^\dagger |n\rangle = \sqrt{n+1} |n+1\rangle, \quad \hat{a} |n\rangle = \sqrt{n} |n-1\rangle
  ```

**Fock Space:**
  The quantum states are described in Fock space, which accounts for all possible particle numbers.
  *Example* states in Fock space:
  ```{math}
  |0\rangle \text{ (vacuum state)}, \quad |1\rangle \text{ (single-particle state)}, \quad |n\rangle \text{ (n-particle state)}
  ```

**Hamiltonian in Second Quantisation:**
  The Hamiltonian is expressed in terms of creation and annihilation operators. For a simple free particle, the Hamiltonian is:
  ```{math}
  \hat{H} = \sum_k \epsilon_k \hat{a}^\dagger_k \hat{a}_k
  ```
  where $ \epsilon_k $ is the energy of the particle in mode $ k $.

*Example*: Quantum Harmonic Oscillator:
  In second quantisation, the Hamiltonian is written as:
  ```{math}
  \hat{H} = \hbar \omega \left( \hat{a}^\dagger \hat{a} + \frac{1}{2} \right)
  ```
  where $ \hat{a}^\dagger $ and $ \hat{a} $ are the creation and annihilation operators.

**Particle Statistics:**
  Second quantisation naturally incorporates the quantum statistics of particles:
  Bosons (integer spin): Obey Bose-Einstein statistics, allowing multiple particles in the same state.
  Fermions (half-integer spin): Obey the Pauli exclusion principle and Fermi-Dirac statistics, disallowing multiple particles in the same state.

**Field Theory:**
  Second quantisation is essential for quantum field theory, where particles are excitations of underlying fields.

---

### Comparison of First and Second Quantisation

| Feature                | First Quantisation                        | Second Quantisation                      |
|------------------------|-------------------------------------------|------------------------------------------|
| Focus                  | Single-particle systems                  | Many-particle systems or fields          |
| Wavefunction           | Describes particle states                | Replaced by field operators              |
| Particle Number        | Fixed                                    | Variable                                |
| Framework              | Schrödinger equation                     | Fock space and creation/annihilation ops |
| Applications           | Atomic and molecular systems             | Quantum field theory, condensed matter   |

---

### Applications of Second Quantisation

*Quantum Electrodynamics (QED):*
  Describes the interaction of light and matter by quantising the electromagnetic field.
   
*Condensed Matter Physics:*
  Used to study phenomena like superconductivity, magnetism, and Bose-Einstein condensation.

*Particle Physics:*
  Fundamental particles are treated as excitations of quantum fields (e.g., electrons, photons).

*Many-Body Systems:*
  Second quantisation provides a natural framework for studying systems with large numbers of interacting particles, such as in nuclear physics or solid-state systems.

---

### Summary

First Quantisation is the framework for describing single-particle systems with fixed particle numbers, relying on the Schrödinger equation and wavefunctions.

Second Quantisation generalises the approach by treating wavefunctions as operators, enabling the study of variable particle numbers, fields, and many-body systems.  This second quantisation underpins modern quantum field theory and is indispensable for understanding fundamental particle interactions and many-body physics.

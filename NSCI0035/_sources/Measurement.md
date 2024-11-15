# Measurement in Quantum Mechanics

In quantum mechanics, the measurement problem arises from the difference between the deterministic evolution of a quantum system's wavefunction according to the Schrödinger equation and the probabilistic nature of measurement outcomes. This section expands on each area with examples.

## Schrödinger Equation and Deterministic Evolution

The time evolution of a quantum system is described by the Schrödinger equation:
```{math}
i\hbar \frac{\partial}{\partial t} |\psi(t)\rangle = \hat{H} |\psi(t)\rangle
```
where $ \hat{H} $ is the Hamiltonian operator of the system.

### Example: A Free Particle

Consider a free particle of mass $ m $ moving in one dimension. The Hamiltonian for this particle is:
```{math}
\hat{H} = \frac{\hat{p}^2}{2m} = -\frac{\hbar^2}{2m} \frac{\partial^2}{\partial x^2}
```
If we start with an initial wavefunction $ \psi(x, 0) $, we can determine the particle’s wavefunction $ \psi(x, t) $ at any later time by solving the Schrödinger equation. This evolution is deterministic: given the initial wavefunction, we can predict the wavefunction at any future time.

The measurement problem arises because this deterministic evolution does not explain what happens when we observe the particle’s position or momentum, as measurements yield only one of the possible values.

## Measurement and Wavefunction Collapse

When a measurement is performed on a quantum system, the wavefunction appears to "collapse" to an eigenstate of the observable being measured, yielding a single outcome among many possible ones. This process is described by the **Born rule**, which gives the probability of obtaining a particular result.

```{math}
P(a_i) = |\langle a_i | \psi \rangle|^2
```
where $ |a_i\rangle $ is an eigenstate of the measured observable with eigenvalue $ a_i $.

### Example: Spin Measurement for an Electron

Consider an electron with spin-1/2. If the electron is in the state:
```{math}
|\psi\rangle = \frac{1}{\sqrt{2}} \left( | \uparrow_z \rangle + | \downarrow_z \rangle \right)
```
where $ | \uparrow_z \rangle $ and $ | \downarrow_z \rangle $ are the spin-up and spin-down states along the $ z $-axis, then a measurement of the spin along the $ z $-axis will result in either $ +\hbar/2 $ or $ -\hbar/2 $ with equal probability $ P = 1/2 $.

Before measurement, the electron is in a superposition, but after measurement, the wavefunction appears to "collapse" to either $ | \uparrow_z \rangle $ or $ | \downarrow_z \rangle $, with the corresponding probability given by the Born rule.

## The Role of Superposition

Quantum systems can exist in a superposition of multiple states, leading to interference effects that are unique to quantum mechanics. However, when measured, only one of the possible states is observed, which raises questions about the status of the other states in the superposition.

Consider a particle in a superposition:
```{math}
|\psi\rangle = c_1 |a_1\rangle + c_2 |a_2\rangle
```
where $ |a_1\rangle $ and $ |a_2\rangle $ are orthogonal eigenstates of an observable with eigenvalues $ a_1 $ and $ a_2 $. Measuring the observable seems to cause the system to "choose" one of these states randomly.

### Example: Double-Slit Experiment

In the famous double-slit experiment, an electron passes through two slits and interferes with itself, creating an interference pattern on a screen behind the slits. The electron’s wavefunction is a superposition of states corresponding to passing through slit 1 and slit 2:
```{math}
|\psi\rangle = \frac{1}{\sqrt{2}} (|\text{slit 1}\rangle + |\text{slit 2}\rangle)
```
If we observe which slit the electron goes through, the interference pattern disappears, and we observe the electron passing through only one slit. This phenomenon illustrates the collapse of the superposition upon measurement, yet the theory itself does not explain why this happens.

## Example: Isolated System and Measuring Device

To further explore the measurement problem, let's examine an isolated system being measured by a generic measuring device. This example emphasizes the role of entanglement and the challenge of explaining collapse.

1. **System State**: Suppose we have a quantum system $ S $ in a superposition:
   ```{math}
   |\psi_S\rangle = \alpha |0\rangle + \beta |1\rangle
   ```
   where $ |0\rangle $ and $ |1\rangle $ are eigenstates of an observable associated with $ S $.

2. **Measuring Device State**: Let the measuring device $ M $ initially be in a "ready" state $ |M_0\rangle $.

3. **Interaction and Entanglement**: When $ S $ interacts with $ M $, the two systems become entangled. The joint state of $ S $ and $ M $ becomes:
   ```{math}
   |\Psi_{SM}\rangle = \alpha |0\rangle \otimes |M_0\rangle + \beta |1\rangle \otimes |M_1\rangle
   ```
   where $ |M_0\rangle $ and $ |M_1\rangle $ are the states of the measuring device corresponding to the system being in $ |0\rangle $ and $ |1\rangle $, respectively.

4. **Measurement Problem**: After entanglement, the combined state $ |\Psi_{SM}\rangle $ is still in a superposition. According to quantum theory, this superposition persists indefinitely, but in practice, when we observe the device, we find it in either $ |M_0\rangle $ or $ |M_1\rangle $ with probabilities $ |\alpha|^2 $ and $ |\beta|^2 $, respectively. The measurement problem asks why we never observe superpositions like $ |0\rangle \otimes |M_1\rangle + |1\rangle \otimes |M_0\rangle $.

## Diagram of Measurement Process

Here’s a diagram illustrating this measurement process:

**Before Measurement:**  
$|\psi_S\rangle$ (System) —–> $|M_0\rangle$ (Measuring Device Ready State)

**After Interaction (Entangled State):**  
$\alpha|0\rangle \otimes |M_0\rangle + \beta|1\rangle \otimes |M_1\rangle$

**Observed Outcome:**  
Either $|0\rangle \otimes |M_0\rangle$ or $|1\rangle \otimes |M_1\rangle$


This scenario shows that, according to quantum mechanics, the entire system remains in a superposition after measurement. However, real observations indicate that the system collapses into one definite state.
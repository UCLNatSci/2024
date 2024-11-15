# Bohmian Mechanics (Pilot Wave Theory)

**Bohmian Mechanics**, also known as **Pilot Wave Theory**, is an interpretation of quantum mechanics developed by physicist David Bohm in the 1950s. It offers an alternative to the standard Copenhagen interpretation by providing a deterministic, realist account of quantum phenomena. In Bohmian Mechanics, particles have well-defined positions and velocities at all times, guided by a "pilot wave" that dictates their trajectories.

## Key Assumptions and Concepts

Bohmian Mechanics departs from traditional quantum mechanics by introducing the concept of particle trajectories and removing the need for wavefunction collapse. Here are the foundational principles of this interpretation:

### Particles with Definite Positions and Trajectories

In Bohmian Mechanics, particles are treated as real, physical entities with definite positions and well-defined trajectories at all times. Unlike the probabilistic interpretation of particles in the Copenhagen framework, Bohmian Mechanics assumes that particles have exact positions and follow specific paths determined by the pilot wave.

- **Deterministic Nature**: Given the initial positions of particles and the form of the guiding wavefunction, their future positions and trajectories are completely determined.
- **Ontological Commitment**: Bohmian Mechanics is realist, assigning a clear physical existence to particles and their properties, independent of measurement.

#### Example: Particle in a Potential

Consider a particle moving under a potential $ V(x) $ with a wavefunction $ \psi(x, t) $ satisfying the Schrödinger equation:
```{math}
i \hbar \frac{\partial \psi}{\partial t} = -\frac{\hbar^2}{2m} \nabla^2 \psi + V(x) \psi
```
In Bohmian Mechanics, the particle has a position $ x(t) $ at all times, and its velocity is determined by the guiding equation (discussed below), based on the wavefunction $ \psi(x, t) $.

### The Pilot Wave (Guiding Wave)

The **pilot wave**, represented by the wavefunction $ \psi $, determines the behavior of particles through a guiding equation. In this interpretation, the wavefunction is treated as a real field that "guides" the particles, rather than as a mere probability amplitude.

- **Wave-Particle Duality**: In Bohmian Mechanics, particles and waves coexist. The wavefunction acts as a guiding wave, influencing the motion of particles, while the particles themselves follow well-defined trajectories.
- **No Collapse**: There is no wavefunction collapse in Bohmian Mechanics. The wavefunction evolves continuously according to the Schrödinger equation, and particles follow trajectories without any discontinuous changes.

### The Guiding Equation

The **guiding equation** in Bohmian Mechanics determines the velocity of each particle based on the gradient of the phase of the wavefunction. For a particle with position $ x $ and wavefunction $ \psi(x, t) $, the particle’s velocity $ v $ is given by:
```{math}
\mathbf{v}(x, t) = \frac{\hbar}{m} \operatorname{Im} \left( \frac{\nabla \psi(x, t)}{\psi(x, t)} \right)
```
or, equivalently, if we write the wavefunction in polar form $ \psi(x, t) = R(x, t) e^{i S(x, t)/\hbar} $,
```{math}
\mathbf{v}(x, t) = \frac{\nabla S(x, t)}{m}
```
where $ S(x, t) $ is the phase of the wavefunction. This equation means that the pilot wave dictates the direction and speed of each particle, based on the configuration of the wavefunction at each point.

#### Example Calculation: Velocity from the Guiding Equation

Suppose we have a particle in a one-dimensional wavefunction $ \psi(x, t) = R(x, t) e^{i S(x, t)/\hbar} $, with $ S(x, t) = kx - \omega t $. The velocity of the particle is:
```{math}
v(x, t) = \frac{1}{m} \frac{\partial S}{\partial x} = \frac{k}{m}
```
This constant velocity $ v = k/m $ shows how the pilot wave guides the particle along a well-defined trajectory.

### Quantum Equilibrium and the Born Rule

In Bohmian Mechanics, the **Born rule** is interpreted as a statistical distribution of particle positions rather than as an intrinsic property of the wavefunction itself. The distribution of particle positions in an ensemble of systems follows the probability density $ |\psi(x)|^2 $, which is called **quantum equilibrium**.

- **Quantum Equilibrium Hypothesis**: If an ensemble of particles has an initial distribution matching $ |\psi(x)|^2 $, then this distribution will remain in equilibrium over time, consistently with the predictions of standard quantum mechanics.
- **Emergence of Probabilities**: Unlike in the Copenhagen interpretation, where probabilities are fundamental, probabilities in Bohmian Mechanics arise from ignorance about the precise initial positions of particles in a large ensemble.

### Measurement Without Collapse

In Bohmian Mechanics, measurement does not collapse the wavefunction. Instead, the wavefunction and particles continue to evolve deterministically according to the Schrödinger and guiding equations. The appearance of wavefunction collapse is effectively the result of interaction between the particle and the measurement apparatus.

- **Effective Collapse**: During a measurement, the wavefunction of the system-apparatus combination becomes highly correlated with the particle's position. This correlation gives the appearance of a collapse, but in Bohmian Mechanics, it is simply a result of the deterministic evolution of the wavefunction.
- **Measurement as Interaction**: Measurement is understood as an interaction that reveals the pre-existing position of the particle, rather than an event that creates a specific outcome from a superposition.

#### Example: Double-Slit Experiment in Bohmian Mechanics

In the double-slit experiment, a particle passes through two slits and an interference pattern forms on a screen. In Bohmian Mechanics, the particle itself only goes through one slit, but the wavefunction passes through both, creating an interference pattern that guides the particle to regions of constructive interference.

- **Trajectory of Particles**: Each particle follows a unique trajectory influenced by the pilot wave. When many particles are sent through the slits, their trajectories collectively form an interference pattern on the screen, matching the predictions of quantum mechanics.

### Determinism and Realism

Bohmian Mechanics is a **deterministic** theory, meaning that if we know the initial position of a particle and the wavefunction, we can predict its future position and trajectory with certainty. Unlike the Copenhagen interpretation, Bohmian Mechanics assumes a **realist ontology**, meaning it attributes a definite reality to particles and their trajectories, as well as to the guiding wave.

- **Deterministic Evolution**: The wavefunction and particle trajectories evolve according to deterministic laws, without randomness. The probabilistic nature of quantum measurements emerges only from uncertainty about initial conditions.
- **Realist Framework**: Bohmian Mechanics assigns real, physical existence to both the particles and the pilot wave, contrasting with the Copenhagen interpretation’s instrumentalist view.

## Differences Between Bohmian Mechanics and Other Interpretations

Bohmian Mechanics contrasts with several other interpretations in its treatment of particles, wavefunction collapse, and the nature of reality.

### Copenhagen Interpretation

The **Copenhagen interpretation** views particles probabilistically and introduces wavefunction collapse upon measurement. In Bohmian Mechanics, particles have definite trajectories, and there is no wavefunction collapse.

- **Collapse**: Bohmian Mechanics has no collapse; the Copenhagen interpretation requires collapse during measurement.
- **Reality**: Bohmian Mechanics is realist, attributing real existence to particles and trajectories, while the Copenhagen interpretation is often instrumentalist.

### Many-Worlds Interpretation (MWI)

In the **Many-Worlds Interpretation (MWI)**, all possible outcomes of a measurement exist in parallel, branching universes. Bohmian Mechanics, in contrast, assumes only one outcome, determined by the particle's trajectory and the guiding wave.

- **Number of Worlds**: Bohmian Mechanics posits a single, deterministic world, while MWI posits a branching multiverse.
- **Guiding Wave vs. Universal Wavefunction**: Bohmian Mechanics uses a pilot wave to guide particles in one world, whereas MWI interprets the wavefunction as a real entity encompassing all possible outcomes.

### Objective Collapse Theories

**Objective Collapse Theories** modify quantum mechanics to include spontaneous collapse of the wavefunction. In Bohmian Mechanics, the wavefunction does not collapse; it evolves continuously and deterministically, guiding particles along their trajectories.

- **Collapse Mechanism**: Objective collapse theories propose physical processes for collapse, while Bohmian Mechanics requires no collapse.
- **Realism**: Both objective collapse theories and Bohmian Mechanics are realist, but they differ in their treatment of the wavefunction.

## Summary of Key Features

| Feature                    | Bohmian Mechanics                              | Other Interpretations             |
|----------------------------|-----------------------------------------------|------------------------------------|
| **Wavefunction**           | Real guiding field, continuously evolving     | Probabilistic tool (Copenhagen), real but branching (MWI) |
| **Measurement**            | Reveals pre-existing particle position, no collapse | Causes collapse in Copenhagen, branching in MWI |
| **Determinism**            | Deterministic particle trajectories           | Probabilistic (Copenhagen), deterministic in MWI |
| **Reality**                | Realist: particles and wave are real          | Instrumentalist (Copenhagen
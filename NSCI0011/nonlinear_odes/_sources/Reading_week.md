# Reading Week - Investigate Dynamical Systems

Over reading week read through Chapter 5 of Steven Strogatz — *Nonlinear Dynamics and Chaos*.  It will explain to you some of the following ideas in a formal way which will be useful for the second part of your project. (optionally chapters 6 and 7 are also useful!)

A dynamical system describes how a state evolves over time:

- **Continuous time (ODEs):**  
$dx/dt = f(x)$

- **Discrete time (maps):**  
$x_{n+1} = f(x_n) $

The state \(x\) may represent position, population, voltage, climate variables, etc. The goal is to understand *long-term behaviour* from simple rules.

When investigating a system, ask:

- What are the **fixed points / equilibria**?
- Are they **stable or unstable**?
- Are there **limit cycles** or periodic orbits?
- Is the motion **quasiperiodic** or **chaotic**?
- How sensitive is it to initial conditions?


## Tools to investigate dynamical systems

### Phase Space
All possible states of the system. Dynamics becomes geometry.

### Linear Stability
Linearise around equilibrium using the Jacobian:
- Eigenvalues → determine local stability
- Real part > 0 → unstable
- Real part < 0 → stable

### Bifurcations
Qualitative change in behaviour as a parameter varies:
- Saddle-node
- Transcritical
- Pitchfork
- Hopf

### Lyapunov Exponents
Measure exponential separation of nearby trajectories.
- Largest exponent > 0 → chaos

### Attractors
Sets that trajectories approach:
- Fixed points
- Limit cycles
- Strange (chaotic) attractors

### Canonical Example Systems

| System | Why it matters |
|---------|----------------|
| Logistic map | Period-doubling and route to chaos |
| Lorenz system | Strange attractor, deterministic chaos |
| Van der Pol oscillator | Nonlinear limit cycle |
| Simple pendulum | Hamiltonian vs damped behaviour |
| Duffing oscillator | Bifurcations and chaos |



